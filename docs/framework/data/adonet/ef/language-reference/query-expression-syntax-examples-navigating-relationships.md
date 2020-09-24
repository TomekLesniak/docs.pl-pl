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
# <a name="query-expression-syntax-examples-navigating-relationships"></a><span data-ttu-id="129d4-102">Przykłady składni wyrażeń zapytania, nawigowanie po relacjach</span><span class="sxs-lookup"><span data-stu-id="129d4-102">Query Expression Syntax Examples: Navigating Relationships</span></span>

<span data-ttu-id="129d4-103">Właściwości nawigacji w Entity Framework są właściwościami skrótu używanymi do lokalizowania jednostek na końcu skojarzenia.</span><span class="sxs-lookup"><span data-stu-id="129d4-103">Navigation properties in the Entity Framework are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="129d4-104">Właściwości nawigacji umożliwiają użytkownikowi nawigowanie z jednej jednostki do innej lub z jednej jednostki do powiązanych jednostek za pośrednictwem zestawu skojarzeń.</span><span class="sxs-lookup"><span data-stu-id="129d4-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="129d4-105">Ten temat zawiera przykłady w składni wyrażenia zapytania dotyczące sposobu nawigowania po relacjach przy użyciu właściwości nawigacji w LINQ to Entities zapytaniach.</span><span class="sxs-lookup"><span data-stu-id="129d4-105">This topic provides examples in query expression syntax of how to navigate relationships through navigation properties in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="129d4-106">Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="129d4-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="129d4-107">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="129d4-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="129d4-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="129d4-108">Example</span></span>  

 <span data-ttu-id="129d4-109">W poniższym przykładzie zastosowano <xref:System.Linq.Queryable.Select%2A> metodę, aby pobrać wszystkie identyfikatory kontaktów i sumę łącznej liczby należnych dla każdego kontaktu, którego nazwisko to "Zhou".</span><span class="sxs-lookup"><span data-stu-id="129d4-109">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="129d4-110">`Contact.SalesOrderHeader`Właściwość nawigacji służy do pobierania kolekcji `SalesOrderHeader` obiektów dla każdego kontaktu.</span><span class="sxs-lookup"><span data-stu-id="129d4-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="129d4-111">`Sum`Metoda używa `Contact.SalesOrderHeader` właściwości nawigacji, aby zsumować sumę ze wszystkich zamówień dla każdego kontaktu.</span><span class="sxs-lookup"><span data-stu-id="129d4-111">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2)]  
  
## <a name="example"></a><span data-ttu-id="129d4-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="129d4-112">Example</span></span>  

 <span data-ttu-id="129d4-113">Poniższy przykład pobiera wszystkie zamówienia kontaktów, których nazwisko to "Zhou".</span><span class="sxs-lookup"><span data-stu-id="129d4-113">The following example gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="129d4-114">`Contact.SalesOrderHeader`Właściwość nawigacji służy do pobierania kolekcji `SalesOrderHeader` obiektów dla każdego kontaktu.</span><span class="sxs-lookup"><span data-stu-id="129d4-114">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="129d4-115">Nazwa i zamówienia kontaktu są zwracane w typie anonimowym.</span><span class="sxs-lookup"><span data-stu-id="129d4-115">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3)]  
  
## <a name="example"></a><span data-ttu-id="129d4-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="129d4-116">Example</span></span>  

 <span data-ttu-id="129d4-117">W poniższym przykładzie zastosowano `SalesOrderHeader.Address` `SalesOrderHeader.Contact` właściwości i nawigacji, aby uzyskać kolekcję `Address` `Contact` obiektów i skojarzonych z nimi kolejności.</span><span class="sxs-lookup"><span data-stu-id="129d4-117">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="129d4-118">Nazwisko osoby kontaktowej, adres ulicy, numer zamówienia sprzedaży oraz suma należna za każde zamówienie do miasta Seattle są zwracane w typie anonimowym.</span><span class="sxs-lookup"><span data-stu-id="129d4-118">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships)]  
  
### <a name="example"></a><span data-ttu-id="129d4-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="129d4-119">Example</span></span>  

 <span data-ttu-id="129d4-120">W poniższym przykładzie użyto `Where` metody, aby znaleźć zamówienia, które zostały wprowadzone po 1 grudnia 2003, a następnie użyć `order.SalesOrderDetail` właściwości nawigacji, aby uzyskać szczegółowe informacje dotyczące poszczególnych zamówień.</span><span class="sxs-lookup"><span data-stu-id="129d4-120">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="129d4-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="129d4-121">See also</span></span>

- [<span data-ttu-id="129d4-122">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="129d4-122">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
