---
title: Zarządzana wątkowość
description: Zobacz linki do artykułów na temat zarządzanych wątków w programie .NET obejmujących podstawowe, najlepsze rozwiązania, obiekty wątkowe & funkcje, strony referencyjne & więcej.
ms.date: 03/30/2017
helpviewer_keywords:
- threading [.NET], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: 28ba05c345d22b14512d280f3855934d727b3142
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728449"
---
# <a name="managed-threading"></a><span data-ttu-id="b4a93-103">Zarządzana wątkowość</span><span class="sxs-lookup"><span data-stu-id="b4a93-103">Managed threading</span></span>

<span data-ttu-id="b4a93-104">Niezależnie od tego, czy tworzysz komputery z jednym procesorem, czy kilka, chcesz, aby aplikacja zapewniała najbardziej reagującą interakcję z użytkownikiem, nawet jeśli aplikacja wykonuje obecnie inne czynności.</span><span class="sxs-lookup"><span data-stu-id="b4a93-104">Whether you're developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="b4a93-105">Korzystanie z wielu wątków wykonywania to jeden z najbardziej zaawansowanych sposobów, aby aplikacja mogła reagować na użytkownika, i w tym samym czasie używa procesora w okresie między lub nawet podczas zdarzeń użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b4a93-105">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="b4a93-106">W tej sekcji przedstawiono podstawowe pojęcia związane z wątkami, które koncentrują się na zarządzanych pojęciach związanych z wątkami i korzystaniu z zarządzanych wątków.</span><span class="sxs-lookup"><span data-stu-id="b4a93-106">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4a93-107">Począwszy od .NET Framework 4, programowanie wielowątkowe jest znacznie uproszczone przy użyciu <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> klas i, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), klas kolekcji współbieżnych w <xref:System.Collections.Concurrent?displayProperty=nameWithType> przestrzeni nazw oraz modelu programowania opartego na koncepcji zadań, a nie wątków.</span><span class="sxs-lookup"><span data-stu-id="b4a93-107">Starting with .NET Framework 4, multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classes, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, and a programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="b4a93-108">Aby uzyskać więcej informacji, zobacz [programowanie równoległe](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4a93-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4a93-109">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="b4a93-109">In This Section</span></span>  

 [<span data-ttu-id="b4a93-110">Zarządzana wątkowość — podstawy</span><span class="sxs-lookup"><span data-stu-id="b4a93-110">Managed Threading Basics</span></span>](managed-threading-basics.md)  
 <span data-ttu-id="b4a93-111">Zawiera omówienie zarządzania wątkami i omówiono, kiedy należy używać wielu wątków.</span><span class="sxs-lookup"><span data-stu-id="b4a93-111">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="b4a93-112">Używanie wątków i wątkowości</span><span class="sxs-lookup"><span data-stu-id="b4a93-112">Using Threads and Threading</span></span>](using-threads-and-threading.md)  
 <span data-ttu-id="b4a93-113">Wyjaśnia, jak tworzyć, uruchamiać, wstrzymywać, wznawiać i przerywać wątki.</span><span class="sxs-lookup"><span data-stu-id="b4a93-113">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="b4a93-114">Zarządzana wątkowość — najlepsze rozwiązania</span><span class="sxs-lookup"><span data-stu-id="b4a93-114">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="b4a93-115">Omawia poziomy synchronizacji, sposób unikania zakleszczenii i warunków wyścigu oraz inne problemy z wątkami.</span><span class="sxs-lookup"><span data-stu-id="b4a93-115">Discusses levels of synchronization, how to avoid deadlocks and race conditions, and other threading issues.</span></span>  
  
 [<span data-ttu-id="b4a93-116">Wątkowość obiektów i funkcji</span><span class="sxs-lookup"><span data-stu-id="b4a93-116">Threading Objects and Features</span></span>](threading-objects-and-features.md)  
 <span data-ttu-id="b4a93-117">Opisuje zarządzane klasy, których można użyć do synchronizowania działań wątków i danych obiektów, do których dostęp odbywa się w różnych wątkach i zawiera Omówienie wątków puli wątków.</span><span class="sxs-lookup"><span data-stu-id="b4a93-117">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b4a93-118">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="b4a93-118">Reference</span></span>  

 <xref:System.Threading>  
 <span data-ttu-id="b4a93-119">Zawiera klasy służące do korzystania z i synchronizowania zarządzanych wątków.</span><span class="sxs-lookup"><span data-stu-id="b4a93-119">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="b4a93-120">Zawiera klasy kolekcji, które są bezpieczne do użytku z wieloma wątkami.</span><span class="sxs-lookup"><span data-stu-id="b4a93-120">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="b4a93-121">Zawiera klasy służące do tworzenia i planowania współbieżnych zadań przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="b4a93-121">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b4a93-122">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="b4a93-122">Related Sections</span></span>  

 [<span data-ttu-id="b4a93-123">Domeny aplikacji</span><span class="sxs-lookup"><span data-stu-id="b4a93-123">Application Domains</span></span>](../../framework/app-domains/application-domains.md)  
 <span data-ttu-id="b4a93-124">Zawiera omówienie domen aplikacji i ich użycia przez Common Language Infrastructure.</span><span class="sxs-lookup"><span data-stu-id="b4a93-124">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="b4a93-125">Asynchroniczne operacje we/wy pliku</span><span class="sxs-lookup"><span data-stu-id="b4a93-125">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)  
 <span data-ttu-id="b4a93-126">Opis korzyści związanych z wydajnością oraz podstawowych asynchronicznych operacji We/Wy.</span><span class="sxs-lookup"><span data-stu-id="b4a93-126">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 [<span data-ttu-id="b4a93-127">Wzorzec asynchroniczny oparty na zadaniach (TAP)</span><span class="sxs-lookup"><span data-stu-id="b4a93-127">Task-based Asynchronous Pattern (TAP)</span></span>](../asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 <span data-ttu-id="b4a93-128">Zawiera omówienie zalecanego wzorca dla programowania asynchronicznego w programie .NET.</span><span class="sxs-lookup"><span data-stu-id="b4a93-128">Provides an overview of the recommended pattern for asynchronous programming in .NET.</span></span>  
  
 [<span data-ttu-id="b4a93-129">Wywołanie metod synchronicznych w sposób asynchroniczny</span><span class="sxs-lookup"><span data-stu-id="b4a93-129">Calling Synchronous Methods Asynchronously</span></span>](../asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="b4a93-130">Wyjaśnia, jak wywoływać metody w wątkach puli wątków przy użyciu wbudowanych funkcji delegatów.</span><span class="sxs-lookup"><span data-stu-id="b4a93-130">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="b4a93-131">Programowanie równoległe</span><span class="sxs-lookup"><span data-stu-id="b4a93-131">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="b4a93-132">Opisuje równoległe biblioteki programistyczne, które upraszczają korzystanie z wielu wątków w aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="b4a93-132">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="b4a93-133">Równoległe LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="b4a93-133">Parallel LINQ (PLINQ)</span></span>](../parallel-programming/introduction-to-plinq.md)  
 <span data-ttu-id="b4a93-134">Opisuje system uruchamiania zapytań równolegle, aby korzystać z wielu procesorów.</span><span class="sxs-lookup"><span data-stu-id="b4a93-134">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>
