---
title: 'Instrukcje: Rozwiązywanie konfliktów ze scaleniem wartości bazy danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
ms.openlocfilehash: fb77c4a23a4c4fa93dc55e63858ee41783c197ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166186"
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a><span data-ttu-id="7ff16-102">Instrukcje: Rozwiązywanie konfliktów ze scaleniem wartości bazy danych</span><span class="sxs-lookup"><span data-stu-id="7ff16-102">How to: Resolve Conflicts by Merging with Database Values</span></span>

<span data-ttu-id="7ff16-103">Aby uzgodnić różnice między oczekiwanymi i rzeczywistymi wartościami bazy danych przed próbą ponownego przesłania zmian, można użyć <xref:System.Data.Linq.RefreshMode.KeepChanges> programu do scalania wartości bazy danych z bieżącymi wartościami członków klienta.</span><span class="sxs-lookup"><span data-stu-id="7ff16-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepChanges> to merge database values with the current client member values.</span></span> <span data-ttu-id="7ff16-104">Aby uzyskać więcej informacji, zobacz [optymistyczne współbieżność: Omówienie](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7ff16-104">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ff16-105">We wszystkich przypadkach rekord na kliencie jest najpierw odświeżany przez pobranie zaktualizowanych danych z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="7ff16-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="7ff16-106">Ta akcja zapewnia, że kolejna próba aktualizacji nie powiedzie się na tych samych kontrolach współbieżności.</span><span class="sxs-lookup"><span data-stu-id="7ff16-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ff16-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="7ff16-107">Example</span></span>  

 <span data-ttu-id="7ff16-108">W tym scenariuszu <xref:System.Data.Linq.ChangeConflictException> wyjątek jest zgłaszany, gdy Użytkownik1 próbuje przesłać zmiany, ponieważ w międzyczasie została zmieniona kolumna asystenta i działu.</span><span class="sxs-lookup"><span data-stu-id="7ff16-108">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="7ff16-109">W poniższej tabeli przedstawiono sytuację.</span><span class="sxs-lookup"><span data-stu-id="7ff16-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="7ff16-110">Menedżer</span><span class="sxs-lookup"><span data-stu-id="7ff16-110">Manager</span></span>|<span data-ttu-id="7ff16-111">Pomocnik</span><span class="sxs-lookup"><span data-stu-id="7ff16-111">Assistant</span></span>|<span data-ttu-id="7ff16-112">Dział</span><span class="sxs-lookup"><span data-stu-id="7ff16-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="7ff16-113">Oryginalny stan bazy danych podczas wykonywania zapytania przez Użytkownik1 i.</span><span class="sxs-lookup"><span data-stu-id="7ff16-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="7ff16-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="7ff16-114">Alfreds</span></span>|<span data-ttu-id="7ff16-115">Maria</span><span class="sxs-lookup"><span data-stu-id="7ff16-115">Maria</span></span>|<span data-ttu-id="7ff16-116">Sales</span><span class="sxs-lookup"><span data-stu-id="7ff16-116">Sales</span></span>|  
|<span data-ttu-id="7ff16-117">Użytkownik1 przygotowuje się do przesłania tych zmian.</span><span class="sxs-lookup"><span data-stu-id="7ff16-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="7ff16-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="7ff16-118">Alfred</span></span>||<span data-ttu-id="7ff16-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="7ff16-119">Marketing</span></span>|  
|<span data-ttu-id="7ff16-120">Do tego celu zostały już przesłane te zmiany.</span><span class="sxs-lookup"><span data-stu-id="7ff16-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="7ff16-121">Mary</span><span class="sxs-lookup"><span data-stu-id="7ff16-121">Mary</span></span>|<span data-ttu-id="7ff16-122">Usługa</span><span class="sxs-lookup"><span data-stu-id="7ff16-122">Service</span></span>|  
  
 <span data-ttu-id="7ff16-123">Użytkownik1 decyduje się rozwiązać ten konflikt przez scalenie wartości bazy danych z bieżącymi wartościami członków klienta.</span><span class="sxs-lookup"><span data-stu-id="7ff16-123">User1 decides to resolve this conflict by merging database values with the current client member values.</span></span> <span data-ttu-id="7ff16-124">Wynikiem tego jest to, że wartości bazy danych są zastępowane tylko wtedy, gdy bieżąca Grupa zmian również zmodyfikował tę wartość.</span><span class="sxs-lookup"><span data-stu-id="7ff16-124">The result will be that database values are overwritten only when the current changeset has also modified that value.</span></span>  
  
 <span data-ttu-id="7ff16-125">Gdy Użytkownik1 rozwiązuje konflikt przy użyciu <xref:System.Data.Linq.RefreshMode.KeepChanges> , wynik w bazie danych jest jak w poniższej tabeli:</span><span class="sxs-lookup"><span data-stu-id="7ff16-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepChanges>, the result in the database is as in the following table:</span></span>  
  
