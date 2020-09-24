---
title: Ograniczenia elementu DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 1224518a9a16f48f770b6839317b9787da97377b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153277"
---
# <a name="datatable-constraints"></a>Ograniczenia elementu DataTable

Możesz użyć ograniczeń, aby wymusić ograniczenia dotyczące danych w <xref:System.Data.DataTable> , aby zachować integralność danych. Ograniczenie jest automatyczną regułą stosowaną do kolumny lub powiązanych kolumn, która określa przebieg akcji, gdy wartość wiersza jest zmieniana. Ograniczenia są wymuszane, gdy `System.Data.DataSet.EnforceConstraints` Właściwość <xref:System.Data.DataSet> ma **wartość true**. Przykładowy kod, który pokazuje, jak ustawić `EnforceConstraints` Właściwość, można znaleźć w <xref:System.Data.DataSet.EnforceConstraints%2A> temacie Reference.  
  
 Istnieją dwa rodzaje ograniczeń w ADO.NET: <xref:System.Data.ForeignKeyConstraint> i <xref:System.Data.UniqueConstraint> . Domyślnie oba ograniczenia są tworzone automatycznie podczas tworzenia relacji między dwiema lub wieloma tabelami przez dodanie <xref:System.Data.DataRelation> do **zestawu danych**. Takie zachowanie można jednak wyłączyć, określając wartość w polu Wyłącz **ograniczenia**  =  **false** podczas tworzenia relacji.  
  
## <a name="foreignkeyconstraint"></a>Element ForeignKeyConstraint  

 **Element ForeignKeyConstraint** wymusza reguły dotyczące sposobu propagacji aktualizacji i usunięć do powiązanych tabel. Na przykład, jeśli wartość w wierszu jednej tabeli jest aktualizowana lub usuwana, a ta sama wartość jest również używana w co najmniej jednej pokrewnych tabelach, **element ForeignKeyConstraint** określa, co się dzieje w tabelach pokrewnych.  
  
 <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A>Właściwości i <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> **element ForeignKeyConstraint** definiują akcję do wykonania, gdy użytkownik próbuje usunąć lub zaktualizować wiersz w powiązanej tabeli. W poniższej tabeli opisano różne ustawienia dostępne dla właściwości **DeleteRule** i **UpdateRule** **element ForeignKeyConstraint**.  
  
|Ustawienie reguły|Opis|  
|------------------|-----------------|  
|**Cascade**|Usuń lub zaktualizuj powiązane wiersze.|  
|**SetNull**|Ustaw wartości w powiązanych wierszach na wartość **DBNull**.|  
|**SetDefault**|Ustaw wartości domyślne w powiązanych wierszach.|  
|**Brak**|Nie podejmuj żadnych działań w odniesieniu do powiązanych wierszy. Jest to opcja domyślna.|  
  
 **Element ForeignKeyConstraint** może ograniczyć, a także propagowanie zmian w powiązanych kolumnach. W zależności od właściwości ustawionych dla **element ForeignKeyConstraint** kolumny, jeśli właściwość **EnforceConstraints** **zestawu danych** ma **wartość true**, wykonanie niektórych operacji w wierszu nadrzędnym spowoduje wyjątek. Na przykład jeśli właściwość **DeleteRule** elementu **element ForeignKeyConstraint** ma **wartość None**, nie można usunąć wiersza nadrzędnego, jeśli ma on wszystkie wiersze podrzędne.  
  
 Można utworzyć ograniczenie klucza obcego między pojedynczymi kolumnami lub między tablicami kolumn za pomocą konstruktora **element ForeignKeyConstraint** . Przekaż otrzymany obiekt **element ForeignKeyConstraint** do metody **Add** właściwości **ograniczenia** tabeli, która jest elementem **ConstraintCollection**. Można również przekazać argumenty konstruktora do kilku przeciążeń metody **Add** obiektu **ConstraintCollection** , aby utworzyć **element ForeignKeyConstraint**.  
  
 Podczas tworzenia elementu **element ForeignKeyConstraint**można przekazać wartości **DeleteRule** i **UpdateRule** do konstruktora jako argumenty lub ustawić je jako właściwości, tak jak w poniższym przykładzie (gdzie wartość **DeleteRule** jest ustawiona na **none**).  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a>AcceptRejectRule  

 Zmiany w wierszach można zaakceptować przy użyciu **metody AcceptChanges** lub anulowane przy użyciu **metody RejectChanges** **zestawu danych**, **DataTable**lub **DataRow**. Gdy **zestaw danych** zawiera **ForeignKeyConstraints**, wywoływanie metod **AcceptChanges** lub **RejectChanges** wymusza **AcceptRejectRule**. Właściwość **AcceptRejectRule** **element ForeignKeyConstraint** określa, która akcja zostanie podjęta w wierszach podrzędnych w przypadku wywołania metody **AcceptChanges** lub **RejectChanges** w wierszu nadrzędnym.  
  
 W poniższej tabeli wymieniono dostępne ustawienia dla **AcceptRejectRule**.  
  
|Ustawienie reguły|Opis|  
|------------------|-----------------|  
|**Cascade**|Akceptowanie lub odrzucanie zmian w wierszach podrzędnych.|  
|**Brak**|Nie podejmuj żadnych działań w wierszach podrzędnych. Jest to opcja domyślna.|  
  
### <a name="example"></a>Przykład  

 Poniższy przykład tworzy <xref:System.Data.ForeignKeyConstraint> , ustawia kilka jego właściwości, w tym <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A> i dodaje go do <xref:System.Data.ConstraintCollection> <xref:System.Data.DataTable> obiektu.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  

 Obiekt **UniqueConstraint** , który można przypisać do pojedynczej kolumny lub do tablicy kolumn w **tabeli DataTable**, zapewnia, że wszystkie dane w określonej kolumnie lub kolumnach są unikatowe dla każdego wiersza. Można utworzyć unikatowe ograniczenie dla kolumny lub tablicy kolumn za pomocą konstruktora **UniqueConstraint** . Przekaż otrzymany obiekt **UniqueConstraint** do metody **Add** właściwości **ograniczenia** tabeli, która jest elementem **ConstraintCollection**. Można również przekazać argumenty konstruktora do kilku przeciążeń metody **Add** obiektu **ConstraintCollection** , aby utworzyć **UniqueConstraint**. Podczas tworzenia **UniqueConstraint** dla kolumny lub kolumn można opcjonalnie określić, czy kolumna lub kolumny są kluczem podstawowym.  
  
 Możesz również utworzyć unikatowe ograniczenie dla kolumny, ustawiając właściwość **Unique** kolumny na **wartość true**. Alternatywnie, ustawienie właściwości **Unique** pojedynczej kolumny na **false** usuwa wszelkie unikatowe ograniczenia, które mogą istnieć. Definiowanie kolumny lub kolumn jako klucza podstawowego dla tabeli spowoduje automatyczne utworzenie unikatowego ograniczenia dla określonej kolumny lub kolumny. Jeśli usuniesz kolumnę z właściwości **PrimaryKey** **elementu DataTable**, **UniqueConstraint** zostanie usunięta.  
  
 Poniższy przykład tworzy **UniqueConstraint** dla dwóch kolumn tabeli **DataTable**.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]
    {custTable.Columns["CustomerID"],
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [Definicja schematu elementu DataTable](datatable-schema-definition.md)
- [Elementy DataSet, DataTable i DataView](index.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
