---
ms.openlocfilehash: b7b16e39fa5df9732fa769f2bcd3696dff3b2a49
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497154"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="f8604-101">RSACng. VerifyHash teraz zwraca wartość false dla dowolnego błędu weryfikacji</span><span class="sxs-lookup"><span data-stu-id="f8604-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

#### <a name="details"></a><span data-ttu-id="f8604-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f8604-102">Details</span></span>

<span data-ttu-id="f8604-103">Rozpoczynając od .NET Framework 4.6.2, ta metoda zwraca **wartość false** , jeśli podpis jest nieprawidłowo sformatowany.</span><span class="sxs-lookup"><span data-stu-id="f8604-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="f8604-104">Teraz zwraca wartość false dla dowolnego błędu weryfikacji. W .NET Framework 4,6 i 4.6.1 Metoda zgłasza, <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> Jeśli podpis jest nieprawidłowo sformatowany.</span><span class="sxs-lookup"><span data-stu-id="f8604-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> if the signature itself is badly formatted.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f8604-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="f8604-105">Suggestion</span></span>

<span data-ttu-id="f8604-106">Każdy kod, którego wykonywanie zależy od obsługi <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> należy zamiast tego wykonać, jeśli Walidacja nie powiedzie się, a metoda zwraca **wartość false**.</span><span class="sxs-lookup"><span data-stu-id="f8604-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> should instead execute if validation fails and the method returns **False**.</span></span>

| <span data-ttu-id="f8604-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="f8604-107">Name</span></span>    | <span data-ttu-id="f8604-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="f8604-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f8604-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="f8604-109">Scope</span></span>   |<span data-ttu-id="f8604-110">Mały</span><span class="sxs-lookup"><span data-stu-id="f8604-110">Minor</span></span>|
|<span data-ttu-id="f8604-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="f8604-111">Version</span></span>|<span data-ttu-id="f8604-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="f8604-112">4.6.2</span></span>|
|<span data-ttu-id="f8604-113">Typ</span><span class="sxs-lookup"><span data-stu-id="f8604-113">Type</span></span>|<span data-ttu-id="f8604-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="f8604-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f8604-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f8604-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
