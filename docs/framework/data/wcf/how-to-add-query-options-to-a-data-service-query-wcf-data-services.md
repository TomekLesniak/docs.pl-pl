---
title: 'Instrukcje: Dodawanie opcji zapytania do zapytania usługi danych (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: e4258526-557e-4e96-91e1-2175400c7c8f
ms.openlocfilehash: 76d2b1ff3cbb5440bfed62ba840e646cf68de025
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180728"
---
# <a name="how-to-add-query-options-to-a-data-service-query-wcf-data-services"></a>Instrukcje: Dodawanie opcji zapytania do zapytania usługi danych (Usługi danych programu WCF)

Usługi danych programu WCF umożliwia wysyłanie zapytań do usługi danych z aplikacji klienckiej opartej na .NET Framework przy użyciu wygenerowanych klas usługi danych klienta. Najłatwiej jest utworzyć wyrażenie zapytania w języku Integrated Query (LINQ) zawierające odpowiednie opcje zapytania. Możesz również wywołać serię metod zapytań LINQ, aby złożyć równoważne zapytanie. Na koniec możesz użyć metody, <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> Aby dodać opcje zapytania do zapytania. W każdym z tych przypadków identyfikator URI generowany przez klienta zawiera żądany zestaw jednostek z zastosowanymi opcjami zapytania. Aby uzyskać więcej informacji, zobacz [wykonywanie zapytań dotyczących usługi danych](querying-the-data-service-wcf-data-services.md).  
  
 W przykładzie w tym temacie jest stosowana usługa danych przykładowych Northwind i klasy usługi danych klientów. Ta usługa i klasy danych klienta są tworzone po zakończeniu [usługi danych programu WCF szybkiego startu](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak utworzyć wyrażenie zapytania LINQ, które zwraca tylko zamówienia z kosztem frachtu większym niż $30 i która porządkuje wyniki według daty wysyłki w kolejności malejącej.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinq)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinq)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak utworzyć zapytanie LINQ przy użyciu metod zapytań LINQ, które są równoważne z poprzednim zapytaniem.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpression)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpression)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak używać  <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> metody do tworzenia <xref:System.Data.Services.Client.DataServiceQuery%601> , która jest równoważna z poprzednimi przykładami.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptions)]
 [!code-vb[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptions)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak używać `$orderby` opcji zapytania do filtrowania i zamawiania zwracanych obiektów Orders według właściwości fracht.  
  
 [!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#orderwithfilter)]
 [!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#orderwithfilter)]  
  
## <a name="see-also"></a>Zobacz też

- [Wykonywanie zapytań do usługi danych](querying-the-data-service-wcf-data-services.md)
- [Instrukcje: Projekt wyników zapytania](how-to-project-query-results-wcf-data-services.md)
