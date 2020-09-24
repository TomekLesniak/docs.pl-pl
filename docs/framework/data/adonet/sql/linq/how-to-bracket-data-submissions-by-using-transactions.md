---
title: 'Instrukcje: Przesyłanie danych nawiasów za pomocą transakcji'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 4d3efedbf15be55fa7a9ab235f881f1c97758953
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161363"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Instrukcje: Przesyłanie danych nawiasów za pomocą transakcji

Możesz użyć <xref:System.Transactions.TransactionScope> , aby przenawiasować przesłanie do bazy danych. Aby uzyskać więcej informacji, zobacz [Obsługa transakcji](transaction-support.md).  
  
## <a name="example"></a>Przykład  

 Poniższy kod obejmuje przesyłanie bazy danych w <xref:System.Transactions.TransactionScope> .  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Zobacz też

- [Pobieranie przykładowych baz danych](downloading-sample-databases.md)
- [Tworzenie i przesyłanie zmian danych](making-and-submitting-data-changes.md)
- [Obsługa transakcji](transaction-support.md)
