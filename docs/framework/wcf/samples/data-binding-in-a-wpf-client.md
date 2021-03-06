---
title: Wiązanie danych w kliencie WPF (Windows Presentation Foundation)
ms.date: 03/30/2017
ms.assetid: bb8c8293-5973-4aef-9b07-afeff5d3293c
ms.openlocfilehash: 926b60bd489d65dd2ec051baae399f2688e52cd7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289220"
---
# <a name="data-binding-in-a-windows-presentation-foundation-client"></a>Wiązanie danych w kliencie WPF (Windows Presentation Foundation)

Ten przykład ilustruje użycie powiązania danych w kliencie Windows Presentation Foundation (WPF). Przykład korzysta z usługi Windows Communication Foundation (WCF), która losowo generuje tablicę albumów do zwrócenia do klienta. Każdy album ma nazwę, cenę i listę ścieżek albumów. Ścieżki albumu mają nazwę i czas trwania. Informacje zwracane przez usługę są automatycznie powiązane z interfejsem użytkownika (UI) udostępnionym przez klienta Windows Presentation Foundation (WPF).  
  
> [!NOTE]
> Procedura instalacji i instrukcje dotyczące kompilacji dla tego przykładu znajdują się na końcu tego tematu.  
  
 Powiązanie danych umożliwia automatyczne powiązanie źródła danych z interfejsem użytkownika. Upraszcza to model programowania, ponieważ nie wymaga programistycznego aktualizowania każdego elementu interfejsu użytkownika przy użyciu danych z obiektu danych lub tablicy obiektów danych. Można powiązać obiekt z pojedynczym elementem interfejsu użytkownika lub tablicą z kontrolką, która pobiera wiele danych wejściowych, takich jak `ListBox` . Poniższy kod przedstawia sposób powiązania danych z `DataContext` elementem interfejsu użytkownika.  
  
```csharp  
// Event handler executed when call is complete  
void client_GetAlbumListCompleted(object sender, GetAlbumListCompletedEventArgs e)  
{  
    // This is on the UI thread, myPanel can be accessed directly  
    myPanel.DataContext = e.Result;
}  
```  
  
 W poprzednim przykładzie, `DataContext` dla `grid` elementu układu o nazwie `myPanel` jest ustawiony na dane zwracane przez `GetAlbumList` metodę. `DataContext`Zezwala na elementy, aby dziedziczyć informacje z elementów nadrzędnych o źródle danych używanym do wiązania, a także inne cechy powiązania, takie jak ścieżka. Wiersz kodu musi być wykonywany za każdym razem, gdy dane na serwerze zostaną zaktualizowane. Na przykład jest wykonywane po zainicjowaniu okna i po dodaniu nowego albumu.  
  
 W poniższym przykładowym kodzie XAML jest `ListBox` określana wartość `ItemsSource="{Binding }"` .  
  
```xml  
<ListBox
          ItemTemplate="{StaticResource AlbumStyle}"  
          ItemsSource="{Binding }"
          IsSynchronizedWithCurrentItem="true" />  
```  
  
 Oznacza to, że dane powiązane z elementem interfejsu użytkownika najwyższego poziomu są również powiązane z tą kontrolką (czyli tablicą albumów). Ponadto `ItemTemplate="{StaticResource AlbumStyle}"` Określa szablon danych, który ma być używany dla każdego elementu w `ListBox` . Możesz również zdefiniować szablony danych, aby określić sposób formatowania danych. Te szablony danych mogą być ponownie używane dla innych elementów interfejsu użytkownika w aplikacji, a korzyść polega na tym, że szablon danych jest zdefiniowany i utrzymywany w jednym miejscu.  
  
 `AlbumStyle`Szablon danych tworzy siatkę zawierającą dwa `TextBlock` elementy obok siebie. Jeden określa nazwę albumu i drugą liczbę ścieżek w albumie.  
  
```xaml  
<DataTemplate x:Key="AlbumStyle">  
    <Grid>  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="260" />  
            <ColumnDefinition Width="60" />  
        </Grid.ColumnDefinitions>  
        <TextBlock Grid.Column="0" TextContent="{Binding Path=Title}" />  
        <TextBlock Grid.Column="1" TextContent="{Binding Path=Tracks#.Count}" HorizontalAlignment="Right" />  
    </Grid>  
</DataTemplate>  
```  
  
 Poniższy kod XAML tworzy sekundę `ListBox` .  
  
```xaml  
<ListBox Grid.Row="2"
            Grid.ColumnSpan="2"
            ItemTemplate="{StaticResource TrackStyle}"  
            ItemsSource="{Binding Path=Tracks}" />  
```  
  
 Kod określa ścieżkę dla `ItemsSource` . Oznacza to, że dane powiązane z tym formantem nie są danymi najwyższego poziomu, ale właściwością danych najwyższego poziomu o nazwie `Tracks` . Ta właściwość reprezentuje tablicę ścieżek zawartych w albumie. Ponadto `DataTemplate` określono inną nazwę `TrackStyle` . Układ `TrackStyle` szablonu jest podobny do tego `AlbumStyle` szablonu, ale `TextBlock` s są powiązane z różnymi właściwościami. Dzieje się tak, ponieważ dwa szablony są używane z różnymi obiektami danych.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, skompilować i uruchomić przykład  
  
1. Upewnij się, że została wykonana [Procedura konfiguracji jednorazowej dla przykładów Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Aby skompilować wersję rozwiązania w języku C# lub Visual Basic .NET, postępuj zgodnie z instrukcjami w temacie [Tworzenie przykładów Windows Communication Foundation](building-the-samples.md).  
  
3. Aby uruchomić przykład w konfiguracji na jednym lub wielu komputerach, postępuj zgodnie z instrukcjami w temacie [Uruchamianie przykładów Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Przykłady mogą być już zainstalowane na komputerze. Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady. Ten przykład znajduje się w następującym katalogu.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WPFDataBinding`  
