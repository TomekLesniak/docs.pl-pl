---
title: System.Math, metody
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: e91c8ea95d21288ad2577f1550333febd448766d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158204"
---
# <a name="systemmath-methods"></a>System.Math, metody

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Program nie obsługuje następujących <xref:System.Math> metod.  
  
- <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>Różnice od platformy .NET  

 .NET Framework ma inną semantykę zaokrąglania z SQL Server. <xref:System.Math.Round%2A>Metoda w .NET Framework wykonuje *Zaokrąglenie w banku*, gdzie liczby kończące się w .5 zaokrąglają do najbliższej parzystej cyfry zamiast do kolejnej wyższej cyfry. Na przykład 2,5 zaokrągla do 2, a 3,5 zaokrągla do 4. (Ta technika pozwala uniknąć regularnego obciążenia w kierunku wyższych wartości w dużych transakcjach danych).  
  
 W języku SQL `ROUND` Funkcja zamiast tego jest zawsze zaokrąglana w kierunku od zera. W związku z tym 2,5 Zaokrąglaj do 3, kontrastowo z zaokrągleniem do 2 w .NET Framework.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] przekazuje do `ROUND` semantyki SQL i nie próbuje zaimplementować zaokrąglenia banku.  
  
## <a name="see-also"></a>Zobacz też

- [Typy danych i funkcje](data-types-and-functions.md)
