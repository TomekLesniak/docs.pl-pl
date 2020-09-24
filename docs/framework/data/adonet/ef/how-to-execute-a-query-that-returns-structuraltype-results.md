---
title: 'Instrukcje: Wykonywanie zapytania, które zwraca wyniki StructuralType'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2314f2a2-b1c3-40c4-95bb-cdf9b21a7b53
ms.openlocfilehash: 4b3a63cb23851c6545f330ebd2371e1a34ff13e8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198317"
---
# <a name="how-to-execute-a-query-that-returns-structuraltype-results"></a><span data-ttu-id="d5c44-102">Instrukcje: Wykonywanie zapytania, które zwraca wyniki StructuralType</span><span class="sxs-lookup"><span data-stu-id="d5c44-102">How to: Execute a Query that Returns StructuralType Results</span></span>

<span data-ttu-id="d5c44-103">W tym temacie pokazano, jak wykonać polecenie względem modelu koncepcyjnego za pomocą <xref:System.Data.EntityClient.EntityCommand> obiektu i jak pobrać <xref:System.Data.Metadata.Edm.StructuralType> wyniki przy użyciu <xref:System.Data.EntityClient.EntityDataReader> .</span><span class="sxs-lookup"><span data-stu-id="d5c44-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.StructuralType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="d5c44-104"><xref:System.Data.Metadata.Edm.EntityType> <xref:System.Data.Metadata.Edm.RowType> Klasy i są <xref:System.Data.Metadata.Edm.ComplexType> pochodne od <xref:System.Data.Metadata.Edm.StructuralType> klasy.</span><span class="sxs-lookup"><span data-stu-id="d5c44-104">The <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.RowType> and <xref:System.Data.Metadata.Edm.ComplexType> classes derive from the <xref:System.Data.Metadata.Edm.StructuralType> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="d5c44-105">Aby uruchomić kod w tym przykładzie</span><span class="sxs-lookup"><span data-stu-id="d5c44-105">To run the code in this example</span></span>  
  
1. <span data-ttu-id="d5c44-106">Dodaj [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) do projektu i skonfiguruj projekt tak, aby korzystał z Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d5c44-106">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="d5c44-107">Aby uzyskać więcej informacji, zobacz [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d5c44-107">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="d5c44-108">Na stronie kodowej aplikacji Dodaj następujące `using` instrukcje ( `Imports` w Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="d5c44-108">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="d5c44-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="d5c44-109">Example</span></span>  

 <span data-ttu-id="d5c44-110">Ten przykład wykonuje zapytanie zwracające <xref:System.Data.Metadata.Edm.EntityType> wyniki.</span><span class="sxs-lookup"><span data-stu-id="d5c44-110">This example executes a query that returns <xref:System.Data.Metadata.Edm.EntityType> results.</span></span> <span data-ttu-id="d5c44-111">W przypadku przekazania następującego zapytania jako argumentu do `ExecuteStructuralTypeQuery` funkcji, funkcja wyświetla szczegółowe informacje o `Products` :</span><span class="sxs-lookup"><span data-stu-id="d5c44-111">If you pass the following query as an argument to the `ExecuteStructuralTypeQuery` function, the function displays details about the `Products`:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SelectProduct](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#selectproduct)]  
  
 <span data-ttu-id="d5c44-112">W przypadku przekazania sparametryzowanych zapytań, takich jak następujące, Dodaj <xref:System.Data.EntityClient.EntityParameter> obiekty do <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> właściwości <xref:System.Data.EntityClient.EntityCommand> obiektu.</span><span class="sxs-lookup"><span data-stu-id="d5c44-112">If you pass a parameterized query, like the following, add the <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlstructuraltypes)]
 [!code-vb[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlstructuraltypes)]  
  
## <a name="see-also"></a><span data-ttu-id="d5c44-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d5c44-113">See also</span></span>

- [<span data-ttu-id="d5c44-114">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="d5c44-114">Entity SQL Reference</span></span>](./language-reference/entity-sql-reference.md)
- [<span data-ttu-id="d5c44-115">Dostawca EntityClient dla programu Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d5c44-115">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
