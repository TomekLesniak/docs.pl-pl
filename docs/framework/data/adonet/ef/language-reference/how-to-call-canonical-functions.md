---
title: 'Instrukcje: Wywoływanie funkcji kanonicznych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
ms.openlocfilehash: acfbdbaf21fe1d454b68dfef5bf4f88d8020ea65
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204453"
---
# <a name="how-to-call-canonical-functions"></a>Instrukcje: Wywoływanie funkcji kanonicznych

<xref:System.Data.Objects.EntityFunctions>Klasa zawiera metody, które uwidaczniają funkcje kanoniczne do użycia w zapytaniach LINQ to Entities. Aby uzyskać informacje o funkcjach kanonicznych, zobacz [funkcje kanoniczne](canonical-functions.md).  
  
> [!NOTE]
> <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A>Metody i <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> w klasie nie <xref:System.Data.Objects.EntityFunctions> mają odpowiedników funkcji kanonicznych.  
  
 Funkcje kanoniczne, które wykonują obliczenia na zestawie wartości i zwracają pojedynczą wartość (znaną również jako zagregowane funkcje kanoniczne), mogą być wywoływane bezpośrednio. Inne funkcje kanoniczne można wywołać tylko jako część zapytania LINQ to Entities. Aby wywołać funkcję agregującą bezpośrednio, należy przekazać <xref:System.Data.Objects.ObjectQuery%601> do funkcji. Aby uzyskać więcej informacji, zobacz drugi przykład poniżej.  
  
 Niektóre funkcje kanoniczne można wywołać przy użyciu metod środowiska uruchomieniowego języka wspólnego (CLR) w LINQ to Entities zapytaniach. Aby zapoznać się z listą metod CLR, które mapują na funkcje kanoniczne, zobacz [Mapowanie funkcji CLR na funkcję kanoniczną](clr-method-to-canonical-function-mapping.md).  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie jest stosowany [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Przykład wykonuje kwerendę LINQ to Entities, która używa metody, <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> Aby zwrócić wszystkie produkty, dla których różnica między `SellEndDate` i `SellStartDate` jest mniejsza niż 365 dni:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie jest stosowany [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Przykład wywołuje <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> metodę Aggregate bezpośrednio, aby zwracała odchylenie standardowe sum częściowych `SalesOrderHeader` . Należy zauważyć, że do <xref:System.Data.Objects.ObjectQuery%601> funkcji jest przenoszona funkcja, która umożliwia jej wywoływanie bez części zapytania LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Zobacz też

- [Wywoływanie funkcji w zapytaniach składnika LINQ to Entities](calling-functions-in-linq-to-entities-queries.md)
- [Zapytania w składniku LINQ to Entities](queries-in-linq-to-entities.md)
