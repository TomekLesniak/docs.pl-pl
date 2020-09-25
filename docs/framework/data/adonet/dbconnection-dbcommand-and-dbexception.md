---
title: DbConnection, DbCommand i DbException
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 58aab611-7e6f-4749-b983-28ab7ae87dbe
ms.openlocfilehash: 3075999c15fccc3a41c191297a146c362b3638e8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183328"
---
# <a name="dbconnection-dbcommand-and-dbexception"></a>DbConnection, DbCommand i DbException

Po utworzeniu i a można <xref:System.Data.Common.DbProviderFactory> <xref:System.Data.Common.DbConnection> następnie korzystać z poleceń i czytników danych w celu pobierania danych ze źródła danych.  
  
## <a name="retrieving-data-example"></a>Przykład pobierania danych  

 Ten przykład pobiera `DbConnection` obiekt jako argument. <xref:System.Data.Common.DbCommand>Jest tworzony w celu wybrania danych z tabeli Kategorie przez ustawienie <xref:System.Data.Common.DbCommand.CommandText%2A> instrukcji SELECT języka SQL. W kodzie założono, że tabela kategorie istnieje w źródle danych. Połączenie jest otwierane, a dane są pobierane przy użyciu <xref:System.Data.Common.DbDataReader> .  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/VB/source.vb#1)]  
  
## <a name="executing-a-command-example"></a>Wykonywanie przykładowego polecenia  

 Ten przykład pobiera `DbConnection` obiekt jako argument. Jeśli `DbConnection` jest prawidłowy, połączenie zostanie otwarte i <xref:System.Data.Common.DbCommand> zostanie utworzone i wykonane. <xref:System.Data.Common.DbCommand.CommandText%2A>Jest ustawiona na instrukcję SQL INSERT, która wykonuje Wstawianie do tabeli Categories w bazie danych Northwind. W kodzie założono, że baza danych Northwind istnieje w źródle danych i że składnia SQL używana w instrukcji INSERT jest prawidłowa dla określonego dostawcy. Błędy występujące w źródle danych są obsługiwane przez <xref:System.Data.Common.DbException> blok kodu, a wszystkie inne wyjątki są obsługiwane w <xref:System.Exception> bloku.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/VB/source.vb#1)]  
  
## <a name="handling-data-errors-with-dbexception"></a>Obsługa błędów danych przy użyciu DbException  

 <xref:System.Data.Common.DbException>Klasa jest klasą bazową dla wszystkich wyjątków zgłoszonych w imieniu źródła danych. Można jej użyć w kodzie obsługi wyjątków do obsługi wyjątków zgłoszonych przez różnych dostawców bez konieczności odwoływania się do określonej klasy wyjątków. Poniższy fragment kodu pokazuje, jak używać <xref:System.Data.Common.DbException> do wyświetlania informacji o błędach zwracanych przez źródło danych przy użyciu <xref:System.Exception.GetType%2A> <xref:System.Exception.Source%2A> właściwości,, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A> i <xref:System.Exception.Message%2A> . W danych wyjściowych zostanie wyświetlony typ błędu, Źródło wskazujące nazwę dostawcy, kod błędu i komunikat skojarzony z błędem.  
  
```vb  
Try  
    ' Do work here.  
Catch ex As DbException  
    ' Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType())  
    Console.WriteLine("Source: {0}", ex.Source)  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode)  
    Console.WriteLine("Message: {0}", ex.Message)  
Finally  
    ' Perform cleanup here.  
End Try  
```  
  
```csharp  
try  
{  
    // Do work here.  
}  
catch (DbException ex)  
{  
    // Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType());  
    Console.WriteLine("Source: {0}", ex.Source);  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode);  
    Console.WriteLine("Message: {0}", ex.Message);  
}  
finally  
{  
    // Perform cleanup here.  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- [DbProviderFactories](dbproviderfactories.md)
- [Uzyskiwanie DbProviderFactory](obtaining-a-dbproviderfactory.md)
- [Modyfikowanie danych za pomocą obiektu DbDataAdapter](modifying-data-with-a-dbdataadapter.md)
- [Omówienie ADO.NET](ado-net-overview.md)
