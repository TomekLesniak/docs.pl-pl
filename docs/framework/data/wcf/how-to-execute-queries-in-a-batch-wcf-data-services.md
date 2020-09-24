---
title: 'Instrukcje: wykonywanie zapytań w partii (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: b9b18aabc8321d2f77c3781b836eeb6a0d320229
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150599"
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Instrukcje: wykonywanie zapytań w partii (Usługi danych programu WCF)

Za pomocą biblioteki klienta Usługi danych programu WCF można wykonać kilka zapytań dotyczących usługi danych w pojedynczej partii. Aby uzyskać więcej informacji, zobacz [Przetwarzanie wsadowe operacji](batching-operations-wcf-data-services.md).  
  
 W przykładzie w tym temacie jest stosowana usługa danych przykładowych Northwind i klasy usługi danych klientów. Ta usługa i klasy danych klienta są tworzone po zakończeniu [usługi danych programu WCF szybkiego startu](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak wywołać metodę, <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> Aby wykonać tablicę <xref:System.Data.Services.Client.DataServiceRequest%601> obiektów, które zawierają zapytania, które zwracają zarówno `Customers` obiekty, jak i `Products` z usługi danych Northwind. Kolekcja <xref:System.Data.Services.Client.QueryOperationResponse%601> obiektów w zwracanym elemencie <xref:System.Data.Services.Client.DataServiceResponse> jest wyliczana i wyliczana jest również kolekcja obiektów zawartych w każdej z nich <xref:System.Data.Services.Client.QueryOperationResponse%601> .  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>Zobacz też

- [Biblioteka klienta usług danych WCF](wcf-data-services-client-library.md)
