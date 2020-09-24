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
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a>Instrukcje: Tworzenie usługi danych przy użyciu dostawcy odbicia (Usługi danych programu WCF)

Usługi danych programu WCF umożliwia zdefiniowanie modelu danych, który jest oparty na dowolnej klasie, tak długo, jak te klasy są udostępniane jako obiekty, które implementują <xref:System.Linq.IQueryable%601> interfejs. Aby uzyskać więcej informacji, zobacz [Data Services Providers](data-services-providers-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie zdefiniowano model danych, który zawiera `Orders` i `Items` . Klasa kontenera jednostek `OrderItemData` ma dwie metody publiczne, które zwracają <xref:System.Linq.IQueryable%601> interfejsy. Te interfejsy są zestawami jednostek `Orders` `Items` typów jednostek i. `Order`Może zawierać wiele `Items` , więc `Orders` Typ jednostki ma `Items` Właściwość nawigacji, która zwraca kolekcję `Items` obiektów. `OrderItemData`Klasa kontenera jednostek jest typem ogólnym <xref:System.Data.Services.DataService%601> klasy, z której `OrderItems` pochodzi usługa danych.  
  
> [!NOTE]
> Ponieważ ten przykład ilustruje dostawcę danych w pamięci, a zmiany nie są utrwalane poza bieżącymi wystąpieniami obiektów, nie ma korzyści wynikającej z implementacji <xref:System.Data.Services.IUpdatable> interfejsu. Przykład implementujący <xref:System.Data.Services.IUpdatable> interfejs można znaleźć w temacie [How to: Create a Data Service przy użyciu LINQ to SQL źródła danych](create-a-data-service-using-linq-to-sql-wcf.md).  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Tworzenie usługi danych przy użyciu źródła danych LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md)
- [Dostawcy usług danych](data-services-providers-wcf-data-services.md)
- [Instrukcje: Tworzenie usługi danych przy użyciu źródła danych programu ADO.NET Entity Framework](create-a-data-service-using-an-adonet-ef-data-wcf.md)
