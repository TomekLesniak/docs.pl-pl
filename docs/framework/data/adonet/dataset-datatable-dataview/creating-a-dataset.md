---
title: Tworzenie elementu DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: cbf652cc3742cb880fe060743dcc2615e6283ca7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202360"
---
# <a name="creating-a-dataset"></a>Tworzenie elementu DataSet

Można utworzyć wystąpienie obiektu <xref:System.Data.DataSet> przez wywołanie <xref:System.Data.DataSet> konstruktora. Opcjonalnie można określić argument nazwy. Jeśli nie określisz nazwy dla <xref:System.Data.DataSet> , nazwa zostanie ustawiona na "NewDataSet".  
  
 Możesz również utworzyć nowy <xref:System.Data.DataSet> oparty na istniejącym <xref:System.Data.DataSet> . Nowy <xref:System.Data.DataSet> może być dokładną kopią istniejącej <xref:System.Data.DataSet> ; klon <xref:System.Data.DataSet> , który kopiuje strukturę relacyjną lub schemat, ale nie zawiera żadnych danych z istniejącego <xref:System.Data.DataSet> lub podzestawu <xref:System.Data.DataSet> , zawierający tylko zmodyfikowane wiersze z istniejących <xref:System.Data.DataSet> przy użyciu <xref:System.Data.DataSet.GetChanges%2A> metody. Aby uzyskać więcej informacji, zobacz [kopiowanie zawartości zestawu danych](copying-dataset-contents.md).  
  
 Poniższy przykład kodu demonstruje sposób konstruowania wystąpienia obiektu <xref:System.Data.DataSet> .  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a>Zobacz też

- [Wypełnianie zestawu danych z elementu DataAdapter](../populating-a-dataset-from-a-dataadapter.md)
- [Elementy DataSet, DataTable i DataView](index.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
