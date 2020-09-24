---
title: Modyfikowanie danych za pomocą procedur składowanych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 65116a48533fd6ce86894c6a4522929285f8e1f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150755"
---
# <a name="modifying-data-with-stored-procedures"></a>Modyfikowanie danych za pomocą procedur składowanych

Procedury składowane mogą akceptować dane jako parametry wejściowe i mogą zwracać dane jako parametry wyjściowe, zestawy wyników lub wartości zwracane. W poniższym przykładzie pokazano, jak ADO.NET wysyła i odbiera parametry wejściowe, parametry wyjściowe oraz wartości zwracane. Przykład wstawia nowy rekord do tabeli, w której kolumna klucza podstawowego jest kolumną tożsamości w bazie danych SQL Server.  
  
> [!NOTE]
> Jeśli używasz SQL Server procedur składowanych do edytowania lub usuwania danych przy użyciu programu <xref:System.Data.SqlClient.SqlDataAdapter> , upewnij się, że w definicji procedury składowanej nie używasz opcji SET NOCOUNT on. Powoduje to, że liczba zwracanych wierszy jest równa zero, która `DataAdapter` interpretuje jako konflikt współbieżności. W takim przypadku <xref:System.Data.DBConcurrencyException> zostanie zgłoszone zdarzenie.  
  
## <a name="example"></a>Przykład  

 Przykład używa następującej procedury składowanej, aby wstawić nową kategorię do tabeli kategorii **Northwind** **Categories** . Procedura składowana przyjmuje wartość w kolumnie **CategoryName** jako parametr wejściowy i używa funkcji SCOPE_IDENTITY (), aby pobrać nową wartość pola tożsamości, **IDkategorii**i zwrócić go w parametrze wyjściowym. Instrukcja RETURN używa funkcji @, @ROWCOUNT Aby zwrócić liczbę wstawionych wierszy.  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 Poniższy przykład kodu używa `InsertCategory` procedury składowanej pokazanej powyżej jako źródła dla <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> elementu <xref:System.Data.SqlClient.SqlDataAdapter> . `@Identity`Parametr wyjściowy zostanie odzwierciedlony w <xref:System.Data.DataSet> po wstawieniu rekordu do bazy danych, gdy `Update` <xref:System.Data.SqlClient.SqlDataAdapter> wywoływana jest metoda obiektu. Kod pobiera również wartość zwracaną.  
  
> [!NOTE]
> Podczas używania <xref:System.Data.OleDb.OleDbDataAdapter> , należy określić parametry z <xref:System.Data.ParameterDirection> **ReturnValue** przed innymi parametrami.  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Pobieranie i modyfikowanie danych ADO.NET](retrieving-and-modifying-data.md)
- [Elementy DataAdapter i DataReader](dataadapters-and-datareaders.md)
- [Wykonywanie polecenia](executing-a-command.md)
- [Omówienie ADO.NET](ado-net-overview.md)
