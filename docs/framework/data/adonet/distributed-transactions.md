---
title: Transakcje rozproszone
ms.date: 03/30/2017
ms.assetid: 718b257c-bcb2-408e-b004-a7b0adb1c176
ms.openlocfilehash: b6553d50039ca0f4888f0610b187c6b419a462b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153200"
---
# <a name="distributed-transactions"></a>Transakcje rozproszone

Transakcja to zestaw powiązanych zadań zakończonych powodzeniem (zatwierdzanie) lub niepowodzenie (przerwanie) jako jednostki, między innymi. *Transakcja rozproszona* to transakcja, która ma wpływ na kilka zasobów. Aby transakcja rozproszona została zatwierdzona, wszyscy uczestnicy muszą zagwarantować, że jakakolwiek zmiana danych będzie trwała. Zmiany muszą zostać zachowane niezależnie awarie systemu lub inne nieprzewidziane zdarzenia. Jeśli nawet pojedynczy uczestnik nie wykona tej gwarancji, cała transakcja zakończy się niepowodzeniem, a wszelkie zmiany danych w zakresie transakcji zostaną wycofane.  
  
> [!NOTE]
> Wyjątek zostanie wygenerowany, jeśli zostanie podjęta próba zatwierdzenia lub wycofania transakcji, jeśli `DataReader` zostanie ona uruchomiona, gdy transakcja jest aktywna.  
  
## <a name="working-with-systemtransactions"></a>Praca z System. Transactions  

 W .NET Framework transakcje rozproszone są zarządzane za pomocą interfejsu API w <xref:System.Transactions> przestrzeni nazw. <xref:System.Transactions>Interfejs API przekaże obsługę transakcji rozproszonych do monitora transakcji, takiego jak Microsoft Distributed Transaction Coordinator (MS DTC), gdy jest używanych wiele menedżerów zasobów trwałych. Aby uzyskać więcej informacji, zobacz temat [podstawy transakcji](../transactions/transaction-fundamentals.md).  
  
 W ADO.NET 2,0 wprowadzono obsługę rejestrowania w transakcji rozproszonej przy użyciu `EnlistTransaction` metody, która powoduje zarejestrowanie połączenia w <xref:System.Transactions.Transaction> wystąpieniu. W poprzednich wersjach ADO.NET jawna Rejestracja w transakcjach rozproszonych została wykonana przy użyciu `EnlistDistributedTransaction` metody połączenia, aby zarejestrować połączenie w <xref:System.EnterpriseServices.ITransaction> wystąpieniu, które jest obsługiwane w celu zapewnienia zgodności z poprzednimi wersjami. Aby uzyskać więcej informacji na temat transakcji usług przedsiębiorstwa, zobacz [współdziałanie z usługami przedsiębiorstwa i transakcjami modelu COM+](../transactions/interoperability-with-enterprise-services-and-com-transactions.md).  
  
 W przypadku korzystania <xref:System.Transactions> z transakcji z dostawcą .NET Framework dla SQL Server z bazą danych SQL Server <xref:System.Transactions.Transaction> zostanie użyta wartość uproszczona. Transakcja może zostać następnie podwyższona do pełnej transakcji rozproszonej w razie potrzeby. Aby uzyskać więcej informacji, zobacz temat [integracja z usługą system. Transactions z SQL Server](system-transactions-integration-with-sql-server.md).  
  
> [!NOTE]
> Maksymalna liczba transakcji rozproszonych, w których jednocześnie może uczestniczyć baza danych Oracle, jest domyślnie ustawiona na 10. Po dziesiątej transakcji po nawiązaniu połączenia z bazą danych Oracle zostanie zgłoszony wyjątek. Firma Oracle nie obsługuje `DDL` transakcji rozproszonej.  
  
## <a name="automatically-enlisting-in-a-distributed-transaction"></a>Automatyczne rejestrowanie w transakcji rozproszonej  

 Automatyczna rejestracja jest domyślnym (i preferowanym) sposobem integrowania połączeń ADO.NET z usługą `System.Transactions` . Obiekt połączenia zostanie automatycznie zarejestrowany w istniejącej transakcji rozproszonej, jeśli ustali, że transakcja jest aktywna, co `System.Transaction` oznacza, że `Transaction.Current` nie ma wartości null. Automatyczne rejestracje transakcji odbywa się po otwarciu połączenia. Nie nastąpi to nawet wtedy, gdy polecenie jest wykonywane wewnątrz zakresu transakcji. Funkcję autorejestracji można wyłączyć w istniejących transakcjach, określając `Enlist=false` jako parametr parametrów połączenia dla <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> parametru lub parametry `OLE DB Services=-7` połączenia dla elementu <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A?displayProperty=nameWithType> . Aby uzyskać więcej informacji o parametrach parametrów połączenia Oracle i ODBC, zobacz <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A?displayProperty=nameWithType> i <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A?displayProperty=nameWithType> .  
  
