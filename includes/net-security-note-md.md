---
ms.openlocfilehash: 3164233f1ac056de385faa119143d75d3c2dc50c
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224344"
---
> [!CAUTION]
> <span data-ttu-id="26e4d-101">Zabezpieczenia dostępu kodu (CAS) i częściowo zaufany kod</span><span class="sxs-lookup"><span data-stu-id="26e4d-101">Code Access Security (CAS) and Partially Trusted Code</span></span>
>
> <span data-ttu-id="26e4d-102">Platforma .NET Framework zapewnia mechanizm wymuszania różnych poziomów zaufania dla różnego kodu uruchamianego w tej samej aplikacji nazywany zabezpieczeniami dostępu kodu (CAS, Code Access Security).</span><span class="sxs-lookup"><span data-stu-id="26e4d-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>
>
> <span data-ttu-id="26e4d-103">**Urzędy certyfikacji nie są obsługiwane w wersjach .NET Core, .NET 5 i nowszych. Urzędy certyfikacji nie są obsługiwane w wersjach języka C# nowszych niż 7,0.**</span><span class="sxs-lookup"><span data-stu-id="26e4d-103">**CAS is not supported in .NET Core, .NET 5, or later versions. CAS is not supported by versions of C# later than 7.0.**</span></span>
>
> <span data-ttu-id="26e4d-104">Urzędów certyfikacji w .NET Framework nie należy używać jako mechanizmu wymuszania granic zabezpieczeń na podstawie pochodzenia kodu lub innych aspektów tożsamości.</span><span class="sxs-lookup"><span data-stu-id="26e4d-104">CAS in .NET Framework should not be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="26e4d-105">Urzędy certyfikacji i kod Security-Transparent nie są obsługiwane jako granice zabezpieczeń z częściowo zaufanym kodem, szczególnie kod nieznanego źródła.</span><span class="sxs-lookup"><span data-stu-id="26e4d-105">CAS and Security-Transparent Code are not supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="26e4d-106">Odradzamy ładowanie i wykonywanie kodu z nieznanego źródła bez zapewnienia alternatywnych środków bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="26e4d-106">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span> <span data-ttu-id="26e4d-107">.NET Framework nie będzie wystawiał poprawek zabezpieczeń dla wszystkich luk w zabezpieczeniach, które mogą zostać odnalezione w piaskownicy urzędów certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="26e4d-107">.NET Framework will not issue security patches for any elevation-of-privilege exploits that might be discovered against the CAS sandbox.</span></span>
>
> <span data-ttu-id="26e4d-108">Te zasady mają zastosowanie do wszystkich wersji platformy .NET Framework, ale nie mają zastosowania do platformy .NET Framework zawartej w technologii Silverlight.</span><span class="sxs-lookup"><span data-stu-id="26e4d-108">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
