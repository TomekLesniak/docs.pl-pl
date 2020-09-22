---
title: Nieprawidłowa wartość sumy kontrolnej, cyfry nieszesnastkowe lub nieparzysta liczba cyfr szesnastkowych
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: 612f0b273bacab541e2d634612a104eff1f4a796
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875162"
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="b5515-102">Nieprawidłowa wartość sumy kontrolnej, cyfry nieszesnastkowe lub nieparzysta liczba cyfr szesnastkowych</span><span class="sxs-lookup"><span data-stu-id="b5515-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>

<span data-ttu-id="b5515-103">Wartość sumy kontrolnej zawiera nieprawidłowe cyfry szesnastkowe lub ma nieparzystą liczbę cyfr.</span><span class="sxs-lookup"><span data-stu-id="b5515-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="b5515-104">Gdy ASP.NET generuje plik źródłowy Visual Basic (rozszerzenie. vb), oblicza sumę kontrolną i umieszcza ją w ukrytym pliku źródłowym identyfikowanym przez `#externalchecksum` .</span><span class="sxs-lookup"><span data-stu-id="b5515-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="b5515-105">Istnieje możliwość, że użytkownik generuje plik. vb, aby to zrobić, ale ten proces jest najlepiej używany do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="b5515-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="b5515-106">Domyślnie ten komunikat jest ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="b5515-106">By default, this message is a warning.</span></span> <span data-ttu-id="b5515-107">Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b5515-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="b5515-108">**Identyfikator błędu:** BC42033</span><span class="sxs-lookup"><span data-stu-id="b5515-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b5515-109">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="b5515-109">To correct this error</span></span>  
  
1. <span data-ttu-id="b5515-110">Jeśli ASP.NET generuje plik źródłowy Visual Basic, uruchom ponownie kompilację projektu.</span><span class="sxs-lookup"><span data-stu-id="b5515-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2. <span data-ttu-id="b5515-111">Jeśli to ostrzeżenie będzie nadal występować po ponownym uruchomieniu, zainstaluj ponownie ASP.NET i spróbuj ponownie wykonać kompilację.</span><span class="sxs-lookup"><span data-stu-id="b5515-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3. <span data-ttu-id="b5515-112">Jeśli ostrzeżenie nadal się utrzymuje lub jeśli nie korzystasz z programu ASP.NET, Zbierz informacje o okolicznościach i powiadom usługi pomocy technicznej firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5515-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5515-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b5515-113">See also</span></span>

- [<span data-ttu-id="b5515-114">ASP.NET — Omówienie</span><span class="sxs-lookup"><span data-stu-id="b5515-114">ASP.NET Overview</span></span>](/aspnet/overview)
- [<span data-ttu-id="b5515-115">Porozmawiaj z nami</span><span class="sxs-lookup"><span data-stu-id="b5515-115">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
