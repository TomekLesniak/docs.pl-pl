---
ms.openlocfilehash: 8b0edd9a49ca431355ab4f57fa041c5d1756d7eb
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855672"
---
> [!CAUTION]
> <span data-ttu-id="feb06-101">Zabezpieczenia dostępu kodu (CAS) i częściowo zaufany kod</span><span class="sxs-lookup"><span data-stu-id="feb06-101">Code Access Security (CAS) and Partially Trusted Code</span></span>
>
> <span data-ttu-id="feb06-102">Platforma .NET Framework zapewnia mechanizm wymuszania różnych poziomów zaufania dla różnego kodu uruchamianego w tej samej aplikacji nazywany zabezpieczeniami dostępu kodu (CAS, Code Access Security).</span><span class="sxs-lookup"><span data-stu-id="feb06-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>
>
> <span data-ttu-id="feb06-103">**Urzędy certyfikacji nie są obsługiwane w wersjach .NET Core, .NET 5 i nowszych. Urzędy certyfikacji nie są obsługiwane w wersjach języka C# nowszych niż 7,0.**</span><span class="sxs-lookup"><span data-stu-id="feb06-103">**CAS is not supported in .NET Core, .NET 5, or later versions. CAS is not supported by versions of C# later than 7.0.**</span></span>
>
> <span data-ttu-id="feb06-104">Urzędów certyfikacji w .NET Framework nie należy używać jako mechanizmu wymuszania granic zabezpieczeń na podstawie pochodzenia kodu lub innych aspektów tożsamości.</span><span class="sxs-lookup"><span data-stu-id="feb06-104">CAS in .NET Framework should not be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="feb06-105">Urzędy certyfikacji i kod przezroczysty zabezpieczeń nie są obsługiwane jako granice zabezpieczeń z częściowo zaufanym kodem, szczególnie kod nieznanego źródła.</span><span class="sxs-lookup"><span data-stu-id="feb06-105">CAS and Security-Transparent Code are not supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="feb06-106">Odradzamy ładowanie i wykonywanie kodu z nieznanego źródła bez zapewnienia alternatywnych środków bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="feb06-106">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>
>
> <span data-ttu-id="feb06-107">Te zasady mają zastosowanie do wszystkich wersji platformy .NET Framework, ale nie mają zastosowania do platformy .NET Framework zawartej w technologii Silverlight.</span><span class="sxs-lookup"><span data-stu-id="feb06-107">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