## <a name="manually-enlisting-in-a-distributed-transaction"></a>Ręczne rejestrowanie w transakcji rozproszonej  

 Jeśli funkcja autorejestracji jest wyłączona lub trzeba zarejestrować transakcję, która została uruchomiona po otwarciu połączenia, można zarejestrować się w istniejącej transakcji rozproszonej przy użyciu `EnlistTransaction` metody <xref:System.Data.Common.DbConnection> obiektu dla dostawcy, z którym pracujesz. Rejestracja w istniejącej transakcji rozproszonej zapewnia, że jeśli transakcja zostanie zatwierdzona lub wycofana, modyfikacje wprowadzone przez kod w źródle danych zostaną zatwierdzone lub wycofane.  
  
 Rejestrowanie w transakcjach rozproszonych jest szczególnie stosowane podczas puli obiektów firmowych. Jeśli obiekt biznesowy jest w puli z otwartym połączeniem, automatyczne rejestrację transakcji odbywa się tylko wtedy, gdy to połączenie jest otwarte. Jeśli wiele transakcji jest wykonywanych przy użyciu obiektu biznesowego w puli, otwarte połączenie dla tego obiektu nie zostanie automatycznie zarejestrowane w nowo zainicjowanych transakcjach. W takim przypadku można wyłączyć automatyczne rejestrowanie transakcji dla połączenia i zarejestrować połączenie w transakcjach za pomocą programu `EnlistTransaction` .  
  
 `EnlistTransaction` przyjmuje pojedynczy argument typu <xref:System.Transactions.Transaction> , który jest odwołaniem do istniejącej transakcji. Po wywołaniu `EnlistTransaction` metody połączenia wszystkie modyfikacje wprowadzone w źródle danych przy użyciu połączenia są uwzględniane w transakcji. Przekazanie wartości null umożliwia odrejestrowanie połączenia z bieżącej rejestracji transakcji rozproszonej. Należy pamiętać, że połączenie musi zostać otwarte przed wywołaniem `EnlistTransaction` .  
  
> [!NOTE]
> Gdy połączenie zostanie jawnie zarejestrowane w transakcji, nie można go wyrejestrować lub zarejestrować w innej transakcji do momentu zakończenia pierwszej transakcji.  
  
> [!CAUTION]
> `EnlistTransaction` zgłasza wyjątek, jeśli połączenie już rozpoczęło transakcję przy użyciu <xref:System.Data.Common.DbConnection.BeginTransaction%2A> metody połączenia. Jeśli jednak transakcja jest transakcją lokalną rozpoczętą w źródle danych (na przykład wykonując instrukcję BEGIN TRANSACTION jawnie używającą <xref:System.Data.SqlClient.SqlCommand> ), `EnlistTransaction` program wycofa transakcję lokalną i zarejestrowany w istniejącej transakcji rozproszonej zgodnie z żądaniem. Nie otrzymasz powiadomienia, że lokalna transakcja została wycofana, i musi zarządzać wszelkimi lokalnymi transakcjami, które nie zostały rozpoczęte przy użyciu <xref:System.Data.Common.DbConnection.BeginTransaction%2A> . Jeśli używasz Dostawca danych .NET Framework dla SQL Server ( `SqlClient` ) z SQL Server, próba zarejestrowania spowoduje zgłoszenie wyjątku. Wszystkie inne przypadki nie zostaną wykryte.  
  
## <a name="promotable-transactions-in-sql-server"></a>Promocja transakcji w SQL Server  

 SQL Server obsługuje operacje promocji, w których lokalna transakcja uproszczona może zostać automatycznie podwyższona do transakcji rozproszonej tylko wtedy, gdy jest to wymagane. Transakcja promocji nie wywołuje dodanego nakładu transakcji rozproszonej, chyba że jest wymagane dodatkowe obciążenie. Aby uzyskać więcej informacji i przykład kodu, zobacz [System. Transactions Integration with SQL Server](system-transactions-integration-with-sql-server.md).  
  
## <a name="configuring-distributed-transactions"></a>Konfigurowanie transakcji rozproszonych  

 Może być konieczne włączenie usługi MS DTC przez sieć w celu korzystania z transakcji rozproszonych. Jeśli Zapora systemu Windows jest włączona, należy zezwolić usłudze MS DTC na korzystanie z sieci lub otworzyć port usługi MS DTC.  
  
## <a name="see-also"></a>Zobacz też

- [Transakcje i współbieżność](transactions-and-concurrency.md)
- [Integracja System.Transactions z programem SQL Server](system-transactions-integration-with-sql-server.md)
- [Omówienie ADO.NET](ado-net-overview.md)
