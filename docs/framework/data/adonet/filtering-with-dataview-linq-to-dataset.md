---
title: Filtrowanie za pomocą widoku danych (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5632d74a-ff53-4ea7-9fe7-4a148eeb1c68
ms.openlocfilehash: 9b4c8e9730dde7d19df9e6a11052ae4591465ea7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177465"
---
# <a name="filtering-with-dataview-linq-to-dataset"></a>Filtrowanie za pomocą widoku danych (LINQ to DataSet)

Możliwość filtrowania danych przy użyciu określonych kryteriów, a następnie prezentowania danych do klienta za pośrednictwem kontrolki interfejsu użytkownika jest ważnym aspektem powiązania danych. <xref:System.Data.DataView> oferuje kilka sposobów filtrowania danych i zwracania podzbiorów wierszy danych spełniających kryteria filtru. Oprócz funkcji filtrowania opartych na ciągach, <xref:System.Data.DataView> umożliwia również korzystanie z wyrażeń LINQ dla kryteriów filtrowania. Wyrażenia LINQ umożliwiają wykonywanie bardziej złożonych i zaawansowanych operacji filtrowania niż filtrowanie oparte na ciągach.  
  
 Istnieją dwa sposoby filtrowania danych przy użyciu <xref:System.Data.DataView> :  
  
- Utwórz <xref:System.Data.DataView> z kwerendy LINQ to DataSetej z klauzulą WHERE.  
  
- Użyj istniejących funkcji filtrowania opartych na ciągach <xref:System.Data.DataView> .  
  
## <a name="creating-dataview-from-a-query-with-filtering-information"></a>Tworzenie elementu DataView z zapytania z informacjami o filtrowaniu  

 <xref:System.Data.DataView>Obiekt można utworzyć na podstawie zapytania LINQ to DataSet. Jeśli zapytanie zawiera `Where` klauzulę, <xref:System.Data.DataView> jest tworzona z informacjami o filtrowaniu z zapytania. Wyrażenie w `Where` klauzuli służy do określenia, które wiersze danych zostaną uwzględnione w <xref:System.Data.DataView> , i jest podstawą filtru.  
  
 Filtry oparte na wyrażeniach oferują bardziej zaawansowane i złożone filtrowanie niż prostsze filtry oparte na ciągach. Filtry oparte na ciągach i wyrażeniach wykluczają się wzajemnie. Gdy parametr jest <xref:System.Data.DataView.RowFilter%2A> ustawiony po utworzeniu na podstawie <xref:System.Data.DataView> zapytania, filtr oparty na wyrażeniach wywnioskowany na podstawie zapytania jest czyszczony.  
  
> [!NOTE]
> W większości przypadków wyrażenia używane do filtrowania nie powinny mieć efektów ubocznych i muszą być deterministyczne. Ponadto wyrażenia nie powinny zawierać żadnych logiki, które są zależne od ustawionej liczby wykonań, ponieważ operacje filtrowania mogą być wykonywane dowolną liczbę razy.  
  
### <a name="example"></a>Przykład  

 W poniższym przykładzie zapytania tabeli SalesOrderDetail są wysyłane w przypadku zamówień o ilości większej niż 2 i mniejszej niż 6; tworzy <xref:System.Data.DataView> z tego zapytania i wiąże z <xref:System.Data.DataView> <xref:System.Windows.Forms.BindingSource> :  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhere](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhere)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhere](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhere)]  
  
### <a name="example"></a>Przykład  

 Poniższy przykład tworzy na <xref:System.Data.DataView> podstawie zapytania o zamówienia złożone po 6 czerwca 2001:  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhere3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhere3)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhere3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhere3)]  
  
### <a name="example"></a>Przykład  

 Filtrowanie może być również łączone z sortowaniem. Poniższy przykład tworzy <xref:System.Data.DataView> zapytanie dla kontaktów, których nazwisko zaczyna się od "S" i posortowane według nazwiska, a następnie imię:  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhereOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhereorderbythenby)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhereOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhereorderbythenby)]  
  
