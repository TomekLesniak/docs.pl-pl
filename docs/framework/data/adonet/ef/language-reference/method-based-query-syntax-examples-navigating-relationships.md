---
title: Przykłady składni zapytania oparte na metodzie, nawigowanie po relacjach
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a0bfa4b1-99e5-4dd1-9912-4b825a9dc25c
ms.openlocfilehash: bb40d10165592b25cc6afc1eac799a05b4504e8d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191973"
---
# <a name="method-based-query-syntax-examples-navigating-relationships"></a>Przykłady składni zapytania oparte na metodzie, nawigowanie po relacjach

Właściwości nawigacji w Entity Framework są właściwościami skrótu używanymi do lokalizowania jednostek na końcu skojarzenia. Właściwości nawigacji umożliwiają użytkownikowi nawigowanie z jednej jednostki do innej lub z jednej jednostki do powiązanych jednostek za pośrednictwem zestawu skojarzeń. Ten temat zawiera przykłady w składni zapytania opartej na metodzie, w jaki sposób nawigować po relacjach za pomocą właściwości nawigacji w zapytaniach LINQ to Entities.  
  
 Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.  
  
 Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład w składni zapytania opartej na metodzie używa <xref:System.Linq.Queryable.SelectMany%2A> metody, aby uzyskać wszystkie zamówienia kontaktów, których nazwisko to "Zhou". `Contact.SalesOrderHeader`Właściwość nawigacji służy do pobierania kolekcji `SalesOrderHeader` obiektów dla każdego kontaktu.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders_mq)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład w składni zapytania opartej na metodzie używa <xref:System.Linq.Queryable.Select%2A> metody, aby uzyskać wszystkie identyfikatory kontaktów i sumę łącznej liczby należnych dla każdego kontaktu, którego nazwisko to "Zhou". `Contact.SalesOrderHeader`Właściwość nawigacji służy do pobierania kolekcji `SalesOrderHeader` obiektów dla każdego kontaktu. `Sum`Metoda używa `Contact.SalesOrderHeader` właściwości nawigacji, aby zsumować sumę ze wszystkich zamówień dla każdego kontaktu.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2_mq)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład w składni zapytania opartej na metodzie pobiera wszystkie zamówienia kontaktów, których nazwisko to "Zhou". `Contact.SalesOrderHeader`Właściwość nawigacji służy do pobierania kolekcji `SalesOrderHeader` obiektów dla każdego kontaktu. Nazwa i zamówienia kontaktu są zwracane w typie anonimowym.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3_mq)]  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie zastosowano `SalesOrderHeader.Address` `SalesOrderHeader.Contact` właściwości nawigacji i w celu uzyskania kolekcji `Address` i `Contact` obiektów skojarzonych z poszczególnymi kolejnością. Nazwisko osoby kontaktowej, adres ulicy, numer zamówienia sprzedaży oraz suma należna za każde zamówienie do miasta Seattle są zwracane w typie anonimowym.  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships_mq)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships_mq)]  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie użyto `Where` metody, aby znaleźć zamówienia, które zostały wprowadzone po 1 grudnia 2003, a następnie użyć `order.SalesOrderDetail` właściwości nawigacji, aby uzyskać szczegółowe informacje dotyczące poszczególnych zamówień.  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a>Zobacz też

- [Relacje, właściwości nawigacji i klucze obce](/ef/ef6/fundamentals/relationships)
- [Zapytania w składniku LINQ to Entities](queries-in-linq-to-entities.md)
