---
title: Oracle REF CURSOR
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: cbf330ba381a825c2d16038c01d7bdc52bc8f482
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180884"
---
# <a name="oracle-ref-cursors"></a>Oracle REF CURSOR

.NET Framework Dostawca danych dla programu Oracle obsługuje typ danych **Cursor ref** firmy Oracle. Gdy dostawca danych jest używany do pracy z kursorami REF Oracle, należy wziąć pod uwagę następujące zachowania.  
  
> [!NOTE]
> Niektóre zachowania różnią się od tych Microsoft OLE DB Provider dla Oracle (MSDAORA I).  
  
- Ze względu na wydajność Dostawca danych dla programu Oracle nie wiąże się automatycznie z typem danych **kursora referencyjnego** , tak jak MSDAORA i, chyba że jawnie je określisz.  
  
- Dostawca danych nie obsługuje żadnych sekwencji unikowych ODBC, w tym kontrolki ucieczki {zestaw wyników} służącej do określania parametrów REF CURSOR.  
  
- Aby wykonać procedurę przechowywaną, która zwraca kursory REF, należy zdefiniować parametry w <xref:System.Data.OracleClient.OracleParameterCollection> z <xref:System.Data.OracleClient.OracleType> **kursorem** i a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> . **Output** Dostawca danych obsługuje Powiązywanie kursorów REFERENCYJNych jako parametrów wyjściowych. Dostawca nie obsługuje REFERENCYJNych kursorów jako parametrów wejściowych.  
  
- Uzyskanie <xref:System.Data.OracleClient.OracleDataReader> z wartości parametru nie jest obsługiwane. Wartości są typu po wykonaniu <xref:System.DBNull> polecenia.  
  
- Jedyną wartością wyliczenia **CommandBehavior** , która działa z kursorami ref (na przykład gdy wywoływanie <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> ) jest **CloseConnection**; wszystkie pozostałe są ignorowane.  
  
- Kolejność kursorów REF w **OracleDataReader** zależy od kolejności parametrów w **OracleParameterCollection**. <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A>Właściwość jest ignorowana.  
  
- Typ danych **tabeli** pl/SQL nie jest obsługiwany. Jednak kursory REF są bardziej wydajne. Jeśli musisz użyć typu danych **tabeli** , użyj OLE DB .NET Dostawca danych z msdaora i.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Przykłady REF CURSOR](ref-cursor-examples.md)  
 Zawiera trzy przykłady, które demonstrują korzystanie z kursorów REF.  
  
 [Parametry kursora REF CURSOR w OracleDataReader](ref-cursor-parameters-in-an-oracledatareader.md)  
 Pokazuje, jak wykonać procedurę składowaną PL/SQL, która zwraca parametr REF CURSOR i odczytuje wartość jako **OracleDataReader**.  
  
 [Pobieranie danych z wielu kursorów REF CURSOR przy użyciu OracleDataReader](retrieving-data-from-multiple-ref-cursors.md)  
 Demonstruje sposób wykonywania procedury składowanej PL/SQL, która zwraca dwa parametry REF CURSOR i odczytuje wartości przy użyciu **OracleDataReader**.  
  
 [Wypełnianie zestawu danych przy użyciu przynajmniej jednego kursora REF CURSOR](filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Demonstruje sposób wykonywania procedury składowanej PL/SQL, która zwraca dwa parametry kursora REF, i wypełnia <xref:System.Data.DataSet> z zwracanymi wierszami.  
  
## <a name="see-also"></a>Zobacz też

- [Oracle i ADO.NET](oracle-and-adonet.md)
- [Omówienie ADO.NET](ado-net-overview.md)
