---
title: 'Instrukcje: Wykonywanie zapytania SQL do sparametryzowanej jednostki przy użyciu EntityCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: 24b24e4c35c85edb1f960ae18a58cbc5893690d0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536226"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a><span data-ttu-id="fb4ca-102">Instrukcje: Wykonywanie zapytania SQL do sparametryzowanej jednostki przy użyciu EntityCommand</span><span class="sxs-lookup"><span data-stu-id="fb4ca-102">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>
<span data-ttu-id="fb4ca-103">W tym temacie pokazano, jak wykonać [!INCLUDE[esql](../../../../../includes/esql-md.md)] zapytanie, które zawiera parametry za pomocą <xref:System.Data.EntityClient.EntityCommand> obiektu.</span><span class="sxs-lookup"><span data-stu-id="fb4ca-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that has parameters by using an <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="fb4ca-104">Aby uruchomić kod w tym przykładzie</span><span class="sxs-lookup"><span data-stu-id="fb4ca-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="fb4ca-105">Dodaj [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) do projektu i skonfiguruj projekt tak, aby korzystał z Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="fb4ca-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="fb4ca-106">Aby uzyskać więcej informacji, zobacz [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="fb4ca-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="fb4ca-107">Na stronie kodowej aplikacji Dodaj następujące `using` instrukcje ( `Imports` w Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="fb4ca-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="fb4ca-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="fb4ca-108">Example</span></span>  
 <span data-ttu-id="fb4ca-109">Poniższy przykład pokazuje, jak utworzyć ciąg zapytania z dwoma parametrami.</span><span class="sxs-lookup"><span data-stu-id="fb4ca-109">The following example shows how to construct a query string with two parameters.</span></span> <span data-ttu-id="fb4ca-110">Następnie tworzy <xref:System.Data.EntityClient.EntityCommand> , dodaje dwa parametry do <xref:System.Data.EntityClient.EntityParameter> kolekcji <xref:System.Data.EntityClient.EntityCommand> i wykonuje iterację kolekcji `Contact` elementów.</span><span class="sxs-lookup"><span data-stu-id="fb4ca-110">It then creates an <xref:System.Data.EntityClient.EntityCommand>, adds two parameters to the <xref:System.Data.EntityClient.EntityParameter> collection of that <xref:System.Data.EntityClient.EntityCommand>, and iterates through the collection of `Contact` items.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="fb4ca-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fb4ca-111">See also</span></span>

- <span data-ttu-id="fb4ca-112">[Instrukcje: wykonywanie zapytania parametrycznego](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fb4ca-112">[How to: Execute a Parameterized Query](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>
- [<span data-ttu-id="fb4ca-113">Jednostki języka SQL</span><span class="sxs-lookup"><span data-stu-id="fb4ca-113">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
