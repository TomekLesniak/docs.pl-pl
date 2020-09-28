---
ms.openlocfilehash: 6c2aff4abf558307d599ff7533c82286e037bc71
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406154"
---
### <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a>Interfejsy API System. Security. Cryptography nie są obsługiwane w zestawie webassembly Blazor

<xref:System.Security.Cryptography> Interfejsy API generują <xref:System.PlatformNotSupportedException> w czasie wykonywania w przypadku uruchamiania w przeglądarce.

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET większość <xref:System.Security.Cryptography> interfejsów API nie jest dostępna dla aplikacji Blazor webassembly. Począwszy od platformy .NET 5,0, Blazor aplikacje webassembly są przeznaczone dla całego obszaru interfejsu API platformy .NET 5, ale nie wszystkie interfejsy API programu .NET 5 są obsługiwane z powodu ograniczeń piaskownicy w przeglądarce. W programie .NET 5,0 i nowszych wersjach nieobsługiwane <xref:System.Security.Cryptography> interfejsy API zgłaszają <xref:System.PlatformNotSupportedException> podczas uruchamiania w zestawie webassembly.

> [!TIP]
> [Analizator zgodności platformy](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) będzie flagować wszystkie wywołania interfejsów API, których to dotyczy, podczas tworzenia projektu, który obsługuje platformę przeglądarki. Ten analizator jest domyślnie uruchamiany w programie .NET 5,0 i nowszych aplikacjach.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Firma Microsoft nie może wydać OpenSSL jako zależności w konfiguracji Blazor webassembly. Podjęto próbę obejścia tego problemu, próbując przeprowadzić integrację z `SubtleCrypto` interfejsem API przeglądarki. Niestety, wymagało znaczących zmian interfejsu API, które zostały zbyt trudne do integracji.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC1

#### <a name="recommended-action"></a>Zalecana akcja

W tej chwili nie ma dobrego obejścia do zaproponowania.

#### <a name="category"></a>Kategoria

- ASP.NET Core
- Kryptografia

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Wszystkie <xref:System.Security.Cryptography?displayProperty=fullName> interfejsy API, z wyjątkiem następujących:

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

#### Affected APIs

- `T:System.Security.Cryptography`

-->
