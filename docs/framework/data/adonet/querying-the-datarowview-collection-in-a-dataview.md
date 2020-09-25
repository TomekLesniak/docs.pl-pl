---
title: Wykonywanie zapytania do kolekcji DataRowView w widoku danych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b9070a12-1094-44d6-bb87-a23b50bcb0af
ms.openlocfilehash: 5757079bbc0ef8c498ea1db1a88f6b356ab0409e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172752"
---
# <a name="querying-the-datarowview-collection-in-a-dataview"></a>Wykonywanie zapytania do kolekcji DataRowView w widoku danych

<xref:System.Data.DataView>Uwidacznia wyliczalną kolekcję <xref:System.Data.DataRowView> obiektów. <xref:System.Data.DataRowView> reprezentuje dostosowany widok a <xref:System.Data.DataRow> i wyświetla określoną wersję programu <xref:System.Data.DataRow> w kontrolce. Tylko jedna wersja programu <xref:System.Data.DataRow> może być wyświetlana za pomocą kontrolki, takiej jak <xref:System.Windows.Forms.DataGridView> . Można uzyskać dostęp do programu <xref:System.Data.DataRow> , który jest udostępniany przez <xref:System.Data.DataRowView> <xref:System.Data.DataRowView.Row%2A> Właściwość <xref:System.Data.DataRowView> . Podczas wyświetlania wartości przy użyciu <xref:System.Data.DataRowView> , <xref:System.Data.DataView.RowStateFilter%2A> Właściwość określa, która wersja wiersza <xref:System.Data.DataRow> jest uwidoczniona. Aby uzyskać informacje o uzyskiwaniu dostępu do różnych wersji wierszy przy użyciu <xref:System.Data.DataRow> , zobacz [Stany wiersza i wersje wierszy](./dataset-datatable-dataview/row-states-and-row-versions.md). Ponieważ kolekcja <xref:System.Data.DataRowView> obiektów uwidocznionych przez <xref:System.Data.DataView> program jest wyliczalna, można użyć LINQ to DataSet, aby wykonać zapytanie.  
  
 Poniższy przykład wysyła zapytanie do `Product` tabeli w poszukiwaniu czerwonych produktów i tworzy tabelę z tej kwerendy. <xref:System.Data.DataView>Jest tworzony na podstawie tabeli, a <xref:System.Data.DataView.RowStateFilter%2A> Właściwość jest ustawiona do filtrowania dla usuniętych i zmodyfikowanych wierszy. <xref:System.Data.DataView>Jest on używany jako źródło w zapytaniu LINQ, a <xref:System.Data.DataRowView> obiekty, które zostały zmodyfikowane i usunięte są powiązane z <xref:System.Windows.Forms.DataGridView> kontrolką.  
  
 [!code-csharp[DP DataView Samples#QueryDataView2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview2)]
 [!code-vb[DP DataView Samples#QueryDataView2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview2)]  
  
 Poniższy przykład tworzy tabelę produktów z widoku, który jest powiązany z <xref:System.Windows.Forms.DataGridView> kontrolką. <xref:System.Data.DataView>Zapytanie jest wykonywane w przypadku produktów czerwonych, a uporządkowane wyniki są powiązane z <xref:System.Windows.Forms.DataGridView> kontrolką.  
  
 [!code-csharp[DP DataView Samples#QueryDataView1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview1)]
 [!code-vb[DP DataView Samples#QueryDataView1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview1)]  
  
## <a name="see-also"></a>Zobacz też

- [Powiązanie danych i LINQ to DataSet](data-binding-and-linq-to-dataset.md)
