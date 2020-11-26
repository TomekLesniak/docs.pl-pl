---
title: 'Ograniczenie: układ platformy WPF'
description: Dowiedz się, jak wyeliminować problemy, które wynikają z zmiany w układzie formantów WPF, jak umieszczanie obiektu w pikselach.
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: caed758f6e86a1e2bee255c2f29ca3160b327e17
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244083"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="a8335-103">Ograniczenie: układ platformy WPF</span><span class="sxs-lookup"><span data-stu-id="a8335-103">Mitigation: WPF Layout</span></span>

<span data-ttu-id="a8335-104">Układ formantów WPF może się nieco zmieniać.</span><span class="sxs-lookup"><span data-stu-id="a8335-104">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="a8335-105">Wpływ</span><span class="sxs-lookup"><span data-stu-id="a8335-105">Impact</span></span>  

 <span data-ttu-id="a8335-106">W wyniku tej zmiany:</span><span class="sxs-lookup"><span data-stu-id="a8335-106">As a result of this change:</span></span>  
  
- <span data-ttu-id="a8335-107">Szerokość lub wysokość elementów może wzrosnąć lub zmniejszyć o co najwyżej jeden piksel.</span><span class="sxs-lookup"><span data-stu-id="a8335-107">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="a8335-108">Położenie obiektu może zostać przeniesione o co najwyżej jeden piksel.</span><span class="sxs-lookup"><span data-stu-id="a8335-108">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="a8335-109">Wyśrodkowane elementy mogą być przesunięte w pionie lub w poziomie o co najwyżej jeden piksel.</span><span class="sxs-lookup"><span data-stu-id="a8335-109">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="a8335-110">Domyślnie ten nowy układ jest włączony tylko dla aplikacji przeznaczonych dla .NET Framework 4,6.</span><span class="sxs-lookup"><span data-stu-id="a8335-110">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="a8335-111">Ograniczanie ryzyka</span><span class="sxs-lookup"><span data-stu-id="a8335-111">Mitigation</span></span>  

 <span data-ttu-id="a8335-112">Ponieważ ta modyfikacja ma na celu wyeliminowanie wycinków prawej lub dolnej części formantów WPF o wysokiej rozdzielczościami, aplikacje, które są przeznaczone dla wcześniejszych wersji .NET Framework ale działają na .NET Framework 4,6, mogą przystąpić do tego nowego zachowania, dodając następujący wiersz do `<runtime>` sekcji pliku app.config:</span><span class="sxs-lookup"><span data-stu-id="a8335-112">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="a8335-113">Aplikacje, które są przeznaczone dla .NET Framework 4,6, ale chcą, aby formanty WPF mogły być renderowane przy użyciu poprzedniego algorytmu układu, można to zrobić, dodając następujący wiersz do  `<runtime>` sekcji pliku app.config:</span><span class="sxs-lookup"><span data-stu-id="a8335-113">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8335-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a8335-114">See also</span></span>

- [<span data-ttu-id="a8335-115">Zgodność aplikacji</span><span class="sxs-lookup"><span data-stu-id="a8335-115">Application compatibility</span></span>](application-compatibility.md)
