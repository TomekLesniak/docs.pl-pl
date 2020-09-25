---
title: Pola ogólne i metody SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: 9deda11592389dd799477bdc027d59a0be0036da
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200657"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Pola ogólne i metody SetField (LINQ to DataSet)

LINQ to DataSet dostarcza metody rozszerzające do <xref:System.Data.DataRow> klasy w celu uzyskania dostępu do wartości kolumn: <xref:System.Data.DataRowExtensions.Field%2A> metody i <xref:System.Data.DataRowExtensions.SetField%2A> metody. Te metody zapewniają łatwiejszy dostęp do wartości kolumn dla deweloperów, szczególnie w odniesieniu do wartości null. <xref:System.Data.DataSet>Używa <xref:System.DBNull.Value?displayProperty=nameWithType> do reprezentowania wartości null, podczas gdy LINQ używa <xref:System.Nullable> typów i <xref:System.Nullable%601> . Użycie metody dostępu do istniejącej kolumny w programie <xref:System.Data.DataRow> wymaga, aby rzutować obiekt zwracany na odpowiedni typ. Jeśli określone pole w <xref:System.Data.DataRow> może mieć wartość null, należy jawnie sprawdzić pod kątem wartości null, ponieważ zwracają <xref:System.DBNull.Value?displayProperty=nameWithType> i niejawnie Rzutowanie na inny typ zgłasza <xref:System.InvalidCastException> . W poniższym przykładzie, jeśli <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> Metoda nie została użyta do sprawdzenia wartości null, wyjątek zostałby wygenerowany, jeśli indeksator zwrócił <xref:System.DBNull.Value?displayProperty=nameWithType> i próbował wykonać rzutowanie do <xref:System.String> .  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 <xref:System.Data.DataRowExtensions.Field%2A>Metoda zapewnia dostęp do wartości kolumn a <xref:System.Data.DataRow> i <xref:System.Data.DataRowExtensions.SetField%2A> Ustawia wartości kolumn w <xref:System.Data.DataRow> . <xref:System.Data.DataRowExtensions.Field%2A>Metody i <xref:System.Data.DataRowExtensions.SetField%2A> metody obsługują typy wartości null, więc nie trzeba jawnie sprawdzać wartości null tak jak w poprzednim przykładzie. Obie metody są metodami ogólnymi, więc nie trzeba rzutować zwracanego typu.  
  
 W poniższym przykładzie zastosowano <xref:System.Data.DataRowExtensions.Field%2A> metodę.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Należy zauważyć, że typ danych określony w parametrze ogólnym `T` <xref:System.Data.DataRowExtensions.Field%2A> metody i <xref:System.Data.DataRowExtensions.SetField%2A> metody musi być zgodny z typem podstawowej wartości. W przeciwnym razie <xref:System.InvalidCastException> zostanie zgłoszony wyjątek. Określona nazwa kolumny musi być również zgodna z nazwą kolumny w <xref:System.Data.DataSet> lub <xref:System.ArgumentException> zostanie wygenerowane. W obu przypadkach wyjątek jest zgłaszany w czasie wykonywania podczas wyliczania danych podczas wykonywania zapytania.  
  
 <xref:System.Data.DataRowExtensions.SetField%2A>Sama metoda nie wykonuje żadnych konwersji typów. Nie oznacza to jednak, że konwersja typu nie zostanie wykonana. <xref:System.Data.DataRowExtensions.SetField%2A>Metoda ujawnia zachowanie ADO.NET <xref:System.Data.DataRow> klasy. Konwersja typu może być wykonywana przez <xref:System.Data.DataRow> obiekt i przekonwertowana wartość zostałaby następnie zapisana do <xref:System.Data.DataRow> obiektu.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataRowExtensions>
