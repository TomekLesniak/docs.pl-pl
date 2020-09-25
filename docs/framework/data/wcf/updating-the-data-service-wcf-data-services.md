---
title: Aktualizowanie usługi danych (Usługi danych programu WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
- WCF Data Services, client library
ms.assetid: 00d993be-ffed-4dea-baf7-6eea982cdb54
ms.openlocfilehash: 3e2bd3f4ca5402abe4a7f8ec8f5410effaee6700
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180611"
---
# <a name="updating-the-data-service-wcf-data-services"></a>Aktualizowanie usługi danych (Usługi danych programu WCF)

W przypadku korzystania z biblioteki klienta Usługi danych programu WCF do korzystania z kanału informacyjnego protokołu OData (Open Data Protocol), biblioteka tłumaczy wpisy w strumieniu na wystąpienia klas usługi danych klienta. Te klasy usługi danych są śledzone przy użyciu, <xref:System.Data.Services.Client.DataServiceContext> do którego <xref:System.Data.Services.Client.DataServiceQuery%601> należy. Klient śledzi zmiany w jednostkach, które są zgłaszane przy użyciu metod w <xref:System.Data.Services.Client.DataServiceContext> . Te metody umożliwiają klientowi śledzenie dodanych i usuniętych jednostek, a także zmiany wartości właściwości lub relacje między wystąpieniami jednostek. Te śledzone zmiany są wysyłane z powrotem do usługi danych jako operacje oparte na interfejsie REST podczas wywoływania <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> metody.  
  
> [!NOTE]
> W przypadku użycia wystąpienia programu <xref:System.Data.Services.Client.DataServiceCollection%601> w celu powiązania danych z kontrolkami zmiany wprowadzone do danych w formancie powiązanym są automatycznie raportowane do <xref:System.Data.Services.Client.DataServiceContext> . Aby uzyskać więcej informacji, zobacz [Powiązywanie danych z kontrolkami](binding-data-to-controls-wcf-data-services.md).  
  
## <a name="adding-modifying-and-changing-entities"></a>Dodawanie, modyfikowanie i zmiana jednostek  

 W przypadku użycia okna dialogowego **Dodaj odwołanie do usługi** w programie Visual Studio w celu dodania odwołania do źródła danych OData, wytworzone klasy usługi dane klienta mają metodę static *Create* , która przyjmuje jeden parametr dla każdej właściwości jednostki, która nie dopuszcza wartości null. Tej metody można użyć do tworzenia wystąpień klas typu jednostki, jak w poniższym przykładzie:  
  
 [!code-csharp[Astoria Northwind Client#CreateNewProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#createnewproduct)]
 [!code-vb[Astoria Northwind Client#CreateNewProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#createnewproduct)]  
  
 Aby dodać wystąpienie jednostki, wywołaj odpowiednią metodę *AddTo* w <xref:System.Data.Services.Client.DataServiceContext> klasie wygenerowanej przez okno dialogowe **Dodaj odwołanie do usługi** , jak w poniższym przykładzie:  
  
 [!code-csharp[Astoria Northwind Client#AddProductSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addproductspecific)]
 [!code-vb[Astoria Northwind Client#AddProductSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addproductspecific)]  
  
 Spowoduje to dodanie obiektu do kontekstu i do poprawnego zestawu jednostek. Można również wywołać metodę <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> , ale zamiast tego należy podać nazwę zestawu jednostek. Jeśli dodana jednostka ma jedną lub więcej relacji z innymi jednostkami, można użyć <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> metody lub użyć jednej z powyższych metod, a także jawnie zdefiniować te linki. Te operacje zostały omówione w dalszej części tego tematu.  
  
 Aby zmodyfikować istniejące wystąpienie jednostki, pierwsze zapytanie dla tej jednostki, wprowadź odpowiednie zmiany w jego właściwościach, a następnie Wywołaj <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> metodę w <xref:System.Data.Services.Client.DataServiceContext> celu wskazania do biblioteki klienta, której potrzebuje do wysłania aktualizacji dla tego obiektu, jak pokazano w następującym przykładzie:  
  
 [!code-csharp[Astoria Northwind Client#ModifyCustomerSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#modifycustomerspecific)]
 [!code-vb[Astoria Northwind Client#ModifyCustomerSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#modifycustomerspecific)]  
  
 Aby usunąć wystąpienie jednostki, wywołaj <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> metodę w <xref:System.Data.Services.Client.DataServiceContext> , jak pokazano w następującym przykładzie:  
  
 [!code-csharp[Astoria Northwind Client#DeleteProductSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#deleteproductspecific)]
 [!code-vb[Astoria Northwind Client#DeleteProductSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#deleteproductspecific)]  
  
 Aby uzyskać więcej informacji, zobacz [jak: Dodawanie, modyfikowanie i usuwanie jednostek](how-to-add-modify-and-delete-entities-wcf-data-services.md).  
  
## <a name="attaching-entities"></a>Dołączanie jednostek  

 Biblioteka klienta umożliwia zapisywanie aktualizacji dokonanych w jednostce bez uprzedniego wykonania zapytania w celu załadowania jednostki do programu <xref:System.Data.Services.Client.DataServiceContext> . Użyj <xref:System.Data.Services.Client.DataServiceContext.AttachTo%2A> metody, aby dołączyć istniejący obiekt do określonego zestawu jednostek w <xref:System.Data.Services.Client.DataServiceContext> . Następnie można zmodyfikować obiekt i zapisać zmiany w usłudze danych. W poniższym przykładzie obiekt klienta, który został zmieniony, jest dołączony do kontekstu, a następnie <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> jest wywoływana w celu oznaczenia dołączonego obiektu, tak jak <xref:System.Data.Services.Client.EntityStates.Modified> wcześniej, <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> jest wywoływana:  
  
 [!code-csharp[Astoria Northwind Client#AttachObjectSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobjectspecific)]
 [!code-vb[Astoria Northwind Client#AttachObjectSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobjectspecific)]  
  
 Podczas dołączania obiektów stosowane są następujące zagadnienia:  
  
- Obiekt jest podłączony w <xref:System.Data.Services.Client.EntityStates.Unchanged> stanie.  
  
- Po dołączeniu obiektu obiekty powiązane z dołączonym obiektem nie są także dołączone.  
  
- Nie można dołączyć obiektu, jeśli jednostka jest już śledzona przez kontekst.  
  
- <xref:System.Data.Services.Client.DataServiceContext.AttachTo%28System.String%2CSystem.Object%2CSystem.String%29>Przeciążenie metody, które pobiera `etag` parametr, jest używany podczas dołączania obiektu jednostki, który został odebrany wraz z wartością ETag. Ta wartość eTag jest następnie używana do sprawdzania współbieżności po zapisaniu zmian w dołączonym obiekcie.  
  
 Aby uzyskać więcej informacji, zobacz [How to: dołączanie istniejącej jednostki do obiekcie DataServiceContext](attach-an-existing-entity-to-dc-wcf-data.md).  
  
## <a name="creating-and-modifying-relationship-links"></a>Tworzenie i modyfikowanie linków relacji  

 Po dodaniu nowej jednostki przy użyciu <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> metody lub odpowiedniej metody *AddTo* <xref:System.Data.Services.Client.DataServiceContext> klasy wygenerowanej przez okno dialogowe **Dodaj odwołanie do usługi** wszelkie relacje między nową jednostką i powiązanymi jednostkami nie są definiowane automatycznie.  
  
 Można tworzyć i zmieniać relacje między wystąpieniami jednostek, a ich Biblioteka kliencka odzwierciedla te zmiany w usłudze danych. Relacje między jednostkami są zdefiniowane jako skojarzenia w modelu i <xref:System.Data.Services.Client.DataServiceContext> śledzi każdą relację jako obiekt łącza w kontekście. Usługi danych programu WCF udostępnia następujące metody <xref:System.Data.Services.Client.DataServiceContext> klasy do tworzenia, modyfikowania i usuwania tych linków:  
  
|Metoda|Opis|  
|------------|-----------------|  
|<xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A>|Tworzy nowy link między dwoma powiązanymi obiektami jednostek. Wywołanie tej metody jest równoważne wywołaniu <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> i <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> zarówno do tworzenia nowego obiektu, jak i definiowania relacji z istniejącym obiektem.|  
|<xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>|Tworzy nowy link między dwoma powiązanymi obiektami jednostek.|  
|<xref:System.Data.Services.Client.DataServiceContext.SetLink%2A>|Aktualizuje istniejące łącze między dwoma powiązanymi obiektami jednostek. <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> służy również do usuwania linków z kardynalnością zero-lub-jeden-do-jednego ( `0..1:1` ) i jeden-do-jednego ( `1:1` ). Można to zrobić przez ustawienie powiązanego obiektu na `null` .|  
|<xref:System.Data.Services.Client.DataServiceContext.DeleteLink%2A>|Oznacza link, który jest śledzony przez kontekst do usunięcia, gdy <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> wywoływana jest metoda. Tej metody należy użyć w przypadku usunięcia powiązanego obiektu lub zmiany relacji przez usunięcie łącza do istniejącego obiektu, a następnie dodanie linku do nowego powiązanego obiektu.|  
|<xref:System.Data.Services.Client.DataServiceContext.AttachLink%2A>|Powiadamia kontekst istniejącego łącza między dwoma obiektami jednostek. W kontekście przyjęto założenie, że ta relacja już istnieje w usłudze danych i nie próbuje utworzyć łącza po wywołaniu <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> metody. Użyj tej metody, gdy dołączysz obiekty do kontekstu i chcesz również dołączyć łącze między nimi. W przypadku definiowania nowej relacji należy zamiast niej używać <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> .|  
|<xref:System.Data.Services.Client.DataServiceContext.DetachLink%2A>|Wyłącza śledzenie określonego linku w kontekście. Ta metoda służy do usuwania relacji jeden-do-wielu ( `*:*` ). W przypadku linków relacji z kardynalnością jednego należy zamiast tego użyć <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> .|  
  
 Poniższy przykład pokazuje, jak użyć metody, <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> Aby dodać nową `Order_Detail` , która jest powiązana z istniejącą `Orders` jednostką. Ponieważ nowy `Order_Details` obiekt jest teraz śledzony przez <xref:System.Data.Services.Client.DataServiceContext> , relacja dodanego `Order_Details` obiektu do istniejącej `Products` jednostki jest definiowana przez wywołanie <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> metody:  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorderspecific)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorderspecific)]  
  
 Chociaż <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> Metoda definiuje linki, które muszą zostać utworzone w usłudze danych w celu odzwierciedlenia tych linków w obiektach, które znajdują się w kontekście, należy również ustawić właściwości nawigacji dla obiektów. W poprzednim przykładzie należy ustawić właściwości nawigacji w następujący sposób:  
  
 [!code-csharp[Astoria Northwind Client#SetNavProps](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#setnavprops)]
 [!code-vb[Astoria Northwind Client#SetNavProps](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#setnavprops)]  
  
 Aby uzyskać więcej informacji, zobacz [How to: define Entity Relationships](how-to-define-entity-relationships-wcf-data-services.md).  
  
## <a name="saving-changes"></a>Zapisywanie zmian  

 Zmiany są śledzone w <xref:System.Data.Services.Client.DataServiceContext> wystąpieniu, ale nie są natychmiast wysyłane do serwera. Po zakończeniu pracy z wymaganymi zmianami dotyczącymi określonego działania Wywołaj polecenie <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> Prześlij wszystkie zmiany do usługi danych. Aby uzyskać więcej informacji, zobacz [zarządzanie kontekstem usługi danych](managing-the-data-service-context-wcf-data-services.md). Można także zapisywać zmiany asynchronicznie przy użyciu <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A> metod i <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A> . Aby uzyskać więcej informacji, zobacz [operacje asynchroniczne](asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>Zobacz też

- [Biblioteka klienta usług danych WCF](wcf-data-services-client-library.md)
- [Wykonywanie zapytań do usługi danych](querying-the-data-service-wcf-data-services.md)
- [Operacje asynchroniczne](asynchronous-operations-wcf-data-services.md)
- [Operacje przetwarzania wsadowego](batching-operations-wcf-data-services.md)
- [Materializacja obiektu](object-materialization-wcf-data-services.md)
- [Zarządzanie kontekstem usługi danych](managing-the-data-service-context-wcf-data-services.md)
