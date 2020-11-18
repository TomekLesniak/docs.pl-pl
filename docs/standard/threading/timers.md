---
title: Czasomierze
description: Dowiedz się, jakie czasomierze .NET mają być używane w środowisku wielowątkowym.
ms.date: 07/03/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: 1ab612bc32a84c1248d311b0603a01a32a25199f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826108"
---
# <a name="timers"></a><span data-ttu-id="c1e22-103">Czasomierze</span><span class="sxs-lookup"><span data-stu-id="c1e22-103">Timers</span></span>

<span data-ttu-id="c1e22-104">Platforma .NET oferuje dwa czasomierze do użycia w środowisku wielowątkowym:</span><span class="sxs-lookup"><span data-stu-id="c1e22-104">.NET provides two timers to use in a multithreaded environment:</span></span>

- <span data-ttu-id="c1e22-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, która wykonuje pojedynczą metodę wywołania zwrotnego w <xref:System.Threading.ThreadPool> wątku w regularnych odstępach czasu.</span><span class="sxs-lookup"><span data-stu-id="c1e22-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, which executes a single callback method on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>
- <span data-ttu-id="c1e22-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, które domyślnie wywołuje zdarzenie w <xref:System.Threading.ThreadPool> wątku w regularnych odstępach czasu.</span><span class="sxs-lookup"><span data-stu-id="c1e22-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, which by default raises an event on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>

> [!NOTE]
> <span data-ttu-id="c1e22-107">Niektóre implementacje platformy .NET mogą obejmować dodatkowe czasomierze:</span><span class="sxs-lookup"><span data-stu-id="c1e22-107">Some .NET implementations may include additional timers:</span></span>
>
> - <span data-ttu-id="c1e22-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: składnik Windows Forms, który uruchamia zdarzenie w regularnych odstępach czasu.</span><span class="sxs-lookup"><span data-stu-id="c1e22-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: a Windows Forms component that fires an event at regular intervals.</span></span> <span data-ttu-id="c1e22-109">Składnik nie ma interfejsu użytkownika i jest przeznaczony do użytku w środowisku jednowątkowym.</span><span class="sxs-lookup"><span data-stu-id="c1e22-109">The component has no user interface and is designed for use in a single-threaded environment.</span></span>  
> - <span data-ttu-id="c1e22-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: składnik ASP.NET, który wykonuje asynchroniczne lub synchroniczne ogłaszanie stron sieci Web w regularnych odstępach czasu.</span><span class="sxs-lookup"><span data-stu-id="c1e22-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: an ASP.NET component that performs asynchronous or synchronous web page postbacks at a regular interval.</span></span>
> - <span data-ttu-id="c1e22-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: czasomierz, który jest zintegrowany z <xref:System.Windows.Threading.Dispatcher> kolejką, która jest przetwarzana w określonym przedziale czasu i o określonym priorytecie.</span><span class="sxs-lookup"><span data-stu-id="c1e22-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: a timer that is integrated into the <xref:System.Windows.Threading.Dispatcher> queue which is processed at a specified interval of time and at a specified priority.</span></span>

## <a name="the-systemthreadingtimer-class"></a><span data-ttu-id="c1e22-112">Klasa System. Threading. Timer</span><span class="sxs-lookup"><span data-stu-id="c1e22-112">The System.Threading.Timer class</span></span>

<span data-ttu-id="c1e22-113"><xref:System.Threading.Timer?displayProperty=nameWithType>Klasa umożliwia ciągłe wywoływanie delegata w określonych przedziałach czasowych.</span><span class="sxs-lookup"><span data-stu-id="c1e22-113">The <xref:System.Threading.Timer?displayProperty=nameWithType> class enables you to continuously call a delegate at specified time intervals.</span></span> <span data-ttu-id="c1e22-114">Tej klasy można również użyć do zaplanowania pojedynczego wywołania delegata w określonym przedziale czasu.</span><span class="sxs-lookup"><span data-stu-id="c1e22-114">You can also use this class to schedule a single call to a delegate in a specified time interval.</span></span> <span data-ttu-id="c1e22-115">Delegat jest wykonywany w <xref:System.Threading.ThreadPool> wątku.</span><span class="sxs-lookup"><span data-stu-id="c1e22-115">The delegate is executed on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="c1e22-116">Podczas tworzenia <xref:System.Threading.Timer?displayProperty=nameWithType> obiektu należy określić <xref:System.Threading.TimerCallback> delegata, który definiuje metodę wywołania zwrotnego, opcjonalny obiekt stanu, który jest przesyłany do wywołania zwrotnego, ilość czasu oczekiwania przed pierwszym wywołaniem wywołania zwrotnego oraz odstęp czasu między wywołaniami wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="c1e22-116">When you create a <xref:System.Threading.Timer?displayProperty=nameWithType> object, you specify a <xref:System.Threading.TimerCallback> delegate that defines the callback method, an optional state object that is passed to the callback, the amount of time to delay before the first invocation of the callback, and the time interval between callback invocations.</span></span> <span data-ttu-id="c1e22-117">Aby anulować oczekujący czasomierz, wywołaj <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="c1e22-117">To cancel a pending timer, call the <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c1e22-118">Poniższy przykład tworzy czasomierz, który wywołuje dostarczony delegat po raz pierwszy po jednej sekundzie (1000 milisekund), a następnie wywołuje ją co dwie sekundy.</span><span class="sxs-lookup"><span data-stu-id="c1e22-118">The following example creates a timer that calls the provided delegate for the first time after one second (1000 milliseconds) and then calls it every two seconds.</span></span> <span data-ttu-id="c1e22-119">Obiekt State w przykładzie służy do zliczania, ile razy obiekt delegowany jest wywoływany.</span><span class="sxs-lookup"><span data-stu-id="c1e22-119">The state object in the example is used to count how many times the delegate is called.</span></span> <span data-ttu-id="c1e22-120">Czasomierz jest zatrzymany, gdy delegat został wywołany co najmniej 10 razy.</span><span class="sxs-lookup"><span data-stu-id="c1e22-120">The timer is stopped when the delegate has been called at least 10 times.</span></span>

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

