---
ms.openlocfilehash: b7b16e39fa5df9732fa769f2bcd3696dff3b2a49
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497154"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng. VerifyHash teraz zwraca wartość false dla dowolnego błędu weryfikacji

#### <a name="details"></a>Szczegóły

Rozpoczynając od .NET Framework 4.6.2, ta metoda zwraca **wartość false** , jeśli podpis jest nieprawidłowo sformatowany. Teraz zwraca wartość false dla dowolnego błędu weryfikacji. W .NET Framework 4,6 i 4.6.1 Metoda zgłasza, <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> Jeśli podpis jest nieprawidłowo sformatowany.

#### <a name="suggestion"></a>Sugestia

Każdy kod, którego wykonywanie zależy od obsługi <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> należy zamiast tego wykonać, jeśli Walidacja nie powiedzie się, a metoda zwraca **wartość false**.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.6.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
