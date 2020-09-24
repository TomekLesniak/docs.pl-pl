---
title: Wykonywanie polecenia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
ms.openlocfilehash: d7d290c1c149f9eab2449c25e8d32f2568eb0277
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156462"
---
# <a name="executing-a-command"></a>Wykonywanie polecenia

Każdy dostawca danych .NET Framework dołączony do .NET Framework ma własny obiekt polecenia, który dziedziczy z <xref:System.Data.Common.DbCommand> . Dostawca danych .NET Framework dla OLE DB zawiera obiekt <xref:System.Data.OleDb.OleDbCommand> , .NET Framework dostawca danych dla SQL Server zawiera obiekt <xref:System.Data.SqlClient.SqlCommand> , .NET Framework dostawca danych dla ODBC zawiera obiekt <xref:System.Data.Odbc.OdbcCommand> , a .NET Framework dostawca danych dla programu Oracle zawiera <xref:System.Data.OracleClient.OracleCommand> obiekt. Każdy z tych obiektów uwidacznia metody wykonywania poleceń na podstawie typu polecenia i żądanej wartości zwracanej, zgodnie z opisem w poniższej tabeli.  
  
|Polecenie|Wartość zwracana|  
|-------------|------------------|  
|`ExecuteReader`|Zwraca `DataReader` obiektu.|  
|`ExecuteScalar`|Zwraca pojedynczą wartość skalarną.|  
|`ExecuteNonQuery`|Wykonuje polecenie, które nie zwraca żadnych wierszy.|  
|`ExecuteXMLReader`|Zwraca wartość <xref:System.Xml.XmlReader> . Dostępne tylko dla `SqlCommand` obiektu.|  
  
 Każdy obiekt polecenia o jednoznacznie określonym typie obsługuje również <xref:System.Data.CommandType> Wyliczenie, które określa sposób interpretacji ciągu polecenia, zgodnie z opisem w poniższej tabeli.  
  
|CommandType|Opis|  
|-----------------|-----------------|  
|`Text`|Polecenie SQL definiujące instrukcje do wykonania w źródle danych.|  
|`StoredProcedure`|Nazwa procedury składowanej. Można użyć `Parameters` Właściwości polecenia, aby uzyskać dostęp do parametrów wejściowych i wyjściowych oraz zwracanych wartości, niezależnie od tego, która `Execute` Metoda jest wywoływana. W przypadku używania `ExecuteReader` wartości zwracane i parametry wyjściowe nie będą dostępne do momentu `DataReader` zamknięcia.|  
|`TableDirect`|Nazwa tabeli.|  
  
## <a name="example"></a>Przykład  

 Poniższy przykład kodu demonstruje sposób tworzenia <xref:System.Data.SqlClient.SqlCommand> obiektu do wykonania procedury składowanej przez ustawienie jej właściwości. <xref:System.Data.SqlClient.SqlParameter>Obiekt jest używany do określenia parametru wejściowego procedury składowanej. Polecenie jest wykonywane przy użyciu <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> metody, a dane wyjściowe z programu <xref:System.Data.SqlClient.SqlDataReader> są wyświetlane w oknie konsoli.  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a>Rozwiązywanie problemów z poleceniami  

 .NET Framework Dostawca danych do SQL Server dodaje liczniki wydajności, aby umożliwić wykrywanie sporadycznych problemów związanych z operacjami zakończonymi niepowodzeniem. Aby uzyskać więcej informacji, zobacz [liczniki wydajności](performance-counters.md).  
  
## <a name="see-also"></a>Zobacz też

- [Polecenia i parametry](commands-and-parameters.md)
- [Elementy DataAdapter i DataReader](dataadapters-and-datareaders.md)
- [Omówienie ADO.NET](ado-net-overview.md)