<span data-ttu-id="c1e22-121">Aby uzyskać więcej informacji i przykładów, zobacz <xref:System.Threading.Timer?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c1e22-121">For more information and examples, see <xref:System.Threading.Timer?displayProperty=nameWithType>.</span></span>

## <a name="the-systemtimerstimer-class"></a><span data-ttu-id="c1e22-122">Klasa System. Timers. czasomierz</span><span class="sxs-lookup"><span data-stu-id="c1e22-122">The System.Timers.Timer class</span></span>

<span data-ttu-id="c1e22-123">Innym czasomierzem, który może być używany w środowisku wielowątkowym, jest to <xref:System.Timers.Timer?displayProperty=nameWithType> , że domyślnie wywołuje zdarzenie na <xref:System.Threading.ThreadPool> wątku.</span><span class="sxs-lookup"><span data-stu-id="c1e22-123">Another timer that can be used in a multithreaded environment is <xref:System.Timers.Timer?displayProperty=nameWithType> that by default raises an event on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="c1e22-124">Podczas tworzenia <xref:System.Timers.Timer?displayProperty=nameWithType> obiektu można określić przedział czasu, w którym ma zostać zgłoszone <xref:System.Timers.Timer.Elapsed> zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="c1e22-124">When you create a <xref:System.Timers.Timer?displayProperty=nameWithType> object, you may specify the time interval in which to raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="c1e22-125">Użyj <xref:System.Timers.Timer.Enabled%2A> właściwości, aby wskazać, czy czasomierz powinien zgłosić <xref:System.Timers.Timer.Elapsed> zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="c1e22-125">Use the <xref:System.Timers.Timer.Enabled%2A> property to indicate if a timer should raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="c1e22-126">Jeśli potrzebujesz <xref:System.Timers.Timer.Elapsed> zdarzenia, które ma zostać zgłoszone tylko raz po upływie określonego interwału, ustaw wartość <xref:System.Timers.Timer.AutoReset%2A> na `false` .</span><span class="sxs-lookup"><span data-stu-id="c1e22-126">If you need an <xref:System.Timers.Timer.Elapsed> event to be raised only once after the specified interval has elapsed, set the <xref:System.Timers.Timer.AutoReset%2A> to `false`.</span></span> <span data-ttu-id="c1e22-127">Wartość domyślna <xref:System.Timers.Timer.AutoReset%2A> Właściwości to `true` , co oznacza, że <xref:System.Timers.Timer.Elapsed> zdarzenie jest zgłaszane regularnie w interwale zdefiniowanym przez <xref:System.Timers.Timer.Interval%2A> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="c1e22-127">The default value of the <xref:System.Timers.Timer.AutoReset%2A> property is `true`, which means that an <xref:System.Timers.Timer.Elapsed> event is raised regularly at the interval defined by the <xref:System.Timers.Timer.Interval%2A> property.</span></span>

<span data-ttu-id="c1e22-128">Aby uzyskać więcej informacji i przykładów, zobacz <xref:System.Timers.Timer?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c1e22-128">For more information and examples, see <xref:System.Timers.Timer?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c1e22-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c1e22-129">See also</span></span>

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [<span data-ttu-id="c1e22-130">Wątkowość obiektów i funkcji</span><span class="sxs-lookup"><span data-stu-id="c1e22-130">Threading Objects and Features</span></span>](threading-objects-and-features.md)
