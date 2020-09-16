---
title: 'Instrukcje: Tworzenie parametrów połączenia EntityConnection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: 86ba3956797ff603dd944bfc8df1990df8f23001
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556437"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a><span data-ttu-id="e02d7-102">Instrukcje: Tworzenie parametrów połączenia EntityConnection</span><span class="sxs-lookup"><span data-stu-id="e02d7-102">How to: Build an EntityConnection Connection String</span></span>
<span data-ttu-id="e02d7-103">Ten temat zawiera przykład sposobu tworzenia programu <xref:System.Data.EntityClient.EntityConnection> .</span><span class="sxs-lookup"><span data-stu-id="e02d7-103">This topic provides an example of how to build an <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="e02d7-104">Aby uruchomić kod w tym przykładzie</span><span class="sxs-lookup"><span data-stu-id="e02d7-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="e02d7-105">Dodaj [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) do projektu i skonfiguruj projekt tak, aby korzystał z Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="e02d7-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="e02d7-106">Aby uzyskać więcej informacji, zobacz [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e02d7-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="e02d7-107">Na stronie kodowej aplikacji Dodaj następujące `using` instrukcje ( `Imports` w Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="e02d7-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="e02d7-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="e02d7-108">Example</span></span>  
 <span data-ttu-id="e02d7-109">Poniższy przykład inicjuje <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> dla podstawowego dostawcy, inicjuje <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> obiekt i przekazuje ten obiekt do konstruktora obiektu <xref:System.Data.EntityClient.EntityConnection> .</span><span class="sxs-lookup"><span data-stu-id="e02d7-109">The following example initializes the <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> for the underlying provider, then initializes the <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> object and passes this object to the constructor of the <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="e02d7-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e02d7-110">See also</span></span>

- <span data-ttu-id="e02d7-111">[Instrukcje: korzystanie z EntityConnection z kontekstem obiektu](/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e02d7-111">[How to: Use EntityConnection with an Object Context](/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span></span>
- [<span data-ttu-id="e02d7-112">Dostawca EntityClient dla programu Entity Framework</span><span class="sxs-lookup"><span data-stu-id="e02d7-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
