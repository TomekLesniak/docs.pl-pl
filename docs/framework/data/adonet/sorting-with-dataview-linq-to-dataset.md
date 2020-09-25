---
title: Sortowanie za pomocą widoku danych (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
ms.openlocfilehash: d80c00a4b06a31f61a521e7206c204c02106748a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175281"
---
# <a name="sorting-with-dataview-linq-to-dataset"></a>Sortowanie za pomocą widoku danych (LINQ to DataSet)

Możliwość sortowania danych na podstawie określonych kryteriów, a następnie prezentowania danych do klienta za pośrednictwem kontrolki interfejsu użytkownika jest ważnym aspektem powiązania danych. <xref:System.Data.DataView> oferuje kilka sposobów sortowania danych i zwracania wierszy danych uporządkowanych według określonych kryteriów określania kolejności. Oprócz funkcji sortowania opartych na ciągach, można <xref:System.Data.DataView> także używać wyrażeń programu Query-Integrated Language (LINQ) dla kryteriów sortowania. Wyrażenia LINQ umożliwiają znacznie bardziej skomplikowane i zaawansowane operacje sortowania niż sortowanie oparte na ciągach. W tym temacie opisano oba podejścia do sortowania przy użyciu <xref:System.Data.DataView> .  
  
## <a name="creating-dataview-from-a-query-with-sorting-information"></a>Tworzenie elementu DataView z zapytania z informacjami o sortowaniu  

 <xref:System.Data.DataView>Obiekt można utworzyć na podstawie zapytania LINQ to DataSet. Jeśli zapytanie zawiera <xref:System.Linq.Enumerable.OrderBy%2A> <xref:System.Linq.Enumerable.OrderByDescending%2A> klauzulę,, <xref:System.Linq.Enumerable.ThenBy%2A> lub, <xref:System.Linq.Enumerable.ThenByDescending%2A> wyrażenia w tych klauzulach są używane jako podstawa sortowania danych w <xref:System.Data.DataView> . Na przykład, jeśli zapytanie zawiera `Order By…` `Then By…` klauzulę i, wynikiem <xref:System.Data.DataView> byłyby zamówienie danych według określonych kolumn.  
  
 Sortowanie oparte na wyrażeniach oferuje bardziej zaawansowane i złożone sortowanie niż prostsze sortowanie oparte na ciągach. Należy zauważyć, że sortowanie oparte na ciągach i wyrażeniach wykluczają się wzajemnie. Jeśli parametr jest <xref:System.Data.DataView.Sort%2A> ustawiony po utworzeniu na podstawie <xref:System.Data.DataView> zapytania, filtr oparty na wyrażeniach wywnioskowany na podstawie zapytania jest wyczyszczony i nie można go zresetować.  
  
 Indeks dla obiektu <xref:System.Data.DataView> jest kompilowany zarówno podczas tworzenia, <xref:System.Data.DataView> jak i gdy dowolna z informacji o sortowaniu lub filtrowaniu jest modyfikowana. Najlepszą wydajność uzyskuje się, dostarczając kryteria sortowania w kwerendzie LINQ to DataSet, że <xref:System.Data.DataView> jest tworzona z i nie modyfikując informacji o sortowaniu w późniejszym czasie. Aby uzyskać więcej informacji, zobacz temat [wydajność widoku](dataview-performance.md)danych.  
  
> [!NOTE]
> W większości przypadków wyrażenia używane do sortowania nie powinny mieć efektów ubocznych i muszą być deterministyczne. Ponadto wyrażenia nie powinny zawierać żadnych logiki, które są zależne od ustawionej liczby wykonań, ponieważ operacje sortowania mogą być wykonywane dowolną liczbę razy.  
  
### <a name="example"></a>Przykład  

 Poniższy przykład wysyła zapytanie do tabeli SalesOrderHeader i porządkuje zwracane wiersze według daty zamówienia; tworzy <xref:System.Data.DataView> z tego zapytania i wiąże z <xref:System.Data.DataView> do <xref:System.Windows.Forms.BindingSource> .  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby)]  
  
