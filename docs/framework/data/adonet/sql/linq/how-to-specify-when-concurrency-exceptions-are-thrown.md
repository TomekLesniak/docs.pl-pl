---
title: 'Instrukcje: Określanie, kiedy są zgłaszane wyjątki współbieżności'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 9d71ca82c3fe1abd23a82d952d38c3ea23a7f1c0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197121"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a><span data-ttu-id="6b6c7-102">Instrukcje: Określanie, kiedy są zgłaszane wyjątki współbieżności</span><span class="sxs-lookup"><span data-stu-id="6b6c7-102">How to: Specify When Concurrency Exceptions are Thrown</span></span>

<span data-ttu-id="6b6c7-103">W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.ChangeConflictException> wyjątek jest zgłaszany, gdy obiekty nie są aktualizowane z powodu nieoptymistycznych konfliktów współbieżności.</span><span class="sxs-lookup"><span data-stu-id="6b6c7-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when objects do not update because of optimistic concurrency conflicts.</span></span> <span data-ttu-id="6b6c7-104">Aby uzyskać więcej informacji, zobacz [optymistyczne współbieżność: Omówienie](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6b6c7-104">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="6b6c7-105">Przed przesłaniem zmian do bazy danych można określić, kiedy mają być zgłaszane wyjątki współbieżności:</span><span class="sxs-lookup"><span data-stu-id="6b6c7-105">Before you submit your changes to the database, you can specify when concurrency exceptions should be thrown:</span></span>  
  
- <span data-ttu-id="6b6c7-106">Zgłoś wyjątek przy pierwszym błędzie ( <xref:System.Data.Linq.ConflictMode.FailOnFirstConflict> ).</span><span class="sxs-lookup"><span data-stu-id="6b6c7-106">Throw the exception at the first failure (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span></span>  
  
- <span data-ttu-id="6b6c7-107">Zakończ wszystkie próby aktualizacji, zakumulowanie wszystkich błędów i Zgłoś błędy skumulowane w wyjątku ( <xref:System.Data.Linq.ConflictMode.ContinueOnConflict> ).</span><span class="sxs-lookup"><span data-stu-id="6b6c7-107">Finish all update tries, accumulate all failures, and report the accumulated failures in the exception (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span></span>  
  
 <span data-ttu-id="6b6c7-108">Gdy zostanie zgłoszony, <xref:System.Data.Linq.ChangeConflictException> wyjątek zapewnia dostęp do <xref:System.Data.Linq.ChangeConflictCollection> kolekcji.</span><span class="sxs-lookup"><span data-stu-id="6b6c7-108">When thrown, the <xref:System.Data.Linq.ChangeConflictException> exception provides access to a <xref:System.Data.Linq.ChangeConflictCollection> collection.</span></span> <span data-ttu-id="6b6c7-109">Ta kolekcja zawiera szczegółowe informacje dotyczące każdego konfliktu (zamapowane do pojedynczej nieudanej aktualizacji), w tym dostęp do <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> kolekcji.</span><span class="sxs-lookup"><span data-stu-id="6b6c7-109">This collection provides details for each conflict (mapped to a single failed update try), including access to the <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> collection.</span></span> <span data-ttu-id="6b6c7-110">Konflikty każdego elementu członkowskiego są mapowane na pojedynczy element członkowski w aktualizacji, która nie mogła sprawdzić współbieżności.</span><span class="sxs-lookup"><span data-stu-id="6b6c7-110">Each member conflict maps to a single member in the update that failed the concurrency check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b6c7-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="6b6c7-111">Example</span></span>  

 <span data-ttu-id="6b6c7-112">Poniższy kod przedstawia przykłady obu wartości.</span><span class="sxs-lookup"><span data-stu-id="6b6c7-112">The following code shows examples of both values.</span></span>  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6b6c7-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6b6c7-113">See also</span></span>

- [<span data-ttu-id="6b6c7-114">Instrukcje: Zarządzanie konfliktami zmian</span><span class="sxs-lookup"><span data-stu-id="6b6c7-114">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="6b6c7-115">Tworzenie i przesyłanie zmian danych</span><span class="sxs-lookup"><span data-stu-id="6b6c7-115">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
