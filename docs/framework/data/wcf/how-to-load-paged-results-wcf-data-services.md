---
title: 'Instrukcje: ładowanie wyników stronicowanych (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
ms.openlocfilehash: c49e0b170743332d6cc3aaef7e5503eabab52d97
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91182795"
---
# <a name="how-to-load-paged-results-wcf-data-services"></a>Instrukcje: ładowanie wyników stronicowanych (Usługi danych programu WCF)

Usługi danych programu WCF umożliwia usłudze danych ograniczenie liczby jednostek, które są zwracane w ramach pojedynczego źródła odpowiedzi. W takim przypadku końcowy wpis w kanale informacyjnym zawiera link do następnej strony danych. Identyfikator URI następnej strony danych jest uzyskiwany przez wywołanie <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> metody <xref:System.Data.Services.Client.QueryOperationResponse%601> , która jest zwracana, gdy <xref:System.Data.Services.Client.DataServiceQuery%601> jest wykonywane. Identyfikator URI reprezentowany przez ten obiekt jest następnie używany do załadowania następnej strony wyników. Aby uzyskać więcej informacji, zobacz [ładowanie odroczonej zawartości](loading-deferred-content-wcf-data-services.md).  
  
 W przykładzie w tym temacie jest stosowana usługa danych przykładowych Northwind i klasy usługi danych klientów. Ta usługa i klasy danych klienta są tworzone po zakończeniu [usługi danych programu WCF szybkiego startu](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  

 W tym przykładzie zastosowano `do…while` pętlę w celu załadowania `Customers` jednostek z wyników ze strony z usługi danych.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getcustomerspaged)]  
  
## <a name="example"></a>Przykład  

 Ten przykład zwraca powiązane `Orders` jednostki z każdą `Customers` jednostką i używa `do…while` pętli do załadowania `Customers` stron jednostek i zagnieżdżonej `while` pętli w celu załadowania stron powiązanych `Orders` jednostek z usługi danych.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getcustomerspagednested)]  
  
## <a name="see-also"></a>Zobacz też

- [Ładowanie odroczonej zawartości](loading-deferred-content-wcf-data-services.md)
- [Instrukcje: Ładowanie powiązanych jednostek](how-to-load-related-entities-wcf-data-services.md)
