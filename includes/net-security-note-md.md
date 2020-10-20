---
ms.openlocfilehash: 3164233f1ac056de385faa119143d75d3c2dc50c
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224344"
---
> [!CAUTION]
> Zabezpieczenia dostępu kodu (CAS) i częściowo zaufany kod
>
> Platforma .NET Framework zapewnia mechanizm wymuszania różnych poziomów zaufania dla różnego kodu uruchamianego w tej samej aplikacji nazywany zabezpieczeniami dostępu kodu (CAS, Code Access Security).
>
> **Urzędy certyfikacji nie są obsługiwane w wersjach .NET Core, .NET 5 i nowszych. Urzędy certyfikacji nie są obsługiwane w wersjach języka C# nowszych niż 7,0.**
>
> Urzędów certyfikacji w .NET Framework nie należy używać jako mechanizmu wymuszania granic zabezpieczeń na podstawie pochodzenia kodu lub innych aspektów tożsamości. Urzędy certyfikacji i kod Security-Transparent nie są obsługiwane jako granice zabezpieczeń z częściowo zaufanym kodem, szczególnie kod nieznanego źródła. Odradzamy ładowanie i wykonywanie kodu z nieznanego źródła bez zapewnienia alternatywnych środków bezpieczeństwa. .NET Framework nie będzie wystawiał poprawek zabezpieczeń dla wszystkich luk w zabezpieczeniach, które mogą zostać odnalezione w piaskownicy urzędów certyfikacji.
>
> Te zasady mają zastosowanie do wszystkich wersji platformy .NET Framework, ale nie mają zastosowania do platformy .NET Framework zawartej w technologii Silverlight.
