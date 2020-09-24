---
title: Uzyskiwanie pojedynczej wartości z bazy danych
description: Dowiedz się, jak zwrócić pojedynczą wartość w ADO.NET. Ten przykładowy kod zwraca wartość kolumny tożsamości dla wstawionego rekordu.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 9ce29bc1321814bd60cfaacd222fc55a3fbf12ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150729"
---
# <a name="obtaining-a-single-value-from-a-database"></a>Uzyskiwanie pojedynczej wartości z bazy danych

Może być konieczne zwrócenie informacji o bazie danych, która jest po prostu pojedynczą wartością, a nie w formie tabeli lub strumienia danych. Na przykład możesz chcieć zwrócić wynik funkcji agregującej, takiej jak COUNT ( \* ), sum (Price) lub AVG (ilość). Obiekt **Command** oferuje możliwość zwracania pojedynczych wartości przy użyciu metody **ExecuteScalar** . Metoda **ExecuteScalar** zwraca, jako wartość skalarną, wartość pierwszej kolumny pierwszego wiersza w zestawie wyników.  
  
 Poniższy przykład kodu wstawia nową wartość w bazie danych przy użyciu <xref:System.Data.SqlClient.SqlCommand> . <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>Metoda jest używana do zwracania wartości kolumny Identity dla wstawionego rekordu.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Polecenia i parametry](commands-and-parameters.md)
- [Wykonywanie polecenia](executing-a-command.md)
- [DbConnection, DbCommand i DbException](dbconnection-dbcommand-and-dbexception.md)
- [Omówienie ADO.NET](ado-net-overview.md)
