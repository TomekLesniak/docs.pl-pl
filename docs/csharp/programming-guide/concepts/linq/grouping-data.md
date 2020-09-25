---
title: Grupowanie danych (C#)
description: Grupowanie umieszcza dane w grupach elementów, które współużytkują atrybut. Zapoznaj się ze standardowymi metodami operatorów zapytań w LINQ w języku C#, które grupują elementy danych.
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 584d50fc15dd8b4ce1cfdf4766f3bc8b8383eb12
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202568"
---
# <a name="grouping-data-c"></a>Grupowanie danych (C#)

Grupowanie odwołuje się do operacji umieszczania danych w grupach, tak aby elementy w każdej grupie miały wspólny atrybut.  
  
 Na poniższej ilustracji przedstawiono wyniki grupowania sekwencji znaków. Klucz dla każdej grupy jest znakiem.  
  
 ![Diagram przedstawiający operację grupowania LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 Standardowe metody operatorów zapytań, które grupują elementy danych, są wymienione w poniższej sekcji.  
  
## <a name="methods"></a>Metody  
  
|Nazwa metody|Opis|Składnia wyrażenia zapytania C#|Więcej informacji|  
|-----------------|-----------------|---------------------------------|----------------------|  
|GroupBy|Grupuje elementy, które mają wspólny atrybut. Każda grupa jest reprezentowana przez <xref:System.Linq.IGrouping%602> obiekt.|`group … by`<br /><br /> -lub-<br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|ToLookup|Wstawia elementy do <xref:System.Linq.Lookup%602> (słownik jeden-do-wielu) w oparciu o funkcję selektora kluczy.|Nie dotyczy.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Przykład składni wyrażenia zapytania  

 Poniższy przykład kodu używa `group by` klauzuli do grupowania liczb całkowitych na liście zgodnie z tym, czy są one parzyste czy nieparzyste.  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Linq>
- [Standardowe operatory zapytań — Omówienie (C#)](./standard-query-operators-overview.md)
- [group — Klauzula](../../../language-reference/keywords/group-clause.md)
- [Tworzenie grupy zagnieżdżonej](../../../linq/create-a-nested-group.md)
- [Jak grupować pliki według rozszerzenia (LINQ) (C#)](./how-to-group-files-by-extension-linq.md)
- [Grupowanie wyników zapytania](../../../linq/group-query-results.md)
- [Wykonywanie podzapytania w operacji grupowania](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [Jak podzielić plik na wiele plików przy użyciu grup (LINQ) (C#)](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
