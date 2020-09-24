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
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="82b95-102">Instrukcje: Włączanie stronicowania wyników usługi danych (Usługi danych programu WCF)</span><span class="sxs-lookup"><span data-stu-id="82b95-102">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>

<span data-ttu-id="82b95-103">Usługi danych programu WCF pozwala ograniczyć liczbę jednostek zwracanych przez zapytanie usługi danych.</span><span class="sxs-lookup"><span data-stu-id="82b95-103">WCF Data Services enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="82b95-104">Limity stron są zdefiniowane w metodzie, która jest wywoływana, gdy usługa jest inicjowana i można ją ustawić osobno dla każdego zestawu jednostek.</span><span class="sxs-lookup"><span data-stu-id="82b95-104">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="82b95-105">Po włączeniu stronicowania końcowy wpis w kanale informacyjnym zawiera link do następnej strony danych.</span><span class="sxs-lookup"><span data-stu-id="82b95-105">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="82b95-106">Aby uzyskać więcej informacji, zobacz [Konfigurowanie usługi danych](configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="82b95-106">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="82b95-107">W tym temacie przedstawiono sposób modyfikowania usługi danych w celu włączenia stronicowania zwracanych `Customers` i `Orders` zestawów jednostek.</span><span class="sxs-lookup"><span data-stu-id="82b95-107">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="82b95-108">W przykładzie w tym temacie jest stosowana Przykładowa usługa danych Northwind.</span><span class="sxs-lookup"><span data-stu-id="82b95-108">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="82b95-109">Ta usługa jest tworzona po zakończeniu [usługi danych programu WCF przewodnika Szybki Start](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="82b95-109">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="82b95-110">Jak włączyć stronicowanie zwracanych klientów i zestawów jednostek zamówień</span><span class="sxs-lookup"><span data-stu-id="82b95-110">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
- <span data-ttu-id="82b95-111">W kodzie usługi danych Zastąp symbol zastępczy w `InitializeService` funkcji następującymi elementami:</span><span class="sxs-lookup"><span data-stu-id="82b95-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="82b95-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="82b95-112">See also</span></span>

- [<span data-ttu-id="82b95-113">Ładowanie odroczonej zawartości</span><span class="sxs-lookup"><span data-stu-id="82b95-113">Loading Deferred Content</span></span>](loading-deferred-content-wcf-data-services.md)
- [<span data-ttu-id="82b95-114">Instrukcje: Ładowanie stronicowanych wyników</span><span class="sxs-lookup"><span data-stu-id="82b95-114">How to: Load Paged Results</span></span>](how-to-load-paged-results-wcf-data-services.md)
