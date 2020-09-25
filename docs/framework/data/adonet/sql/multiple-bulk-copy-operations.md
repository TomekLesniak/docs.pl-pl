---
title: Wiele operacji kopiowania zbiorczego
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: d447f09fcbfe108346b81a2bced44cf305e2844b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172674"
---
# <a name="multiple-bulk-copy-operations"></a>Wiele operacji kopiowania zbiorczego

Można wykonywać wiele operacji kopiowania zbiorczego przy użyciu jednego wystąpienia <xref:System.Data.SqlClient.SqlBulkCopy> klasy. Jeśli parametry operacji zmieniają się między kopiami (na przykład nazwę tabeli docelowej), należy je zaktualizować przed kolejnymi wywołaniami dowolnej metody **WriteToServer** , jak pokazano w poniższym przykładzie. O ile nie zmieniono jawnie, wszystkie wartości właściwości pozostają takie same, jak w poprzedniej operacji kopiowania zbiorczego dla danego wystąpienia.  
  
> [!NOTE]
> Wykonywanie wielu operacji kopiowania zbiorczego przy użyciu tego samego wystąpienia <xref:System.Data.SqlClient.SqlBulkCopy> jest zwykle wydajniejsze niż używanie osobnego wystąpienia dla każdej operacji.  
  
 Jeśli wykonujesz kilka operacji kopiowania zbiorczego przy użyciu tego samego <xref:System.Data.SqlClient.SqlBulkCopy> obiektu, nie ma żadnych ograniczeń dotyczących tego, czy informacje źródłowe i docelowe są równe lub różnią się w poszczególnych operacjach. Należy jednak upewnić się, że informacje o skojarzeniach kolumn są prawidłowo ustawiane za każdym razem, gdy piszesz na serwerze.  
  
> [!IMPORTANT]
> Ten przykład nie zostanie uruchomiony, jeśli nie utworzono tabel roboczych, zgodnie z opisem w [przykładowej konfiguracji kopiowania zbiorczego](bulk-copy-example-setup.md). Ten kod jest dostarczany w celu przedstawienia składni tylko za pomocą **SqlBulkCopy** . Jeśli tabele źródłowe i docelowe znajdują się w tym samym wystąpieniu SQL Server, łatwiej i szybciej można używać instrukcji języka Transact-SQL `INSERT … SELECT` do kopiowania danych.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Operacje kopiowania masowego w programie SQL Server](bulk-copy-operations-in-sql-server.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
