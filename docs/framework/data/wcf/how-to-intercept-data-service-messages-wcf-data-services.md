---
title: 'Instrukcje: Przechwytywanie komunikatów usługi danych (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: 8cc8bdcf776befafba967ee2649a6ada789d07c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194365"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a>Instrukcje: Przechwytywanie komunikatów usługi danych (Usługi danych programu WCF)

Za pomocą Usługi danych programu WCF można przechwycić komunikaty żądania, aby można było dodać logikę niestandardową do operacji. Aby przechwycić komunikat, należy użyć specjalnie przypisanych metod w usłudze danych. Aby uzyskać więcej informacji, zobacz [Interceptory](interceptors-wcf-data-services.md).  
  
 W przykładzie w tym temacie jest stosowana Przykładowa usługa danych Northwind. Ta usługa jest tworzona po zakończeniu [usługi danych programu WCF przewodnika Szybki Start](quickstart-wcf-data-services.md).  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a>Aby zdefiniować interceptor zapytania dla zestawu jednostek Orders  
  
1. W projekcie usługi danych Northwind Otwórz plik Northwind. svc.  
  
2. Na stronie kodowej dla `Northwind` klasy Dodaj następującą `using` instrukcję ( `Imports` w Visual Basic).  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. W `Northwind` klasie Zdefiniuj metodę operacji usługi o nazwie `OnQueryOrders` w następujący sposób:  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a>Aby zdefiniować interceptor zmiany dla zestawu jednostek Products  
  
1. W projekcie usługi danych Northwind Otwórz plik Northwind. svc.  
  
2. W `Northwind` klasie Zdefiniuj metodę operacji usługi o nazwie `OnChangeProducts` w następujący sposób:  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a>Przykład  

 W tym przykładzie zdefiniowano metodę interceptora zapytania dla `Orders` zestawu jednostek, który zwraca wyrażenie lambda. To wyrażenie zawiera delegata, który filtruje żądany na `Orders` podstawie pokrewnych `Customers` nazw kontaktów. Nazwa jest z kolei określana na podstawie żądającego użytkownika. W tym przykładzie przyjęto założenie, że usługa danych jest hostowana w aplikacji sieci Web ASP.NET używającej programu WCF, a uwierzytelnianie jest włączone. <xref:System.Web.HttpContext>Klasa jest używana do pobierania zasady bieżącego żądania.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a>Przykład  

 W tym przykładzie zdefiniowano metodę interceptora zmian dla `Products` zestawu jednostek. Ta metoda sprawdza poprawność danych wejściowych do usługi <xref:System.Data.Services.UpdateOperations.Add> dla <xref:System.Data.Services.UpdateOperations.Change> operacji lub i zgłasza wyjątek w przypadku wprowadzenia zmiany do wycofanego produktu. Blokuje również usuwanie produktów jako nieobsługiwaną operację.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Definiowanie operacji usługi](how-to-define-a-service-operation-wcf-data-services.md)
- [Definiowanie usług danych WCF](defining-wcf-data-services.md)
