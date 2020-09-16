---
title: 'Instrukcje: Nawigowanie po relacjach za pomocą operatora nawigowania'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: c51b093c1b74157b957566c4c67712278e50b9e3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546669"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a><span data-ttu-id="aa8bc-102">Instrukcje: Nawigowanie po relacjach za pomocą operatora nawigowania</span><span class="sxs-lookup"><span data-stu-id="aa8bc-102">How to: Navigate Relationships with the Navigate Operator</span></span>
<span data-ttu-id="aa8bc-103">W tym temacie pokazano, jak wykonać polecenie względem modelu koncepcyjnego za pomocą <xref:System.Data.EntityClient.EntityCommand> obiektu i jak pobrać <xref:System.Data.Metadata.Edm.RefType> wyniki przy użyciu <xref:System.Data.EntityClient.EntityDataReader> .</span><span class="sxs-lookup"><span data-stu-id="aa8bc-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="aa8bc-104">Aby uruchomić kod w tym przykładzie</span><span class="sxs-lookup"><span data-stu-id="aa8bc-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="aa8bc-105">Dodaj [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) do projektu i skonfiguruj projekt tak, aby korzystał z Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="aa8bc-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="aa8bc-106">Aby uzyskać więcej informacji, zobacz [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="aa8bc-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="aa8bc-107">Na stronie kodowej aplikacji Dodaj następujące `using` instrukcje ( `Imports` w Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="aa8bc-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="aa8bc-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="aa8bc-108">Example</span></span>  
 <span data-ttu-id="aa8bc-109">Poniższy przykład pokazuje, jak nawigować w relacji [!INCLUDE[esql](../../../../../includes/esql-md.md)] za pomocą operatora [nawigacji](./language-reference/navigate-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="aa8bc-109">The following example shows how to navigate relationships in [!INCLUDE[esql](../../../../../includes/esql-md.md)] by using the [NAVIGATE](./language-reference/navigate-entity-sql.md) operator.</span></span> <span data-ttu-id="aa8bc-110">`Navigate`Operator przyjmuje następujące parametry: wystąpienie jednostki, typ relacji, koniec relacji i początek relacji...</span><span class="sxs-lookup"><span data-stu-id="aa8bc-110">The `Navigate` operator takes the following parameters: an instance of an entity, the relationship type, the end of the relationship, and the beginning of the relationship.</span></span> <span data-ttu-id="aa8bc-111">Opcjonalnie można przekazać tylko wystąpienie jednostki i typ relacji do `Navigate` operatora.</span><span class="sxs-lookup"><span data-stu-id="aa8bc-111">Optionally, you can pass only an instance of an entity and the relationship type to the `Navigate` operator.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="aa8bc-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="aa8bc-112">See also</span></span>

- [<span data-ttu-id="aa8bc-113">Dostawca EntityClient dla programu Entity Framework</span><span class="sxs-lookup"><span data-stu-id="aa8bc-113">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="aa8bc-114">Jednostki języka SQL</span><span class="sxs-lookup"><span data-stu-id="aa8bc-114">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
