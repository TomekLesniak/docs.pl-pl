---
title: Tworzenie wątków i przekazywanie danych w czasie rozpoczęcia
description: Zapoznaj się z tematem tworzenia wątków i przekazywania danych w czasie rozpoczęcia procesu systemu operacyjnego w programie .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET], creating
- threading [.NET], passing data to threads
- threading [.NET], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
ms.openlocfilehash: 3f44eb9dabc9145cd0e6ec9bfd3d484c9079e803
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819932"
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="9bc32-103">Tworzenie wątków i przekazywanie danych w czasie rozpoczęcia</span><span class="sxs-lookup"><span data-stu-id="9bc32-103">Creating threads and passing data at start time</span></span>

<span data-ttu-id="9bc32-104">Podczas tworzenia procesu systemu operacyjnego system operacyjny wprowadza wątek w celu wykonania kodu w tym procesie, w tym wszystkich oryginalnych domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9bc32-104">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="9bc32-105">Od tego momentu domeny aplikacji mogą być tworzone i niszczone bez konieczności tworzenia lub zniszczenia wątków systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="9bc32-105">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="9bc32-106">Jeśli wykonywany kod jest kodem zarządzanym, <xref:System.Threading.Thread> można uzyskać obiekt dla wątku wykonywanego w bieżącej domenie aplikacji, pobierając Właściwość statyczną <xref:System.Threading.Thread.CurrentThread%2A> typu <xref:System.Threading.Thread> .</span><span class="sxs-lookup"><span data-stu-id="9bc32-106">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="9bc32-107">W tym temacie opisano tworzenie wątku i omówiono alternatywy przekazywania danych do procedury wątku.</span><span class="sxs-lookup"><span data-stu-id="9bc32-107">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="9bc32-108">Tworzenie wątku</span><span class="sxs-lookup"><span data-stu-id="9bc32-108">Creating a thread</span></span>

 <span data-ttu-id="9bc32-109">Tworzenie nowego <xref:System.Threading.Thread> obiektu powoduje utworzenie nowego wątku zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="9bc32-109">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="9bc32-110"><xref:System.Threading.Thread>Klasa ma konstruktory, które przyjmują <xref:System.Threading.ThreadStart> delegata lub <xref:System.Threading.ParameterizedThreadStart> delegata; delegat otacza metodę, która jest wywoływana przez nowy wątek po wywołaniu <xref:System.Threading.Thread.Start%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="9bc32-110">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="9bc32-111">Wywoływanie <xref:System.Threading.Thread.Start%2A> więcej niż raz powoduje, że <xref:System.Threading.ThreadStateException> zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="9bc32-111">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="9bc32-112"><xref:System.Threading.Thread.Start%2A>Metoda wraca natychmiast, często przed rozpoczęciem nowego wątku.</span><span class="sxs-lookup"><span data-stu-id="9bc32-112">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="9bc32-113">Można użyć <xref:System.Threading.Thread.ThreadState%2A> <xref:System.Threading.Thread.IsAlive%2A> właściwości i do określenia stanu wątku w dowolnym momencie, ale te właściwości nie powinny być używane do synchronizowania działań wątków.</span><span class="sxs-lookup"><span data-stu-id="9bc32-113">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bc32-114">Po uruchomieniu wątku nie jest konieczne zachowywanie odwołania do <xref:System.Threading.Thread> obiektu.</span><span class="sxs-lookup"><span data-stu-id="9bc32-114">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="9bc32-115">Wątek będzie wykonywany do momentu zakończenia procedury wątku.</span><span class="sxs-lookup"><span data-stu-id="9bc32-115">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="9bc32-116">Poniższy przykład kodu tworzy dwa nowe wątki do wywoływania wystąpień i metod statycznych dla innego obiektu.</span><span class="sxs-lookup"><span data-stu-id="9bc32-116">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads"></a><span data-ttu-id="9bc32-117">Przekazywanie danych do wątków</span><span class="sxs-lookup"><span data-stu-id="9bc32-117">Passing data to threads</span></span>

<span data-ttu-id="9bc32-118"><xref:System.Threading.ParameterizedThreadStart>Delegat zapewnia łatwy sposób przekazywania obiektu zawierającego dane do wątku podczas wywoływania <xref:System.Threading.Thread.Start(System.Object)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9bc32-118">The <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call <xref:System.Threading.Thread.Start(System.Object)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9bc32-119">Zobacz <xref:System.Threading.ParameterizedThreadStart> , aby zobaczyć przykład kodu.</span><span class="sxs-lookup"><span data-stu-id="9bc32-119">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>
  
 <span data-ttu-id="9bc32-120">Użycie <xref:System.Threading.ParameterizedThreadStart> delegata nie jest bezpiecznym typem sposobu przekazywania danych, ponieważ <xref:System.Threading.Thread.Start(System.Object)?displayProperty=nameWithType> Metoda akceptuje każdy obiekt.</span><span class="sxs-lookup"><span data-stu-id="9bc32-120">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start(System.Object)?displayProperty=nameWithType> method accepts any object.</span></span> <span data-ttu-id="9bc32-121">Alternatywą jest hermetyzacja procedury wątku i danych w klasie pomocnika i użycie <xref:System.Threading.ThreadStart> delegata do wykonania procedury wątku.</span><span class="sxs-lookup"><span data-stu-id="9bc32-121">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="9bc32-122">Poniższy przykład ilustruje tę technikę:</span><span class="sxs-lookup"><span data-stu-id="9bc32-122">The following example demonstrates this technique:</span></span>

 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  

<span data-ttu-id="9bc32-123">Ani <xref:System.Threading.ThreadStart> <xref:System.Threading.ParameterizedThreadStart> delegat nie ma zwracanej wartości, ponieważ nie ma miejsca do zwrócenia danych z wywołania asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="9bc32-123">Neither <xref:System.Threading.ThreadStart> nor <xref:System.Threading.ParameterizedThreadStart> delegate has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="9bc32-124">Aby pobrać wyniki metody wątku, można użyć metody wywołania zwrotnego, jak pokazano w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="9bc32-124">To retrieve the results of a thread method, you can use a callback method, as shown in the next section.</span></span>
  
## <a name="retrieving-data-from-threads-with-callback-methods"></a><span data-ttu-id="9bc32-125">Pobieranie danych z wątków z metodami wywołania zwrotnego</span><span class="sxs-lookup"><span data-stu-id="9bc32-125">Retrieving data from threads with callback methods</span></span>

 <span data-ttu-id="9bc32-126">Poniższy przykład demonstruje metodę wywołania zwrotnego, która pobiera dane z wątku.</span><span class="sxs-lookup"><span data-stu-id="9bc32-126">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="9bc32-127">Konstruktor klasy, która zawiera dane i metoda wątku, również akceptuje delegata reprezentujący metodę wywołania zwrotnego; przed zakończeniem metody wątku wywołuje delegata wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="9bc32-127">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="9bc32-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9bc32-128">See also</span></span>

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadStart>
- <xref:System.Threading.ParameterizedThreadStart>
- <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9bc32-129">Wątkowość</span><span class="sxs-lookup"><span data-stu-id="9bc32-129">Threading</span></span>](index.md)
- [<span data-ttu-id="9bc32-130">Używanie wątków i wątkowości</span><span class="sxs-lookup"><span data-stu-id="9bc32-130">Using Threads and Threading</span></span>](using-threads-and-threading.md)
