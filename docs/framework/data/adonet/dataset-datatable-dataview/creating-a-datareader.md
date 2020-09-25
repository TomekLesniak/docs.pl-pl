---
title: Tworzenie elementu DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 3af6ae3a8f4ecc3ec34c186ce55c1c77c27514a9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202334"
---
# <a name="creating-a-datareader"></a>Tworzenie elementu DataReader

<xref:System.Data.DataTable>Klasy i <xref:System.Data.DataSet> mają <xref:System.Data.DataTable.CreateDataReader%2A> metodę, która zwraca zawartość <xref:System.Data.DataTable> lub zawartość <xref:System.Data.DataSet> <xref:System.Data.DataSet.Tables%2A> kolekcji obiektu jako co najmniej jeden zestaw wyników tylko do odczytu.  
  
## <a name="example"></a>Przykład  

 Następująca aplikacja konsolowa tworzy <xref:System.Data.DataTable> wystąpienie. Następnie przykład przekazuje wypełniony <xref:System.Data.DataTable> do procedury, która wywołuje <xref:System.Data.DataTable.CreateDataReader%2A> metodę, która wykonuje iterację przez wyniki zawarte w <xref:System.Data.DataTableReader> .  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 W przykładzie są wyświetlane następujące dane wyjściowe w oknie konsoli:  
  
```output  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [Elementy DataTableReader](datatablereaders.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
