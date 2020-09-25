---
title: 'Instrukcje: Ponowne użycie połączenia między poleceniem ADO.NET a DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 89c9a12399d3d76487d1fdc2bd82aa037c167710
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197355"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Instrukcje: Ponowne użycie połączenia między poleceniem ADO.NET a DataContext

Ponieważ [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] jest częścią ADO.NET technologii i opiera się na usługach zapewnianych przez ADO.NET, można ponownie użyć połączenia między poleceniem ADO.net a <xref:System.Data.Linq.DataContext> .  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak ponownie użyć tego samego połączenia między poleceniem ADO.NET a <xref:System.Data.Linq.DataContext> .  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Zobacz też

- [Informacje uzupełniające](background-information.md)
- [ADO.NET i LINQ to SQL](ado-net-and-linq-to-sql.md)
- [Komunikacja z bazą danych](communicating-with-the-database.md)
