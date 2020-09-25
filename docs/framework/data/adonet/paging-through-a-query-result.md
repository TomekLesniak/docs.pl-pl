---
title: Stronicowanie za pośrednictwem wyniku zapytania
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 065b509d8385ee37b2a86587f520b5fd3207ceff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186955"
---
# <a name="paging-through-a-query-result"></a>Stronicowanie za pośrednictwem wyniku zapytania

Stronicowanie za pomocą wyniku zapytania jest procesem zwracającym wyniki zapytania w mniejszych podzestawach danych lub stronach. Jest to typowa metoda wyświetlania wyników dla użytkownika w małych i łatwych do zarządzania fragmentach.  
  
 Obiekt **DataAdapter** udostępnia funkcję do zwracania tylko strony danych, przez przeciążenia metody **Fill** . Jednak może to nie być najlepszym wyborem w przypadku stronicowania za pomocą dużych wyników zapytania, ponieważ, chociaż element **DataAdapter** wypełnia obiekt docelowy <xref:System.Data.DataTable> lub <xref:System.Data.DataSet> tylko z żądanymi rekordami, zasoby, które mają zwrócić całe zapytanie, są nadal używane. Aby zwrócić stronę danych ze źródła danych bez użycia zasobów do zwrócenia całego zapytania, należy określić dodatkowe kryteria dla zapytania, które zmniejszają liczbę zwracanych wierszy tylko do wymaganych.  
  
 Aby użyć metody **Fill** do zwrócenia strony danych, należy określić parametr **startRecord** dla pierwszego rekordu na stronie danych oraz parametr **MaxRecords** , dla liczby rekordów na stronie danych.  
  
 Poniższy przykład kodu pokazuje, jak używać metody **Fill** do zwrócenia pierwszej strony wyniku zapytania, gdzie rozmiar strony jest pięcioma rekordami.  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 W poprzednim przykładzie **zestaw danych** zawiera tylko pięć rekordów, ale zwracana jest cała tabela **Orders** . Aby wypełnić **zestaw danych** tymi samymi pięcioma rekordami, ale zwróć tylko pięć rekordów, użyj klauzul Top i WHERE w instrukcji języka SQL, jak w poniższym przykładzie kodu.  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 Należy pamiętać, że podczas tworzenia stronicowania w wyniku zapytania w ten sposób należy zachować unikatowy identyfikator, który porządkuje wiersze, aby przekazać unikatowy identyfikator do polecenia w celu zwrócenia następnej strony rekordów, jak pokazano w poniższym przykładzie kodu.  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 Aby zwrócić następną stronę rekordów przy użyciu przeciążenia metody **Fill** , która przyjmuje parametry **startRecord** i **MaxRecords** , zwiększ bieżący indeks rekordu przez rozmiar strony i wypełnij tabelę. Należy pamiętać, że serwer bazy danych zwraca całe wyniki zapytania, nawet wtedy, gdy tylko jedna strona rekordów jest dodawana do **zestawu danych**. W poniższym przykładzie kodu wiersze tabeli są czyszczone, zanim zostaną wypełnione następną stroną danych. Możesz chcieć zachować określoną liczbę zwracanych wierszy w lokalnej pamięci podręcznej, aby zredukować podróże do serwera bazy danych.  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 Aby zwrócić następną stronę rekordów bez konieczności zwrócenia przez serwer bazy danych całego zapytania, określ kryteria ograniczające do instrukcji SELECT. Ponieważ w powyższym przykładzie zachowano ostatni zwrócony rekord, można go użyć w klauzuli WHERE, aby określić punkt początkowy zapytania, jak pokazano w poniższym przykładzie kodu.  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a>Zobacz też

- [Elementy DataAdapter i DataReader](dataadapters-and-datareaders.md)
- [Omówienie ADO.NET](ado-net-overview.md)
