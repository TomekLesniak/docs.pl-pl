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
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>Instrukcje: Włączanie dostępu do usługi danych (Usługi danych programu WCF)

W Usługi danych programu WCF należy jawnie udzielić dostępu do zasobów, które są udostępniane przez usługę danych. Oznacza to, że po utworzeniu nowej usługi danych nadal trzeba jawnie zapewnić dostęp do poszczególnych zasobów jako zestawy jednostek. W tym temacie pokazano, jak włączyć dostęp do odczytu i zapisu do pięciu zestawów jednostek w usłudze danych Northwind, która została utworzona po zakończeniu [przewodnika Szybki Start](quickstart-wcf-data-services.md). Ponieważ <xref:System.Data.Services.EntitySetRights> Wyliczenie jest zdefiniowane przy użyciu <xref:System.FlagsAttribute> , można użyć operatora logicznego OR do określenia wielu uprawnień dla pojedynczego zestawu jednostek.  
  
> [!NOTE]
> Każdy klient, który może uzyskać dostęp do aplikacji ASP.NET, może również uzyskać dostęp do zasobów udostępnianych przez usługę danych. W przypadku usługi danych produkcyjnych aby zapobiec nieautoryzowanemu dostępowi do zasobów, należy również zabezpieczyć samą aplikację. Aby uzyskać więcej informacji, zobacz [Zabezpieczanie witryn sieci Web ASP.NET](/previous-versions/aspnet/91f66yxt(v=vs.100)).  
  
### <a name="to-enable-access-to-the-data-service"></a>Aby włączyć dostęp do usługi danych  
  
- W kodzie usługi danych Zastąp symbol zastępczy w `InitializeService` funkcji następującymi elementami:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     Dzięki temu klienci mają dostęp do odczytu i zapisu do `Orders` `Order_Details` zestawów jednostek oraz dostęp tylko do odczytu do `Customers` zestawów jednostek.  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Tworzenie usługi danych WCF działającej na serwerze IIS](how-to-develop-a-wcf-data-service-running-on-iis.md)
- [Konfigurowanie usługi danych](configuring-the-data-service-wcf-data-services.md)
