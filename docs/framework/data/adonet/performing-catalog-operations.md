---
title: Wykonywanie operacji katalogu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: 802762592a63a2046abcde8ed83ac67be47faf96
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161649"
---
# <a name="performing-catalog-operations"></a>Wykonywanie operacji katalogu

Aby wykonać polecenie modyfikacji bazy danych lub wykazu, takie jak CREATE TABLE lub CREATE PROCEDURe, Utwórz obiekt **Command** przy użyciu odpowiednich instrukcji SQL i obiektu **Connection** . Wykonaj polecenie za pomocą metody **ExecuteNonQuery** obiektu **Command** .  
  
 Poniższy przykład kodu tworzy procedurę przechowywaną w bazie danych Microsoft SQL Server.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a>Zobacz też

- [Używanie poleceń do modyfikacji danych](using-commands-to-modify-data.md)
- [Polecenia i parametry](commands-and-parameters.md)
- [Omówienie ADO.NET](ado-net-overview.md)
