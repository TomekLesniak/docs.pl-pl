---
title: Ładowanie danych do zestawu danych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: c870cabc875aa0152910ce916819fb1ff1c018f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166719"
---
# <a name="loading-data-into-a-dataset"></a>Ładowanie danych do zestawu danych

<xref:System.Data.DataSet>Aby można było wykonać zapytanie dotyczące obiektu przy użyciu LINQ to DataSet, należy najpierw wypełnić obiekt. Istnieje kilka różnych sposobów wypełnienia <xref:System.Data.DataSet> . Na przykład można użyć [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] programu do wysyłania zapytań do bazy danych i załadowania wyników do <xref:System.Data.DataSet> . Aby uzyskać więcej informacji, zobacz [LINQ to SQL](./sql/linq/index.md).  
  
 Innym typowym sposobem ładowania danych do programu <xref:System.Data.DataSet> jest użycie <xref:System.Data.Common.DataAdapter> klasy do pobierania danych z bazy danych. Jest to zilustrowane w poniższym przykładzie.  
  
## <a name="example"></a>Przykład  

 W tym przykładzie używa <xref:System.Data.Common.DataAdapter> się do wysyłania zapytań do bazy danych AdventureWorks o informacje o sprzedaży z roku 2002 i ładowania wyników do programu <xref:System.Data.DataSet> . Po wypełnieniu <xref:System.Data.DataSet> można napisać zapytania do niego przy użyciu LINQ to DataSet. `FillDataSet`Metoda w tym przykładzie jest używana w przykładowych kwerendach [LINQ to DataSet przykładów](linq-to-dataset-examples.md). Aby uzyskać więcej informacji, zobacz [wykonywanie zapytania dotyczącego zestawów danych](querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>Zobacz też

- [Omówienie LINQ to DataSet](linq-to-dataset-overview.md)
- [Wykonywanie zapytania do zestawów danych](querying-datasets-linq-to-dataset.md)
- [Przykłady LINQ to DataSet](linq-to-dataset-examples.md)
