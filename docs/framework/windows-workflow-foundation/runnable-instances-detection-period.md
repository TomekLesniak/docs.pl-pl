---
title: Okres wykrywania wystąpień możliwych do uruchomienia
ms.date: 03/30/2017
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
ms.openlocfilehash: aefde2726bb2ccc15f9e68009e5e141602b13b10
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245773"
---
# <a name="runnable-instances-detection-period"></a>Okres wykrywania wystąpień możliwych do uruchomienia

Magazyn wystąpień przepływu pracy SQL uruchamia zadanie wewnętrzne, które okresowo wznawia i wykrywa wystąpienia możliwy do uruchomienia lub aktywowalnej w bazie danych trwałości. Właściwość **okres wykrywania wystąpień możliwy do uruchomienia** magazynu wystąpień przepływu pracy SQL określa czas, po upływie którego magazyn wystąpień przepływu pracy SQL uruchamia zadanie wykrywania w celu wykrycia dowolnego wystąpienia przepływu pracy możliwy do uruchomienia lub aktywowalnej w bazie danych trwałości po poprzednim cyklu wykrywania.  
  
 Ustawienie krótszego interwału dla tej właściwości skraca czas między upływem czasu wygaśnięcia czasomierza skojarzonego z wystąpieniem przepływu pracy oraz sygnalizowaniem zdarzenia i następnym załadowaniem wystąpienia. Jednak zwiększa to również obciążenie przetwarzaniem na hoście i może nie być pożądane w scenariuszach, w których trwałe czasomierze i/lub awarie hosta są rzadkie. Typ właściwości to TimeSpan, a wartość właściwości jest zgodna z formatem: gg: mm: SS. Minimalna wartość tej właściwości to 00:00:01. Wartość domyślna właściwości to 00:00:05.  
  
 Aby uzyskać więcej informacji na temat wykrywania i aktywowania wystąpień przepływu pracy możliwy do uruchomienia i aktywowalnej, zobacz [Aktywacja wystąpienia](instance-activation.md).
