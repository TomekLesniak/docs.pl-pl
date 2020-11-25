---
title: 'Istotna zmiana: domyślne mechanizmy szyfrowania TLS dla platformy .NET w systemie Linux'
description: Dowiedz się więcej o istotnej zmianie w programie .NET 5,0, w której platforma .NET w systemie Linux uwzględnia konfigurację OpenSSL dla domyślnych mechanizmów szyfrowania podczas przeprowadzania protokołów TLS/SSL.
ms.date: 10/16/2020
ms.openlocfilehash: f1c23517161ac213a9cd7cf6e7da8eebeb91583b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761320"
---
# <a name="default-tls-cipher-suites-for-net-on-linux"></a>Domyślne mechanizmy szyfrowania TLS dla platformy .NET w systemie Linux

Platforma .NET w systemie Linux uwzględnia teraz konfigurację OpenSSL dla domyślnych mechanizmów szyfrowania podczas wykonywania protokołu TLS/SSL za pośrednictwem <xref:System.Net.Security.SslStream> klasy lub operacji wyższego poziomu, takich jak https za pośrednictwem <xref:System.Net.Http.HttpClient> klasy. Jeśli domyślne mechanizmy szyfrowania nie są skonfigurowane jawnie, platforma .NET w systemie Linux używa ściśle ograniczonej listy dozwolonych mechanizmów szyfrowania.

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET program .NET nie szanuje konfiguracji systemu dla domyślnych mechanizmów szyfrowania. Domyślna lista mechanizmów szyfrowania dla platformy .NET w systemie Linux jest bardzo zależna.

Począwszy od platformy .NET 5,0, .NET w systemie Linux uwzględnia konfigurację OpenSSL dla domyślnych mechanizmów szyfrowania, gdy jest ona określona w *OpenSSL. cnf*. Jeśli mechanizmy szyfrowania nie są jawnie skonfigurowane, Jedynymi dozwolonymi mechanizmami szyfrowania są następujące:

- Mechanizmy szyfrowania TLS 1,3
- TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384
- TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256
- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
- TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384
- TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256

Ponieważ ta wartość domyślna nie obejmuje żadnych mechanizmów szyfrowania, które są zgodne z protokołem TLS 1,0 lub TLS 1,1, te starsze wersje protokołów są skutecznie wyłączone.

Dostarczenie wartości CipherSuitePolicy do SslStream dla określonej sesji nadal zastępuje zawartość pliku konfiguracji i/lub wartość domyślną dla platformy .NET.

## <a name="reason-for-change"></a>Przyczyna zmiany

Użytkownicy korzystający z platformy .NET w systemie Linux zażądali zmiany konfiguracji domyślnej na <xref:System.Net.Security.SslStream> taką, która zapewnia wysoką ocenę zabezpieczeń z narzędzi do oceny innych firm.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

Nowe wartości domyślne mogą być wykonywane podczas komunikowania się z nowoczesnymi klientami lub serwerami. Jeśli musisz rozwinąć listę domyślnych pakietów szyfrowania, aby akceptować starszych klientów (lub aby skontaktować się z starszymi serwerami), określ `CipherSuitePolicy` wartość lub Zmień plik konfiguracji OpenSSL. W przypadku wielu dystrybucji systemu Linux plik konfiguracji OpenSSL ma */etc/SSL/OpenSSL.cnf*.

Ten przykładowy plik *OpenSSL. cnf* jest minimalnym plikiem równoważnym z domyślnymi zasadami szyfrowania dla platformy .NET 5,0 i nowszych w systemie Linux. Zamiast zamieniać plik systemowy, należy scalić te koncepcje z plikiem, który jest obecny w systemie.

```ini
openssl_conf = default_conf

[default_conf]
ssl_conf = ssl_sect

[ssl_sect]
system_default = system_default_sect

[system_default_sect]
CipherString = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES256-SHA384:ECDHE-RSA-AES128-SHA256
```

W przypadku Red Hat Enterprise Linux, CentOS i dystrybucji Fedora domyślnie aplikacje platformy .NET są mechanizmami szyfrowania dozwolonymi przez zasady kryptograficzne całego systemu. W tych dystrybucjach Użyj konfiguracji zasad kryptograficznych zamiast *OpenSSL. cnf*.

## <a name="affected-apis"></a>Dotyczy interfejsów API

Nie detectible za pośrednictwem analizy interfejsu API.

<!--

### Affected APIs

- Not detectible via API analysis.

### Category

- Cryptography
- Security

-->
