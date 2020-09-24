---
title: Usuwanie elementu DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 2092d7319a398bbdeaef764d677818f78ddf9de9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153355"
---
# <a name="datarow-deletion"></a>Usuwanie elementu DataRow

Istnieją dwie metody, których można użyć, aby usunąć <xref:System.Data.DataRow> obiekt z <xref:System.Data.DataTable> obiektu: metodę **Remove** <xref:System.Data.DataRowCollection> obiektu i <xref:System.Data.DataRow.Delete%2A> metodę obiektu **DataRow** . Natomiast <xref:System.Data.DataRowCollection.Remove%2A> Metoda usuwa element **DataRow** z obiektu **DataRowCollection**, <xref:System.Data.DataRow.Delete%2A> Metoda oznacza tylko wiersz do usunięcia. Faktyczne usunięcie odbywa się, gdy aplikacja wywołuje metodę **AcceptChanges** . Za pomocą programu <xref:System.Data.DataRow.Delete%2A> można programowo sprawdzić, które wiersze są oznaczone do usunięcia przed ich faktycznym usunięciem. Gdy wiersz jest oznaczony do usunięcia, jego <xref:System.Data.DataRow.RowState%2A> Właściwość jest ustawiona na <xref:System.Data.DataRow.Delete%2A> .  
  
 Nie <xref:System.Data.DataRow.Delete%2A> <xref:System.Data.DataRowCollection.Remove%2A> należy wywoływać ani wywołać w pętli Foreach podczas iterowania za pomocą <xref:System.Data.DataRowCollection> obiektu. <xref:System.Data.DataRow.Delete%2A> ani <xref:System.Data.DataRowCollection.Remove%2A> modyfikować stanu kolekcji.  
  
 W przypadku używania <xref:System.Data.DataSet> elementu **DataTable** w połączeniu z elementem **DataAdapter** i relacyjnym źródłem danych Użyj metody **delete** obiektu **DataRow** , aby usunąć wiersz. Metoda **delete** oznacza wiersz jako **usunięty** w **zestawie danych** lub **DataTable** , ale nie usuwa go. Zamiast tego, gdy element **DataAdapter** napotka wiersz oznaczony jako **usunięty**, wykonuje jego metodę **DeleteCommand** , aby usunąć wiersz w źródle danych. Wiersz można następnie trwale usunąć za pomocą metody **AcceptChanges** . Jeśli używasz **Usuń** do usunięcia wiersza, wiersz zostanie usunięty całkowicie z tabeli, ale element **DataAdapter** nie usunie wiersza ze źródła danych.  
  
 Metoda **Remove** obiektu **DataRowCollection** przyjmuje element **DataRow** jako argument i usuwa go z kolekcji, jak pokazano w poniższym przykładzie.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 W poniższym przykładzie pokazano, jak wywołać metodę **delete** dla elementu **DataRow** , aby zmienić **RowState** na **usunięty**.  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Jeśli wiersz jest oznaczony do usunięcia i wywoływana jest metoda **AcceptChanges** obiektu **DataTable** , wiersz zostanie usunięty z **tabeli DataTable**. Z drugiej strony, jeśli wywołasz **RejectChanges**, **RowState** wiersza powróci do tego, co było przed oznaczeniem jako **usunięte**.  
  
> [!NOTE]
> Jeśli **RowState** elementu **DataRow** zostanie **dodany**, oznacza to, że został on właśnie dodany do tabeli, a następnie jest oznaczony jako **usunięty**, zostanie usunięty z tabeli.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Operowanie na danych w elemencie DataTable](manipulating-data-in-a-datatable.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