||<span data-ttu-id="7ff16-126">Menedżer</span><span class="sxs-lookup"><span data-stu-id="7ff16-126">Manager</span></span>|<span data-ttu-id="7ff16-127">Pomocnik</span><span class="sxs-lookup"><span data-stu-id="7ff16-127">Assistant</span></span>|<span data-ttu-id="7ff16-128">Dział</span><span class="sxs-lookup"><span data-stu-id="7ff16-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="7ff16-129">Nowy stan po rozwiązaniu konfliktu.</span><span class="sxs-lookup"><span data-stu-id="7ff16-129">New state after conflict resolution.</span></span>|<span data-ttu-id="7ff16-130">Alfred</span><span class="sxs-lookup"><span data-stu-id="7ff16-130">Alfred</span></span><br /><br /> <span data-ttu-id="7ff16-131">(od Użytkownik1)</span><span class="sxs-lookup"><span data-stu-id="7ff16-131">(from User1)</span></span>|<span data-ttu-id="7ff16-132">Mary</span><span class="sxs-lookup"><span data-stu-id="7ff16-132">Mary</span></span><br /><br /> <span data-ttu-id="7ff16-133">(od b do)</span><span class="sxs-lookup"><span data-stu-id="7ff16-133">(from User2)</span></span>|<span data-ttu-id="7ff16-134">Marketing</span><span class="sxs-lookup"><span data-stu-id="7ff16-134">Marketing</span></span><br /><br /> <span data-ttu-id="7ff16-135">(od Użytkownik1)</span><span class="sxs-lookup"><span data-stu-id="7ff16-135">(from User1)</span></span>|  
  
 <span data-ttu-id="7ff16-136">Poniższy przykład pokazuje, jak scalić wartości bazy danych z bieżącymi wartościami członków klienta (chyba że klient również zmienił tę wartość).</span><span class="sxs-lookup"><span data-stu-id="7ff16-136">The following example shows how to merge database values with the current client member values (unless the client has also changed that value).</span></span> <span data-ttu-id="7ff16-137">Nie występuje żadna Inspekcja ani Niestandardowa obsługa konfliktów poszczególnych członków.</span><span class="sxs-lookup"><span data-stu-id="7ff16-137">No inspection or custom handling of individual member conflicts occurs.</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7ff16-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7ff16-138">See also</span></span>

- [<span data-ttu-id="7ff16-139">Instrukcje: Rozwiązywanie konfliktów z zastąpieniem wartości bazy danych</span><span class="sxs-lookup"><span data-stu-id="7ff16-139">How to: Resolve Conflicts by Overwriting Database Values</span></span>](how-to-resolve-conflicts-by-overwriting-database-values.md)
- [<span data-ttu-id="7ff16-140">Instrukcje: Rozwiązywanie konfliktów z zachowaniem wartości bazy danych</span><span class="sxs-lookup"><span data-stu-id="7ff16-140">How to: Resolve Conflicts by Retaining Database Values</span></span>](how-to-resolve-conflicts-by-retaining-database-values.md)
- [<span data-ttu-id="7ff16-141">Instrukcje: Zarządzanie konfliktami zmian</span><span class="sxs-lookup"><span data-stu-id="7ff16-141">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