### <a name="example"></a>Przykład  

 Poniższy przykład wysyła zapytanie do tabeli SalesOrderHeader i porządkuje zwrócony wiersz według łącznej kwoty należnej; tworzy <xref:System.Data.DataView> z tego zapytania i wiąże z <xref:System.Data.DataView> do <xref:System.Windows.Forms.BindingSource> .  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby2)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby2)]  
  
### <a name="example"></a>Przykład  

 Poniższy przykład wysyła zapytanie do tabeli SalesOrderDetail i porządkuje zwrócone wiersze według liczby porządkowej, a następnie według identyfikatora zamówienia sprzedaży; tworzy <xref:System.Data.DataView> z tego zapytania i wiąże z <xref:System.Data.DataView> do <xref:System.Windows.Forms.BindingSource> .  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderbythenby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderbythenby)]  
  
## <a name="using-the-string-based-sort-property"></a>Używanie właściwości sortowania opartej na ciągach  

 Funkcja sortowania oparta na ciągach <xref:System.Data.DataView> nadal działa z LINQ to DataSet. Po <xref:System.Data.DataView> utworzeniu z kwerendy LINQ to DataSet można użyć <xref:System.Data.DataView.Sort%2A> właściwości, aby ustawić sortowanie na <xref:System.Data.DataView> .  
  
 Funkcja sortowania oparta na ciągach i wyrażeniach wykluczają się wzajemnie. Ustawienie <xref:System.Data.DataView.Sort%2A> właściwości spowoduje wyczyszczenie opartego na wyrażeniach sortowania dziedziczone z zapytania, <xref:System.Data.DataView> z którego zostało utworzone.  
  
 Aby uzyskać więcej informacji o filtrowaniu opartym na ciągach <xref:System.Data.DataView.Sort%2A> , zobacz [Sortowanie i filtrowanie danych](./dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
### <a name="example"></a>Przykład  

 W poniższym przykładzie następuje utworzenie <xref:System.Data.DataView> z tabeli Contact i sortowanie wierszy według nazwiska w kolejności malejącej, a następnie imię i nazwisko w kolejności rosnącej:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
### <a name="example"></a>Przykład  

 Poniższy przykład wysyła zapytanie do tabeli Contact dla ostatnich nazw, które zaczynają się literą "S".  Element <xref:System.Data.DataView> jest tworzony na podstawie tego zapytania i powiązany z <xref:System.Windows.Forms.BindingSource> obiektem.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="clearing-the-sort"></a>Czyszczenie sortowania  

 Informacje o sortowaniu na stronie <xref:System.Data.DataView> można wyczyścić po ustawieniu jej przy użyciu <xref:System.Data.DataView.Sort%2A> właściwości. Istnieją dwa sposoby wyczyszczenia informacji o sortowaniu w programie <xref:System.Data.DataView> :  
  
- Ustaw <xref:System.Data.DataView.Sort%2A> Właściwość na wartość `null` .  
  
- Ustaw <xref:System.Data.DataView.Sort%2A> Właściwość na pusty ciąg.  
  
### <a name="example"></a>Przykład  

 Poniższy przykład tworzy na <xref:System.Data.DataView> podstawie zapytania i czyści sortowanie przez ustawienie <xref:System.Data.DataView.Sort%2A> właściwości na pusty ciąg:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### <a name="example"></a>Przykład  

 Poniższy przykład tworzy <xref:System.Data.DataView> z tabeli Contact i ustawia <xref:System.Data.DataView.Sort%2A> Właściwość do sortowania według nazwiska w kolejności malejącej. Informacje o sortowaniu są następnie wyczyszczone przez ustawienie <xref:System.Data.DataView.Sort%2A> właściwości na `null` :  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## <a name="see-also"></a>Zobacz też

- [Powiązanie danych i LINQ to DataSet](data-binding-and-linq-to-dataset.md)
- [Filtrowanie za pomocą widoku danych](filtering-with-dataview-linq-to-dataset.md)
- [Sortowanie danych](/previous-versions/visualstudio/visual-studio-2013/bb546145(v=vs.120))
