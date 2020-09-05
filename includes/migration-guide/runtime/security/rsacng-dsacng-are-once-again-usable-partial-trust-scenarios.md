---
ms.openlocfilehash: 4788f5b80306116e63ee56584d65b862ce0606ee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496626"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a>RSACng i DSACng są ponownie nadające się do użytku w scenariuszach częściowej relacji zaufania

#### <a name="details"></a>Szczegóły

CngLightup (używany w kilku interfejsów API kryptografii wyższego poziomu, takich jak <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> ), a <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> w niektórych przypadkach polega na pełnym zaufaniu. Obejmują one polecenie P/Invoke bez potwierdzeń <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> i ścieżki kodu, <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> w których istnieją żądania dotyczące uprawnień <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> . Począwszy od .NET Framework 4.6.2, CngLightup został użyty do przełączenia do <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> wszędzie tam, gdzie to możliwe. W związku z tym częściowo zaufane aplikacje, które pomyślnie używały, <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> zaczęły kończyć się niepowodzeniem i generować <xref:System.Security.SecurityException> wyjątki. Ta zmiana powoduje dodanie wymaganych potwierdzeń, aby wszystkie funkcje korzystające z CngLightup miały wymagane uprawnienia.

#### <a name="suggestion"></a>Sugestia

Jeśli ta zmiana w .NET Framework 4.6.2 ma negatywny wpływ na aplikacje częściowej relacji zaufania, przeprowadź uaktualnienie do .NET Framework 4.7.1.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.6.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.DSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.DSACng.Key`
- `P:System.Security.Cryptography.DSACng.LegalKeySizes`
- `M:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])`
- `M:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])`
- `M:System.Security.Cryptography.RSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.RSACng.Key`
- `M:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)`
- `M:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
