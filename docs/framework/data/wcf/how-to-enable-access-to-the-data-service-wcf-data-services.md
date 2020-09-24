---
title: 'Instrukcje: Włączanie dostępu do usługi danych (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: 62622a5788a735497a6869c114c572e947067449
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155422"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="8e433-102">Instrukcje: Włączanie dostępu do usługi danych (Usługi danych programu WCF)</span><span class="sxs-lookup"><span data-stu-id="8e433-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>

<span data-ttu-id="8e433-103">W Usługi danych programu WCF należy jawnie udzielić dostępu do zasobów, które są udostępniane przez usługę danych.</span><span class="sxs-lookup"><span data-stu-id="8e433-103">In WCF Data Services, you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="8e433-104">Oznacza to, że po utworzeniu nowej usługi danych nadal trzeba jawnie zapewnić dostęp do poszczególnych zasobów jako zestawy jednostek.</span><span class="sxs-lookup"><span data-stu-id="8e433-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="8e433-105">W tym temacie pokazano, jak włączyć dostęp do odczytu i zapisu do pięciu zestawów jednostek w usłudze danych Northwind, która została utworzona po zakończeniu [przewodnika Szybki Start](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8e433-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="8e433-106">Ponieważ <xref:System.Data.Services.EntitySetRights> Wyliczenie jest zdefiniowane przy użyciu <xref:System.FlagsAttribute> , można użyć operatora logicznego OR do określenia wielu uprawnień dla pojedynczego zestawu jednostek.</span><span class="sxs-lookup"><span data-stu-id="8e433-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e433-107">Każdy klient, który może uzyskać dostęp do aplikacji ASP.NET, może również uzyskać dostęp do zasobów udostępnianych przez usługę danych.</span><span class="sxs-lookup"><span data-stu-id="8e433-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="8e433-108">W przypadku usługi danych produkcyjnych aby zapobiec nieautoryzowanemu dostępowi do zasobów, należy również zabezpieczyć samą aplikację.</span><span class="sxs-lookup"><span data-stu-id="8e433-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="8e433-109">Aby uzyskać więcej informacji, zobacz [Zabezpieczanie witryn sieci Web ASP.NET](/previous-versions/aspnet/91f66yxt(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8e433-109">For more information, see [Securing ASP.NET Web Sites](/previous-versions/aspnet/91f66yxt(v=vs.100)).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="8e433-110">Aby włączyć dostęp do usługi danych</span><span class="sxs-lookup"><span data-stu-id="8e433-110">To enable access to the data service</span></span>  
  
- <span data-ttu-id="8e433-111">W kodzie usługi danych Zastąp symbol zastępczy w `InitializeService` funkcji następującymi elementami:</span><span class="sxs-lookup"><span data-stu-id="8e433-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="8e433-112">Dzięki temu klienci mają dostęp do odczytu i zapisu do `Orders` `Order_Details` zestawów jednostek oraz dostęp tylko do odczytu do `Customers` zestawów jednostek.</span><span class="sxs-lookup"><span data-stu-id="8e433-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e433-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8e433-113">See also</span></span>

- [<span data-ttu-id="8e433-114">Instrukcje: Tworzenie usługi danych WCF działającej na serwerze IIS</span><span class="sxs-lookup"><span data-stu-id="8e433-114">How to: Develop a WCF Data Service Running on IIS</span></span>](how-to-develop-a-wcf-data-service-running-on-iis.md)
- [<span data-ttu-id="8e433-115">Konfigurowanie usługi danych</span><span class="sxs-lookup"><span data-stu-id="8e433-115">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)
