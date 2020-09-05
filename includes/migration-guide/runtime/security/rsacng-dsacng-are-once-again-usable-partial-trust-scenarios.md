---
ms.openlocfilehash: 4788f5b80306116e63ee56584d65b862ce0606ee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496626"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a><span data-ttu-id="2ea34-101">RSACng i DSACng są ponownie nadające się do użytku w scenariuszach częściowej relacji zaufania</span><span class="sxs-lookup"><span data-stu-id="2ea34-101">RSACng and DSACng are once again usable in Partial Trust scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="2ea34-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="2ea34-102">Details</span></span>

<span data-ttu-id="2ea34-103">CngLightup (używany w kilku interfejsów API kryptografii wyższego poziomu, takich jak <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> ), a <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> w niektórych przypadkach polega na pełnym zaufaniu.</span><span class="sxs-lookup"><span data-stu-id="2ea34-103">CngLightup (used in several higher-level crypto apis, such as <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) and <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> in some cases rely on full trust.</span></span> <span data-ttu-id="2ea34-104">Obejmują one polecenie P/Invoke bez potwierdzeń <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> i ścieżki kodu, <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> w których istnieją żądania dotyczące uprawnień <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2ea34-104">These include P/Invokes without asserting <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> permissions, and code paths where <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> has permission demands for <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ea34-105">Począwszy od .NET Framework 4.6.2, CngLightup został użyty do przełączenia do <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> wszędzie tam, gdzie to możliwe.</span><span class="sxs-lookup"><span data-stu-id="2ea34-105">Starting with the .NET Framework 4.6.2, CngLightup was used to switch to <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> wherever possible.</span></span> <span data-ttu-id="2ea34-106">W związku z tym częściowo zaufane aplikacje, które pomyślnie używały, <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> zaczęły kończyć się niepowodzeniem i generować <xref:System.Security.SecurityException> wyjątki. Ta zmiana powoduje dodanie wymaganych potwierdzeń, aby wszystkie funkcje korzystające z CngLightup miały wymagane uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="2ea34-106">As a result, partial trust apps that successfully used <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> began to fail and throw <xref:System.Security.SecurityException> exceptions.This change adds the required asserts so that all functions using CngLightup have the required permissions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2ea34-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="2ea34-107">Suggestion</span></span>

<span data-ttu-id="2ea34-108">Jeśli ta zmiana w .NET Framework 4.6.2 ma negatywny wpływ na aplikacje częściowej relacji zaufania, przeprowadź uaktualnienie do .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="2ea34-108">If this change in the .NET Framework 4.6.2 has negatively impacted your partial trust apps, upgrade to the .NET Framework 4.7.1.</span></span>

| <span data-ttu-id="2ea34-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="2ea34-109">Name</span></span>    | <span data-ttu-id="2ea34-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="2ea34-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2ea34-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="2ea34-111">Scope</span></span>   |<span data-ttu-id="2ea34-112">Edge</span><span class="sxs-lookup"><span data-stu-id="2ea34-112">Edge</span></span>|
|<span data-ttu-id="2ea34-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="2ea34-113">Version</span></span>|<span data-ttu-id="2ea34-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="2ea34-114">4.6.2</span></span>|
|<span data-ttu-id="2ea34-115">Typ</span><span class="sxs-lookup"><span data-stu-id="2ea34-115">Type</span></span>|<span data-ttu-id="2ea34-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="2ea34-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2ea34-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="2ea34-117">Affected APIs</span></span>

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
