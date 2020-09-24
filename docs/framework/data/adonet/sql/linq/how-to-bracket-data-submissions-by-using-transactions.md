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
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="da451-102">Instrukcje: Przesyłanie danych nawiasów za pomocą transakcji</span><span class="sxs-lookup"><span data-stu-id="da451-102">How to: Bracket Data Submissions by Using Transactions</span></span>

<span data-ttu-id="da451-103">Możesz użyć <xref:System.Transactions.TransactionScope> , aby przenawiasować przesłanie do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="da451-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="da451-104">Aby uzyskać więcej informacji, zobacz [Obsługa transakcji](transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="da451-104">For more information, see [Transaction Support](transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="da451-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="da451-105">Example</span></span>  

 <span data-ttu-id="da451-106">Poniższy kod obejmuje przesyłanie bazy danych w <xref:System.Transactions.TransactionScope> .</span><span class="sxs-lookup"><span data-stu-id="da451-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="da451-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="da451-107">See also</span></span>

- [<span data-ttu-id="da451-108">Pobieranie przykładowych baz danych</span><span class="sxs-lookup"><span data-stu-id="da451-108">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="da451-109">Tworzenie i przesyłanie zmian danych</span><span class="sxs-lookup"><span data-stu-id="da451-109">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="da451-110">Obsługa transakcji</span><span class="sxs-lookup"><span data-stu-id="da451-110">Transaction Support</span></span>](transaction-support.md)
