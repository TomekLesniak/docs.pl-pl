---
ms.openlocfilehash: 8b0edd9a49ca431355ab4f57fa041c5d1756d7eb
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855672"
---
> [!CAUTION]
> Zabezpieczenia dostępu kodu (CAS) i częściowo zaufany kod
>
> Platforma .NET Framework zapewnia mechanizm wymuszania różnych poziomów zaufania dla różnego kodu uruchamianego w tej samej aplikacji nazywany zabezpieczeniami dostępu kodu (CAS, Code Access Security).
>
> **Urzędy certyfikacji nie są obsługiwane w wersjach .NET Core, .NET 5 i nowszych. Urzędy certyfikacji nie są obsługiwane w wersjach języka C# nowszych niż 7,0.**
>
> Urzędów certyfikacji w .NET Framework nie należy używać jako mechanizmu wymuszania granic zabezpieczeń na podstawie pochodzenia kodu lub innych aspektów tożsamości. Urzędy certyfikacji i kod przezroczysty zabezpieczeń nie są obsługiwane jako granice zabezpieczeń z częściowo zaufanym kodem, szczególnie kod nieznanego źródła. Odradzamy ładowanie i wykonywanie kodu z nieznanego źródła bez zapewnienia alternatywnych środków bezpieczeństwa.
>
> Te zasady mają zastosowanie do wszystkich wersji platformy .NET Framework, ale nie mają zastosowania do platformy .NET Framework zawartej w technologii Silverlight.
