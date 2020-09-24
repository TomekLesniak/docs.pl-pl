---
title: 'Instrukcje: Włączanie stronicowania wyników usługi danych (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: 1c8bb8fe757c35f6096b139da6ca939b1ce1c283
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150625"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a>Instrukcje: Włączanie stronicowania wyników usługi danych (Usługi danych programu WCF)

Usługi danych programu WCF pozwala ograniczyć liczbę jednostek zwracanych przez zapytanie usługi danych. Limity stron są zdefiniowane w metodzie, która jest wywoływana, gdy usługa jest inicjowana i można ją ustawić osobno dla każdego zestawu jednostek.  
  
 Po włączeniu stronicowania końcowy wpis w kanale informacyjnym zawiera link do następnej strony danych. Aby uzyskać więcej informacji, zobacz [Konfigurowanie usługi danych](configuring-the-data-service-wcf-data-services.md).  
  
 W tym temacie przedstawiono sposób modyfikowania usługi danych w celu włączenia stronicowania zwracanych `Customers` i `Orders` zestawów jednostek. W przykładzie w tym temacie jest stosowana Przykładowa usługa danych Northwind. Ta usługa jest tworzona po zakończeniu [usługi danych programu WCF przewodnika Szybki Start](quickstart-wcf-data-services.md).  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a>Jak włączyć stronicowanie zwracanych klientów i zestawów jednostek zamówień  
  
- W kodzie usługi danych Zastąp symbol zastępczy w `InitializeService` funkcji następującymi elementami:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a>Zobacz też

- [Ładowanie odroczonej zawartości](loading-deferred-content-wcf-data-services.md)
- [Instrukcje: Ładowanie stronicowanych wyników](how-to-load-paged-results-wcf-data-services.md)
