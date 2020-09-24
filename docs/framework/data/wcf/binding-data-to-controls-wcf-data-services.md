---
title: Powiązywanie danych z kontrolkami (Usługi danych programu WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- data binding, WCF Data Services
ms.assetid: b32e1d49-c214-4cb1-867e-88fbb3d08c8d
ms.openlocfilehash: f2cb1004ef6316bc67189c4e00930f6086cf0dad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152926"
---
# <a name="binding-data-to-controls-wcf-data-services"></a>Powiązywanie danych z kontrolkami (Usługi danych programu WCF)

Za pomocą Usługi danych programu WCF można powiązać kontrolki, takie jak `ComboBox` `ListView` kontrolki i, z wystąpieniem <xref:System.Data.Services.Client.DataServiceCollection%601> klasy. Ta kolekcja, która dziedziczy z <xref:System.Collections.ObjectModel.ObservableCollection%601> klasy, zawiera dane ze źródła danych Open Data Protocol (OData). Ta klasa reprezentuje dynamiczną zbieranie danych, która dostarcza powiadomienia, gdy elementy zostaną dodane lub usunięte. W przypadku używania wystąpienia programu <xref:System.Data.Services.Client.DataServiceCollection%601> w celu powiązania danych usługi danych programu WCF biblioteki klienta obsługują te zdarzenia, aby upewnić się, że obiekty śledzone przez program <xref:System.Data.Services.Client.DataServiceContext> pozostają zsynchronizowane z danymi w związanym elemencie interfejsu użytkownika.  
  
 <xref:System.Data.Services.Client.DataServiceCollection%601>Klasa (pośrednio) implementuje interfejs, <xref:System.Collections.Specialized.INotifyCollectionChanged> aby ostrzec kontekst, gdy obiekty są dodawane lub usuwane z kolekcji. Obiekty typu usługi danych używane z programem <xref:System.Data.Services.Client.DataServiceCollection%601> muszą również implementować <xref:System.ComponentModel.INotifyPropertyChanged> interfejs, aby ostrzec o <xref:System.Data.Services.Client.DataServiceCollection%601> właściwościach obiektów w kolekcji powiązań.  
  
> [!NOTE]
> W przypadku korzystania z okna dialogowego **Dodaj odwołanie do usługi** lub narzędzia [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) z `/dataservicecollection` opcją wygenerowania klas usługi danych klienta, wygenerowane klasy danych implementują <xref:System.ComponentModel.INotifyPropertyChanged> interfejs. Aby uzyskać więcej informacji, zobacz [jak: ręczne generowanie klas usługi danych klienta](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="creating-the-binding-collection"></a>Tworzenie kolekcji powiązań  

 Utwórz nowe wystąpienie <xref:System.Data.Services.Client.DataServiceCollection%601> klasy przez wywołanie jednej z metod konstruktora klasy z dostarczonym <xref:System.Data.Services.Client.DataServiceContext> wystąpieniem i opcjonalnie <xref:System.Data.Services.Client.DataServiceQuery%601> zapytania LINQ, które, gdy jest wykonywane, zwraca <xref:System.Collections.Generic.IEnumerable%601> wystąpienie. <xref:System.Collections.Generic.IEnumerable%601>Zapewnia to źródło obiektów dla kolekcji powiązań, które są materiałowe ze źródła danych OData. Aby uzyskać więcej informacji, zobacz [obiekt materializację](object-materialization-wcf-data-services.md). Domyślnie zmiany wprowadzone do obiektów powiązanych i elementów wstawionych do kolekcji są automatycznie śledzone przez <xref:System.Data.Services.Client.DataServiceContext> . Jeśli musisz ręcznie śledzić te zmiany, wywołaj jedną z metod konstruktora, która przyjmuje parametr, `trackingMode` i określ wartość <xref:System.Data.Services.Client.TrackingMode.None> .  
  
 Poniższy przykład pokazuje, jak utworzyć wystąpienie <xref:System.Data.Services.Client.DataServiceCollection%601> w oparciu o dostarczone <xref:System.Data.Services.Client.DataServiceContext> i a <xref:System.Data.Services.Client.DataServiceQuery%601> które zwraca wszystkich klientów z powiązanymi zamówieniami:  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders2.cs#customersorders2binding)]
 [!code-vb[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders2.vb#customersorders2binding)]  
  
## <a name="binding-data-to-windows-presentation-foundation-elements"></a>Powiązywanie danych z Windows Presentation Foundation elementami  

 Ponieważ <xref:System.Data.Services.Client.DataServiceCollection%601> Klasa dziedziczy z <xref:System.Collections.ObjectModel.ObservableCollection%601> klasy, można powiązać obiekty z elementem lub kontrolką w aplikacji Windows Presentation Foundation (WPF) tak jak w przypadku używania <xref:System.Collections.ObjectModel.ObservableCollection%601> klasy do powiązania. Aby uzyskać więcej informacji, zobacz [powiązanie danych (Windows Presentation Foundation)](../../../desktop-wpf/data/data-binding-overview.md). Jednym ze sposobów powiązania danych usługi danych z kontrolkami WPF jest ustawienie `DataContext` właściwości elementu na wystąpienie klasy zawierającej <xref:System.Data.Services.Client.DataServiceCollection%601> wynik zapytania. W takim przypadku należy użyć właściwości, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Aby ustawić źródło obiektu dla kontrolki. Użyj <xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A> właściwości, aby określić, która właściwość powiązanego obiektu ma być wyświetlana. W przypadku powiązania elementu z obiektem pokrewnym, który jest zwracany przez właściwość nawigacji, należy uwzględnić ścieżkę w powiązaniu zdefiniowanym dla <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> właściwości. Ta ścieżka jest określana względem obiektu głównego ustawionego przez <xref:System.Windows.FrameworkElement.DataContext%2A> Właściwość kontrolki nadrzędnej. Poniższy przykład ustawia <xref:System.Windows.FrameworkElement.DataContext%2A> Właściwość <xref:System.Windows.Controls.StackPanel> elementu, aby powiązać formant nadrzędny z <xref:System.Data.Services.Client.DataServiceCollection%601> obiektami klienta:  
  
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#masterdetailbinding)]
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#masterdetailbinding)]  
  
 W poniższym przykładzie przedstawiono definicję powiązania XAML elementu podrzędnego <xref:System.Windows.Controls.DataGrid> i <xref:System.Windows.Controls.ComboBox> kontrolek:  
  
 [!code-xaml[Astoria Northwind Client#MasterDetailXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#masterdetailxaml)]  
  
 Aby uzyskać więcej informacji, zobacz [jak: powiązać dane z elementami Windows Presentation Foundation](bind-data-to-wpf-elements-wcf-data-services.md).  
  
 Gdy jednostka uczestniczy w relacji jeden-do-wielu lub wiele-do-wielu, właściwość nawigacji dla relacji zwraca kolekcję obiektów pokrewnych. W przypadku wygenerowania klas usługi danych klienta przy użyciu okna dialogowego **Dodaj odwołanie do usługi** lub narzędzia DataSvcUtil.exe, właściwość nawigacji zwraca wystąpienie elementu <xref:System.Data.Services.Client.DataServiceCollection%601> . Dzięki temu można powiązać powiązane obiekty z kontrolką i obsługiwać typowe scenariusze powiązań WPF, takie jak wzorzec powiązania szczegółów wzorca dla powiązanych jednostek. W poprzednim przykładzie XAML kod XAML wiąże wzorzec <xref:System.Data.Services.Client.DataServiceCollection%601> z elementem głównym danych. Zamówienie <xref:System.Windows.Controls.DataGrid> jest następnie powiązane z zamówieniami <xref:System.Data.Services.Client.DataServiceCollection%601> zwracanymi z wybranego obiektu Customers, który jest z kolei związany z elementem głównym danych <xref:System.Windows.Window> .  
  
## <a name="binding-data-to-windows-forms-controls"></a>Powiązywanie danych z kontrolkami Windows Forms  

 Aby powiązać obiekty z kontrolką formularza systemu Windows, należy ustawić `DataSource` Właściwość kontrolki na wystąpienie klasy zawierającej <xref:System.Data.Services.Client.DataServiceCollection%601> wynik zapytania.  
  
> [!NOTE]
> Powiązanie danych jest obsługiwane tylko dla formantów nasłuchujących zdarzeń zmiany przez implementację <xref:System.Collections.Specialized.INotifyCollectionChanged> interfejsów i <xref:System.ComponentModel.INotifyPropertyChanged> . Gdy kontrolka nie obsługuje tego rodzaju powiadomienia o zmianach, zmiany wprowadzane do bazowego <xref:System.Data.Services.Client.DataServiceCollection%601> nie zostaną odzwierciedlone w kontrolce powiązanej.  
  
 Poniższy przykład tworzy powiązanie <xref:System.Data.Services.Client.DataServiceCollection%601> z <xref:System.Windows.Forms.ComboBox> formantem:  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdatabindingspecific)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdatabindingspecific)]  
  
 W przypadku wygenerowania klas usługi danych klienta przy użyciu okna dialogowego **Dodaj odwołanie do usługi** , tworzone jest również źródło danych projektu oparte na wygenerowanym <xref:System.Data.Services.Client.DataServiceContext> . Za pomocą tego źródła danych można tworzyć elementy interfejsu użytkownika lub kontrolki, które wyświetlają dane z usługi danych po prostu przeciągając elementy z okna **źródła danych** do projektanta. Elementy te stają się elementami w interfejsie użytkownika aplikacji, które są powiązane ze źródłem danych. Aby uzyskać więcej informacji, zobacz [jak: powiązać dane przy użyciu źródła danych projektu](how-to-bind-data-using-a-project-data-source-wcf-data-services.md).  
  
## <a name="binding-paged-data"></a>Powiązywanie danych stronicowanych  

 Usługę danych można skonfigurować w taki sposób, aby ograniczyć ilość danych, które są zwracane w pojedynczym komunikacie odpowiedzi. Aby uzyskać więcej informacji, zobacz [Konfigurowanie usługi danych](configuring-the-data-service-wcf-data-services.md). Gdy usługa danych jest stronicowana, Każda odpowiedź zawiera link, który jest używany do zwrócenia następnej strony wyników. Aby uzyskać więcej informacji, zobacz [ładowanie odroczonej zawartości](loading-deferred-content-wcf-data-services.md). W takim przypadku należy jawnie załadować strony, wywołując <xref:System.Data.Services.Client.DataServiceCollection%601.Load%2A> metodę w <xref:System.Data.Services.Client.DataServiceCollection%601> przez przekazanie identyfikatora URI uzyskanego z <xref:System.Data.Services.Client.DataServiceQueryContinuation.NextLinkUri%2A> właściwości, jak w poniższym przykładzie:  
  
 [!code-csharp[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddataspecific)]
 [!code-vb[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddataspecific)]  
  
 Powiązane obiekty są ładowane w podobny sposób. Aby uzyskać więcej informacji, zobacz [jak: powiązać dane z elementami Windows Presentation Foundation](bind-data-to-wpf-elements-wcf-data-services.md).  
  
## <a name="customizing-data-binding-behaviors"></a>Dostosowywanie zachowań powiązań danych  

 <xref:System.Data.Services.Client.DataServiceCollection%601>Klasa umożliwia przechwycenie zdarzeń zgłaszanych podczas wprowadzania zmian do kolekcji, takich jak obiekt, który jest dodawany lub usuwany, oraz po wprowadzeniu zmian we właściwościach obiektu w kolekcji. Zdarzenia powiązania danych można modyfikować, aby zastąpić zachowanie domyślne, które obejmuje następujące ograniczenia:  
  
- W delegatach nie jest przeprowadzana Walidacja.  
  
- Dodanie jednostki powoduje automatyczne dodanie powiązanych jednostek.  
  
- Usunięcie jednostki nie powoduje usunięcia powiązanych jednostek.  
  
 Podczas tworzenia nowego wystąpienia programu <xref:System.Data.Services.Client.DataServiceCollection%601> można określić następujące parametry, które definiują Delegaty do metod, które obsługują zdarzenia wywoływane, gdy obiekty powiązane są zmieniane:  
  
- `entityChanged` -Metoda, która jest wywoływana, gdy właściwość obiektu powiązanego jest zmieniana. Ten <xref:System.Func%602> Delegat akceptuje <xref:System.Data.Services.Client.EntityChangedParams> obiekt i zwraca wartość logiczną wskazującą, czy domyślne zachowanie, aby wywołać <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> na <xref:System.Data.Services.Client.DataServiceContext> , powinno być nadal wykonywane.  
  
- `entityCollectionChanged` -Metoda, która jest wywoływana, gdy obiekt zostanie dodany lub usunięty z kolekcji powiązań. Ten <xref:System.Func%602> Delegat akceptuje <xref:System.Data.Services.Client.EntityCollectionChangedParams> obiekt i zwraca wartość logiczną wskazującą, czy domyślne zachowanie, do wywołania <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Add> akcji lub <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> dla <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Remove> akcji na <xref:System.Data.Services.Client.DataServiceContext> , powinno być nadal wykonywane.  
  
> [!NOTE]
> Usługi danych programu WCF nie sprawdza poprawności zachowań niestandardowych zaimplementowanych w tych delegatach.  
  
 W poniższym przykładzie <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Remove> Akcja jest dostosowywana do wywoływania <xref:System.Data.Services.Client.DataServiceContext.DeleteLink%2A> <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> metody and w celu usunięcia `Orders_Details` jednostek należących do usuniętej `Orders` jednostki. Ta akcja niestandardowa jest wykonywana, ponieważ jednostki zależne nie są automatycznie usuwane po usunięciu jednostki nadrzędnej.  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#customersordersdeleterelated)]  
  
 Aby uzyskać więcej informacji, zobacz [How to: Dostosowywanie zachowań powiązań danych](how-to-customize-data-binding-behaviors-wcf-data-services.md).  
  
 Zachowanie domyślne, gdy obiekt jest usuwany z przy <xref:System.Data.Services.Client.DataServiceCollection%601> użyciu metody, <xref:System.Collections.ObjectModel.Collection%601.Remove%2A> jest również oznaczony jako usunięty w obiekcie <xref:System.Data.Services.Client.DataServiceContext> . Aby zmienić to zachowanie, można określić delegata metody w `entityCollectionChanged` parametrze, który jest wywoływany, gdy <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> wystąpi zdarzenie.  
  
## <a name="data-binding-with-custom-client-data-classes"></a>Powiązanie danych z niestandardowymi klasami danych klienta  

 Aby można było załadować obiekty do <xref:System.Data.Services.Client.DataServiceCollection%601> , same obiekty muszą implementować <xref:System.ComponentModel.INotifyPropertyChanged> interfejs. Klasy klienta usługi danych, które są generowane podczas korzystania z okna dialogowego **Dodaj odwołanie do usługi** lub narzędzia [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) implementują ten interfejs. W przypadku dostarczania własnych klas danych klienta należy użyć innego typu kolekcji do powiązania danych. Gdy obiekty zmieniają się, należy obsłużyć zdarzenia w formantach powiązanych z danymi, aby wywołać następujące metody <xref:System.Data.Services.Client.DataServiceContext> klasy:  
  
- <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> — Po dodaniu nowego obiektu do kolekcji.  
  
- <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> — gdy obiekt zostanie usunięty z kolekcji.  
  
- <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> — gdy właściwość zostanie zmieniona w obiekcie w kolekcji.  
  
- <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> — Po dodaniu obiektu do kolekcji pokrewnego obiektu.  
  
- <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> — Po dodaniu obiektu do kolekcji powiązanych obiektów.  
  
 Aby uzyskać więcej informacji, zobacz [Aktualizowanie usługi danych](updating-the-data-service-wcf-data-services.md).  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Ręczne generowanie klas usługi danych klienta](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)
- [Instrukcje: Dodawanie odwołania do usługi danych](how-to-add-a-data-service-reference-wcf-data-services.md)
