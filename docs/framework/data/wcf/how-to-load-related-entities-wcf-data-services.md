---
title: 'Instrukcje: ładowanie powiązanych jednostek (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: 1ef7fa93b5afdf664f22bd69d3fe3a3b17e98f18
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180715"
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Instrukcje: ładowanie powiązanych jednostek (Usługi danych programu WCF)

Gdy zachodzi potrzeba załadowania skojarzonych jednostek w Usługi danych programu WCF, można użyć <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> metody <xref:System.Data.Services.Client.DataServiceContext> klasy. Można również użyć metody z <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> , <xref:System.Data.Services.Client.DataServiceQuery%601> Aby wymagać eagerly powiązanych jednostek w tej samej odpowiedzi na zapytanie.  
  
 W przykładzie w tym temacie jest stosowana usługa danych przykładowych Northwind i klasy usługi danych klientów. Ta usługa i klasy danych klienta są tworzone po zakończeniu [usługi danych programu WCF szybkiego startu](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak jawnie załadować `Customer` , która jest powiązana z każdym zwracanym `Orders` wystąpieniem.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak używać <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> metody do zwrócenia `Order Details` , która należy do `Orders` zwracanych przez zapytanie.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>Zobacz też

- [Wykonywanie zapytań do usługi danych](querying-the-data-service-wcf-data-services.md)
