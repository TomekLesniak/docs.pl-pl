---
title: 'Instrukcje: Określanie liczby jednostek zwróconych przez zapytanie (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, row count
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
ms.openlocfilehash: 0513d7cdb3ab8de8cd8a73528f7e6038a0e4faed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194287"
---
# <a name="how-to-determine-the-number-of-entities-returned-by-a-query-wcf-data-services"></a>Instrukcje: Określanie liczby jednostek zwróconych przez zapytanie (Usługi danych programu WCF)

Za pomocą Usługi danych programu WCF można określić liczbę jednostek, które znajdują się w zestawie jednostek określonym przez identyfikator URI zapytania. Tę liczbę można uwzględnić razem z wynikiem zapytania lub jako wartość całkowitą. Aby uzyskać więcej informacji, zobacz [wykonywanie zapytań dotyczących usługi danych](querying-the-data-service-wcf-data-services.md).  
  
 W przykładzie w tym temacie jest stosowana usługa danych przykładowych Northwind i klasy usługi danych klientów. Ta usługa i klasy danych klienta są tworzone po zakończeniu [usługi danych programu WCF szybkiego startu](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  

 Ten przykład wykonuje zapytanie po wywołaniu <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A> metody. <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A>Właściwość zwraca liczbę jednostek w `Customers` zestawie jednostek.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomers)]  
  
## <a name="example"></a>Przykład  

 Ten przykład wywołuje <xref:System.Linq.Enumerable.Count%2A> metodę zwracającą tylko liczbę całkowitą, która jest liczbą jednostek w `Customers` zestawie jednostek.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomersvalueonly)]  
  
## <a name="see-also"></a>Zobacz też

- [Wykonywanie zapytań do usługi danych](querying-the-data-service-wcf-data-services.md)
