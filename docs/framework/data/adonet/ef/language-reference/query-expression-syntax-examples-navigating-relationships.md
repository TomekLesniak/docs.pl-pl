---
title: Przykłady składni wyrażeń zapytania, nawigowanie po relacjach
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0d4a7f41-c758-4059-8f83-d2e9c2745593
ms.openlocfilehash: c09a0458f5b0b7d313da3379b5dda9b969eaf7e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156800"
---
# <a name="query-expression-syntax-examples-navigating-relationships"></a>Przykłady składni wyrażeń zapytania, nawigowanie po relacjach

Właściwości nawigacji w Entity Framework są właściwościami skrótu używanymi do lokalizowania jednostek na końcu skojarzenia. Właściwości nawigacji umożliwiają użytkownikowi nawigowanie z jednej jednostki do innej lub z jednej jednostki do powiązanych jednostek za pośrednictwem zestawu skojarzeń. Ten temat zawiera przykłady w składni wyrażenia zapytania dotyczące sposobu nawigowania po relacjach przy użyciu właściwości nawigacji w LINQ to Entities zapytaniach.  
  
 Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.  
  
 Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie zastosowano <xref:System.Linq.Queryable.Select%2A> metodę, aby pobrać wszystkie identyfikatory kontaktów i sumę łącznej liczby należnych dla każdego kontaktu, którego nazwisko to "Zhou". `Contact.SalesOrderHeader`Właściwość nawigacji służy do pobierania kolekcji `SalesOrderHeader` obiektów dla każdego kontaktu. `Sum`Metoda używa `Contact.SalesOrderHeader` właściwości nawigacji, aby zsumować sumę ze wszystkich zamówień dla każdego kontaktu.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pobiera wszystkie zamówienia kontaktów, których nazwisko to "Zhou". `Contact.SalesOrderHeader`Właściwość nawigacji służy do pobierania kolekcji `SalesOrderHeader` obiektów dla każdego kontaktu. Nazwa i zamówienia kontaktu są zwracane w typie anonimowym.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3)]  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie zastosowano `SalesOrderHeader.Address` `SalesOrderHeader.Contact` właściwości i nawigacji, aby uzyskać kolekcję `Address` `Contact` obiektów i skojarzonych z nimi kolejności. Nazwisko osoby kontaktowej, adres ulicy, numer zamówienia sprzedaży oraz suma należna za każde zamówienie do miasta Seattle są zwracane w typie anonimowym.  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships)]  
  
### <a name="example"></a>Przykład  

 W poniższym przykładzie użyto `Where` metody, aby znaleźć zamówienia, które zostały wprowadzone po 1 grudnia 2003, a następnie użyć `order.SalesOrderDetail` właściwości nawigacji, aby uzyskać szczegółowe informacje dotyczące poszczególnych zamówień.  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a>Zobacz też

- [Zapytania w składniku LINQ to Entities](queries-in-linq-to-entities.md)