### <a name="example"></a>Przykład  

 W poniższym przykładzie jest używany algorytm SoundEx do znajdowania kontaktów, których nazwisko jest podobne do "Zhu". Algorytm SoundEx jest implementowany w metodzie SoundEx.  
  
 [!code-csharp[DP DataView Samples#LDVSoundExFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvsoundexfilter)]
 [!code-vb[DP DataView Samples#LDVSoundExFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvsoundexfilter)]  
  
 SoundEx jest algorytmem fonetycznym używanym do indeksowania nazw przez dźwięk, ponieważ są one wymawiane w języku angielskim, pierwotnie opracowane przez Biuro spisu USA. Metoda SoundEx zwraca 4-znakowy kod dla nazwy składającej się z litery angielskiej, a trzy cyfry. Litera jest pierwszą literą nazwy i numery, które kodują pozostałe spółgłoski w nazwie. Podobne nazwy dźwiękowe mają ten sam kod SoundEx. Implementacja SoundEx użyta w metodzie SoundEx poprzedniego przykładu jest pokazana tutaj:  
  
 [!code-csharp[DP DataView Samples#SoundEx](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#soundex)]
 [!code-vb[DP DataView Samples#SoundEx](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#soundex)]  
  
## <a name="using-the-rowfilter-property"></a>Używanie właściwości RowFilter  

 Istniejące funkcje filtrowania oparte na ciągach <xref:System.Data.DataView> nadal działają w kontekście LINQ to DataSet. Aby uzyskać więcej informacji o filtrowaniu opartym na ciągach <xref:System.Data.DataView.RowFilter%2A> , zobacz [Sortowanie i filtrowanie danych](./dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Poniższy przykład tworzy <xref:System.Data.DataView> z tabeli Contact, a następnie ustawia <xref:System.Data.DataView.RowFilter%2A> Właściwość, aby zwracała wiersze, w których nazwisko kontaktu ma wartość "Zhu":  
  
 [!code-csharp[DP DataView Samples#LDVRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvrowfilter)]
 [!code-vb[DP DataView Samples#LDVRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvrowfilter)]  
  
 Po <xref:System.Data.DataView> utworzeniu z <xref:System.Data.DataTable> kwerendy lub LINQ to DataSet, można użyć <xref:System.Data.DataView.RowFilter%2A> właściwości, aby określić podzestawy wierszy na podstawie ich wartości kolumn. Filtry oparte na ciągach i wyrażeniach wykluczają się wzajemnie. Ustawienie <xref:System.Data.DataView.RowFilter%2A> właściwości spowoduje wyczyszczenie wyrażenia filtru wywnioskowanego z kwerendy LINQ to DataSet i wyrażenia filtru nie można zresetować.  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhereSetRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywheresetrowfilter)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhereSetRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywheresetrowfilter)]  
  
 Jeśli chcesz zwrócić wyniki konkretnego zapytania dotyczącego danych, w przeciwieństwie do udostępnienia dynamicznego widoku podzbioru danych, możesz użyć <xref:System.Data.DataView.Find%2A> metod lub zamiast <xref:System.Data.DataView.FindRows%2A> <xref:System.Data.DataView> ustawić <xref:System.Data.DataView.RowFilter%2A> Właściwość. <xref:System.Data.DataView.RowFilter%2A>Właściwość najlepiej jest używana w aplikacji powiązanej z danymi, gdzie kontrolka powiązania Wyświetla przefiltrowane wyniki. Ustawienie <xref:System.Data.DataView.RowFilter%2A> właściwości powoduje odbudowanie indeksu dla danych, dodanie obciążenia do aplikacji i zmniejszenie wydajności. <xref:System.Data.DataView.Find%2A>Metody i <xref:System.Data.DataView.FindRows%2A> używają bieżącego indeksu bez konieczności ponownego kompilowania indeksu. Jeśli zamierzasz wywołać <xref:System.Data.DataView.Find%2A> lub <xref:System.Data.DataView.FindRows%2A> tylko raz, należy użyć istniejącej <xref:System.Data.DataView> . Jeśli chcesz wywoływać <xref:System.Data.DataView.Find%2A> lub <xref:System.Data.DataView.FindRows%2A> wiele razy, należy utworzyć nową, <xref:System.Data.DataView> Aby ponownie skompilować indeks w kolumnie, w której ma zostać wyszukane, a następnie wywołać <xref:System.Data.DataView.Find%2A> <xref:System.Data.DataView.FindRows%2A> metody lub. Aby uzyskać więcej informacji o <xref:System.Data.DataView.Find%2A> <xref:System.Data.DataView.FindRows%2A> metodach i zobacz [Znajdowanie wierszy](./dataset-datatable-dataview/finding-rows.md) i [wydajności widoku](dataview-performance.md)danych.  
  
## <a name="clearing-the-filter"></a>Czyszczenie filtru  

 Filtr dla <xref:System.Data.DataView> można wyczyścić po ustawieniu filtrowania przy użyciu <xref:System.Data.DataView.RowFilter%2A> właściwości. Filtr na stronie <xref:System.Data.DataView> można wyczyścić na dwa różne sposoby:  
  
- Ustaw <xref:System.Data.DataView.RowFilter%2A> Właściwość na wartość `null` .  
  
- Ustaw <xref:System.Data.DataView.RowFilter%2A> Właściwość na pusty ciąg.  
  
### <a name="example"></a>Przykład  

 Poniższy przykład tworzy na <xref:System.Data.DataView> podstawie zapytania, a następnie czyści Właściwość Filter by Setting <xref:System.Data.DataView.RowFilter%2A> `null` :  
  
 [!code-csharp[DP DataView Samples#LDVClearRowFilter2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearrowfilter2)]
 [!code-vb[DP DataView Samples#LDVClearRowFilter2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearrowfilter2)]  
  
### <a name="example"></a>Przykład  

 Poniższy przykład tworzy <xref:System.Data.DataView> z tabeli zestaw <xref:System.Data.DataView.RowFilter%2A> właściwości, a następnie czyści filtr przez ustawienie <xref:System.Data.DataView.RowFilter%2A> właściwości na pusty ciąg:  
  
 [!code-csharp[DP DataView Samples#LDVClearRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearrowfilter)]
 [!code-vb[DP DataView Samples#LDVClearRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearrowfilter)]  
  
## <a name="see-also"></a>Zobacz też

- [Powiązanie danych i LINQ to DataSet](data-binding-and-linq-to-dataset.md)
- [Sortowanie za pomocą widoku danych](sorting-with-dataview-linq-to-dataset.md)
