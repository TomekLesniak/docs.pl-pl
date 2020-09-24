---
title: 'Instrukcje: Bezpośrednie wykonywanie poleceń SQL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 6c72e683c37968ce18717b70ef6d647ca287bd20
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147648"
---
# <a name="how-to-directly-execute-sql-commands"></a>Instrukcje: Bezpośrednie wykonywanie poleceń SQL

Przy założeniu <xref:System.Data.Linq.DataContext> połączenia, można użyć <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> do wykonywania poleceń SQL, które nie zwracają obiektów.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład powoduje, że SQL Server zwiększyć wartość CenaJednostkowa o 1,00.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Bezpośrednie wykonywanie zapytań SQL](how-to-directly-execute-sql-queries.md)
- [Komunikacja z bazą danych](communicating-with-the-database.md)
