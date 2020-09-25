---
title: 'Instrukcje: wykonywanie zapytań dotyczących usługi danych (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: 62997821-e0c6-4c4d-9fb7-1273fb5e5d18
ms.openlocfilehash: 11a37340df879db7c2f8fdeaa792c1466e4a75d0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184758"
---
# <a name="how-to-execute-data-service-queries-wcf-data-services"></a>Instrukcje: wykonywanie zapytań dotyczących usługi danych (Usługi danych programu WCF)

Usługi danych programu WCF umożliwia wysyłanie zapytań do usługi danych z aplikacji klienckiej opartej na .NET Framework przy użyciu wygenerowanych klas usługi danych klienta. Zapytania można wykonywać za pomocą jednej z następujących metod:  
  
- Wykonywanie zapytania LINQ względem nazwy <xref:System.Data.Services.Client.DataServiceQuery%601> uzyskanej od elementu <xref:System.Data.Services.Client.DataServiceContext> `Add Data Service Reference` generowanego przez narzędzie.  
  
- Niejawnie, przez Wyliczenie w odniesieniu do podanej nazwy <xref:System.Data.Services.Client.DataServiceQuery%601> uzyskanej od <xref:System.Data.Services.Client.DataServiceContext> `Add Data Service Reference` wygenerowanego narzędzia.  
  
- Jawnie, wywołując <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> metodę na <xref:System.Data.Services.Client.DataServiceQuery%601> lub <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> metodę wykonywania asynchronicznego.  
  
 Aby uzyskać więcej informacji, zobacz [wykonywanie zapytań dotyczących usługi danych](querying-the-data-service-wcf-data-services.md).  
  
 W przykładzie w tym temacie jest stosowana usługa danych przykładowych Northwind i klasy usługi danych klientów. Ta usługa i klasy danych klienta są tworzone po zakończeniu [usługi danych programu WCF szybkiego startu](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak zdefiniować i wykonać zapytanie LINQ zwracające wszystko do `Customers` usługi danych Northwind.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomerslinq)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomerslinq)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak użyć kontekstu `Add Data Service Reference` generowanego przez narzędzie, aby niejawnie wykonać zapytanie zwracające wszystko do `Customers` usługi danych Northwind. Identyfikator URI żądanego `Customers` zestawu jednostek jest określany automatycznie przez kontekst. Zapytanie jest wykonywane niejawnie, gdy występuje wyliczenie.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomers)]
 [!code-vb[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomers)]  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie pokazano, jak użyć, <xref:System.Data.Services.Client.DataServiceContext> Aby jawnie wykonać zapytanie zwracające wszystko do `Customers` usługi danych Northwind.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomersexplicit)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomersexplicit)]  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Dodawanie opcji zapytania do zapytania usługi danych](how-to-add-query-options-to-a-data-service-query-wcf-data-services.md)
