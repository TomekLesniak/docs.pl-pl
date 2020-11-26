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
# <a name="mitigation-wpf-layout"></a>Ograniczenie: układ platformy WPF

Układ formantów WPF może się nieco zmieniać.  
  
## <a name="impact"></a>Wpływ  

 W wyniku tej zmiany:  
  
- Szerokość lub wysokość elementów może wzrosnąć lub zmniejszyć o co najwyżej jeden piksel.  
  
- Położenie obiektu może zostać przeniesione o co najwyżej jeden piksel.  
  
- Wyśrodkowane elementy mogą być przesunięte w pionie lub w poziomie o co najwyżej jeden piksel.  
  
 Domyślnie ten nowy układ jest włączony tylko dla aplikacji przeznaczonych dla .NET Framework 4,6.  
  
## <a name="mitigation"></a>Ograniczanie ryzyka  

 Ponieważ ta modyfikacja ma na celu wyeliminowanie wycinków prawej lub dolnej części formantów WPF o wysokiej rozdzielczościami, aplikacje, które są przeznaczone dla wcześniejszych wersji .NET Framework ale działają na .NET Framework 4,6, mogą przystąpić do tego nowego zachowania, dodając następujący wiersz do `<runtime>` sekcji pliku app.config:  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 Aplikacje, które są przeznaczone dla .NET Framework 4,6, ale chcą, aby formanty WPF mogły być renderowane przy użyciu poprzedniego algorytmu układu, można to zrobić, dodając następujący wiersz do  `<runtime>` sekcji pliku app.config:  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a>Zobacz też

- [Zgodność aplikacji](application-compatibility.md)
