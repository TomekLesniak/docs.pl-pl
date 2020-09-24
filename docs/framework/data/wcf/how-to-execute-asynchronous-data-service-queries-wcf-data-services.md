---
title: 'Instrukcje: wykonywanie zapytań asynchronicznych usługi danych (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
ms.openlocfilehash: 84eb88695580598d41615653723c137d3f766a47
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150612"
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Instrukcje: wykonywanie zapytań asynchronicznych usługi danych (Usługi danych programu WCF)

Za pomocą biblioteki klienta Usługi danych programu WCF można asynchronicznie wykonywać operacje na serwerze klienta, takie jak wykonywanie zapytań i zapisywanie zmian. Aby uzyskać więcej informacji, zobacz [operacje asynchroniczne](asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
> W aplikacji, w której wywołanie zwrotne musi być wywoływane w określonym wątku, należy jawnie zorganizować wykonywanie <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> metody. Aby uzyskać więcej informacji, zobacz [operacje asynchroniczne](asynchronous-operations-wcf-data-services.md).  
  
 W przykładzie w tym temacie jest stosowana usługa danych przykładowych Northwind i klasy usługi danych klientów. Ta usługa i klasy danych klienta są tworzone po zakończeniu [usługi danych programu WCF szybkiego startu](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak wykonać zapytanie asynchroniczne przez wywołanie <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> metody w celu uruchomienia zapytania. Obiekt delegowany w tekście wywołuje <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> metodę w celu wyświetlenia wyników zapytania.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>Zobacz też

- [Biblioteka klienta usług danych WCF](wcf-data-services-client-library.md)
