---
ms.openlocfilehash: 7f8f97adcca7e66fa5756212bb977daadd92b8b6
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497125"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>X509Certificate2. ToString (wartość logiczna) nie jest teraz zgłaszana, gdy platforma .NET nie może obsłużyć certyfikatu

#### <a name="details"></a>Szczegóły

W .NET Framework 4.5.2 i starszych wersjach ta metoda zostałaby <code>true</code> zgłoszona, jeśli została przeniesiona do parametru verbose i zainstalowano certyfikaty, które nie były obsługiwane przez .NET Framework. Teraz Metoda zakończy się pomyślnie i zwróci prawidłowy ciąg, który pomija niedostępne fragmenty certyfikatu.

#### <a name="suggestion"></a>Sugestia

Każdy kod w zależności od tego <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> należy zaktualizować, aby oczekiwać, że zwrócony ciąg może wykluczyć niektóre dane certyfikatu (takie jak klucz publiczny, klucz prywatny i rozszerzenia) w niektórych przypadkach, w których interfejs API zostałby wcześniej wygenerowany.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4,6|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)`

-->
