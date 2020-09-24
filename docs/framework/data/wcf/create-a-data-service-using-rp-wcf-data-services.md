---
title: 'Instrukcje: Tworzenie usługi danych przy użyciu dostawcy odbicia (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 6bab9d9be484cf90cb85df63a1b237b5cc39a5e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152770"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="9d90a-102">Instrukcje: Tworzenie usługi danych przy użyciu dostawcy odbicia (Usługi danych programu WCF)</span><span class="sxs-lookup"><span data-stu-id="9d90a-102">How to: Create a Data Service Using the Reflection Provider (WCF Data Services)</span></span>

<span data-ttu-id="9d90a-103">Usługi danych programu WCF umożliwia zdefiniowanie modelu danych, który jest oparty na dowolnej klasie, tak długo, jak te klasy są udostępniane jako obiekty, które implementują <xref:System.Linq.IQueryable%601> interfejs.</span><span class="sxs-lookup"><span data-stu-id="9d90a-103">WCF Data Services enables you to define a data model that is based on arbitrary classes as long as those classes are exposed as objects that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="9d90a-104">Aby uzyskać więcej informacji, zobacz [Data Services Providers](data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9d90a-104">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d90a-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="9d90a-105">Example</span></span>  

 <span data-ttu-id="9d90a-106">W poniższym przykładzie zdefiniowano model danych, który zawiera `Orders` i `Items` .</span><span class="sxs-lookup"><span data-stu-id="9d90a-106">The following example defines a data model that includes `Orders` and `Items`.</span></span> <span data-ttu-id="9d90a-107">Klasa kontenera jednostek `OrderItemData` ma dwie metody publiczne, które zwracają <xref:System.Linq.IQueryable%601> interfejsy.</span><span class="sxs-lookup"><span data-stu-id="9d90a-107">The entity container class `OrderItemData` has two public methods that return <xref:System.Linq.IQueryable%601> interfaces.</span></span> <span data-ttu-id="9d90a-108">Te interfejsy są zestawami jednostek `Orders` `Items` typów jednostek i.</span><span class="sxs-lookup"><span data-stu-id="9d90a-108">These interfaces are the entity sets of the `Orders` and `Items` entity types.</span></span> <span data-ttu-id="9d90a-109">`Order`Może zawierać wiele `Items` , więc `Orders` Typ jednostki ma `Items` Właściwość nawigacji, która zwraca kolekcję `Items` obiektów.</span><span class="sxs-lookup"><span data-stu-id="9d90a-109">An `Order` can include multiple `Items`, so the `Orders` entity type has an `Items` navigation property that returns a collection of `Items` objects.</span></span> <span data-ttu-id="9d90a-110">`OrderItemData`Klasa kontenera jednostek jest typem ogólnym <xref:System.Data.Services.DataService%601> klasy, z której `OrderItems` pochodzi usługa danych.</span><span class="sxs-lookup"><span data-stu-id="9d90a-110">The `OrderItemData` entity container class is the generic type of the <xref:System.Data.Services.DataService%601> class from which the `OrderItems` data service is derived.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d90a-111">Ponieważ ten przykład ilustruje dostawcę danych w pamięci, a zmiany nie są utrwalane poza bieżącymi wystąpieniami obiektów, nie ma korzyści wynikającej z implementacji <xref:System.Data.Services.IUpdatable> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="9d90a-111">Because this example demonstrates an in-memory data provider and changes are not persisted outside of the current object instances, there is no benefit derived from implementing the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="9d90a-112">Przykład implementujący <xref:System.Data.Services.IUpdatable> interfejs można znaleźć w temacie [How to: Create a Data Service przy użyciu LINQ to SQL źródła danych](create-a-data-service-using-linq-to-sql-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="9d90a-112">For an example that implements the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a><span data-ttu-id="9d90a-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9d90a-113">See also</span></span>

- [<span data-ttu-id="9d90a-114">Instrukcje: Tworzenie usługi danych przy użyciu źródła danych LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9d90a-114">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](create-a-data-service-using-linq-to-sql-wcf.md)
- [<span data-ttu-id="9d90a-115">Dostawcy usług danych</span><span class="sxs-lookup"><span data-stu-id="9d90a-115">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="9d90a-116">Instrukcje: Tworzenie usługi danych przy użyciu źródła danych programu ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="9d90a-116">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](create-a-data-service-using-an-adonet-ef-data-wcf.md)
