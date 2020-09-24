---
title: Nawigowanie w elementach DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 9b7ed4ef1dbe141d8f6a1b6c6b9af2fd89e6c7af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148311"
---
# <a name="navigating-datatables"></a>Nawigowanie w elementach DataTable

<xref:System.Data.DataTableReader>Uzyskuje zawartość co najmniej jednego <xref:System.Data.DataTable> obiektu w postaci co najmniej jednego zestawu wyników tylko do odczytu.  
  
 Obiekt <xref:System.Data.DataTableReader> może zawierać wiele zestawów wyników, jeśli jest tworzony przy użyciu <xref:System.Data.DataSet.CreateDataReader%2A> metody. Jeśli istnieje więcej niż jeden zestaw wyników, <xref:System.Data.DataTableReader.NextResult%2A> Metoda przesuwa kursor do następnego zestawu wyników. Jest to proces tylko do przesyłania dalej. Nie można powrócić do poprzedniego zestawu wyników.  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie `TestConstructor` Metoda tworzy dwa <xref:System.Data.DataTable> wystąpienia. Aby przedstawić ten Konstruktor dla <xref:System.Data.DataTableReader> klasy, przykład tworzy nowy **DataTableReader** na podstawie tablicy zawierającej dwie **tabele DataTables**i wykonuje prostą operację, drukując zawartość z pierwszych kilku kolumn do okna konsoli.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Elementy DataTableReader](datatablereaders.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
