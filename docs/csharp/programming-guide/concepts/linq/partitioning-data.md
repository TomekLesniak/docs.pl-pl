---
title: Partycjonowanie danych (C#)
description: Dowiedz się, jak podzielić dane na partycje w LINQ. Wyświetl ilustrację przedstawiającą wyniki operacji partycjonowania.
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: 31beacd672addb3eb38ade8f2bf9cfae25f4d27a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176269"
---
# <a name="partitioning-data-c"></a>Partycjonowanie danych (C#)

Partycjonowanie w LINQ odwołuje się do operacji dzielenia sekwencji wejściowej na dwie sekcje, bez konieczności ponownej rozmieszczania elementów, a następnie zwrócenia jednej z sekcji.  
  
 Na poniższej ilustracji przedstawiono wyniki trzech różnych operacji partycjonowania na sekwencji znaków. Pierwsza operacja zwraca trzy pierwsze elementy w sekwencji. Druga operacja pomija pierwsze trzy elementy i zwraca pozostałe elementy. Trzecia operacja pomija pierwsze dwa elementy w sekwencji i zwraca następne trzy elementy.  
  
 ![Ilustracja przedstawiająca trzy operacje partycjonowania LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 Standardowe metody operatorów zapytań, które są sekwencje partycji, są wymienione w poniższej sekcji.  
  
## <a name="operators"></a>Operatory  
  
|Nazwa operatora|Opis|Składnia wyrażenia zapytania C#|Więcej informacji|  
|-------------------|-----------------|---------------------------------|----------------------|  
|Pomiń|Pomija elementy do określonej pozycji w sekwencji.|Nie dotyczy.|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile —|Pomija elementy na podstawie funkcji predykatu, dopóki element nie spełnia warunku.|Nie dotyczy.|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Pobiera elementy do określonej pozycji w sekwencji.|Nie dotyczy.|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile —|Pobiera elementy na podstawie funkcji predykatu, dopóki element nie spełnia warunku.|Nie dotyczy.|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Linq>
- [Standardowe operatory zapytań — Omówienie (C#)](./standard-query-operators-overview.md)
