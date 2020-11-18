---
title: Przegląd Async
description: Dowiedz się, w jaki sposób programowanie asynchroniczne jest prostą techniką, która ułatwia obsługę blokowania operacji we/wy i współbieżnych na wielu rdzeniach.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.openlocfilehash: 495f225a3732812666dfa2f5c8c07f6f5b849c95
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824808"
---
# <a name="async-overview"></a><span data-ttu-id="49da3-103">Przegląd Async</span><span class="sxs-lookup"><span data-stu-id="49da3-103">Async Overview</span></span>

<span data-ttu-id="49da3-104">Tak długo aplikacje były szybsze po prostu przez zakup nowszego komputera lub serwera, a następnie ten trend został zatrzymany.</span><span class="sxs-lookup"><span data-stu-id="49da3-104">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="49da3-105">W rzeczywistości została odwrócona.</span><span class="sxs-lookup"><span data-stu-id="49da3-105">In fact, it reversed.</span></span> <span data-ttu-id="49da3-106">Pojawiły się telefony komórkowe z 1ghzą pojedyncze podstawowe wióry ARM i obciążenia serwera przenoszone do maszyn wirtualnych.</span><span class="sxs-lookup"><span data-stu-id="49da3-106">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="49da3-107">Użytkownicy nadal chcą, aby właściciele interfejsu użytkownika i biznesowe chcą, aby serwery były skalowane wraz z ich działalnością biznesową.</span><span class="sxs-lookup"><span data-stu-id="49da3-107">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="49da3-108">Przejście do urządzeń przenośnych i chmurowych oraz połączona z Internetem populacja >3B użytkowników spowodowało powstanie nowego zestawu wzorców oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="49da3-108">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span>

- <span data-ttu-id="49da3-109">Aplikacje klienckie powinny być zawsze włączone, zawsze połączone i stale reagować na interakcję z użytkownikiem (na przykład Touch) ze wszystkimi klasyfikacjami w sklepie App Store.</span><span class="sxs-lookup"><span data-stu-id="49da3-109">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
- <span data-ttu-id="49da3-110">Usługi powinny obsłużyć wzrost ruchu przez bezpieczne skalowanie w górę i w dół.</span><span class="sxs-lookup"><span data-stu-id="49da3-110">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span>

<span data-ttu-id="49da3-111">Programowanie asynchroniczne to kluczowa technika, która ułatwia obsługę blokowania operacji we/wy i współbieżnych na wielu rdzeniach.</span><span class="sxs-lookup"><span data-stu-id="49da3-111">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="49da3-112">Platforma .NET umożliwia aplikacjom i usługom reagowanie na wydajność i elastyczność przy użyciu łatwych w użyciu modeli programów asynchronicznych na poziomie języka w językach C#, Visual Basic i F #.</span><span class="sxs-lookup"><span data-stu-id="49da3-112">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, Visual Basic, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="49da3-113">Dlaczego warto pisać kod asynchroniczny?</span><span class="sxs-lookup"><span data-stu-id="49da3-113">Why Write Async Code?</span></span>

<span data-ttu-id="49da3-114">Nowoczesne aplikacje wykorzystują wiele operacji we/wy plików i sieci.</span><span class="sxs-lookup"><span data-stu-id="49da3-114">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="49da3-115">Interfejsy API we/wy tradycyjnie domyślnie blokują, co powoduje słabą obsługę użytkowników i wykorzystanie sprzętu, chyba że chcesz poznać i korzystać z niewielkich wzorców.</span><span class="sxs-lookup"><span data-stu-id="49da3-115">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="49da3-116">Asynchroniczne interfejsy API oparte na zadaniach i asynchroniczny model programowania na poziomie języka odwracają ten model, dzięki czemu asynchroniczne wykonywanie jest domyślnie z kilkoma nowymi koncepcjami, które należy poznać.</span><span class="sxs-lookup"><span data-stu-id="49da3-116">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="49da3-117">Kod asynchroniczny ma następującą charakterystykę:</span><span class="sxs-lookup"><span data-stu-id="49da3-117">Async code has the following characteristics:</span></span>

- <span data-ttu-id="49da3-118">Obsługuje więcej żądań serwera, uzyskując wątki do obsługi większej liczby żądań podczas oczekiwania na zwrócenie żądań we/wy.</span><span class="sxs-lookup"><span data-stu-id="49da3-118">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
- <span data-ttu-id="49da3-119">Umożliwia interfejsów użytkownika więcej odpowiedzi przez uzyskanie wątków do interakcji z interfejsem użytkownika podczas oczekiwania na żądania we/wy i przez przeniesienie długotrwałej pracy na inne rdzenie procesora.</span><span class="sxs-lookup"><span data-stu-id="49da3-119">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
- <span data-ttu-id="49da3-120">Wiele nowszych interfejsów API platformy .NET jest asynchronicznie.</span><span class="sxs-lookup"><span data-stu-id="49da3-120">Many of the newer .NET APIs are asynchronous.</span></span>
- <span data-ttu-id="49da3-121">W programie .NET można łatwo pisać kod asynchroniczny.</span><span class="sxs-lookup"><span data-stu-id="49da3-121">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="49da3-122">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="49da3-122">What's next?</span></span>

<span data-ttu-id="49da3-123">Więcej informacji znajduje się w temacie [Async in głębokości](async-in-depth.md) .</span><span class="sxs-lookup"><span data-stu-id="49da3-123">For more information, see the [Async in depth](async-in-depth.md) topic.</span></span>

<span data-ttu-id="49da3-124">Temat [wzorce programowania asynchronicznego](asynchronous-programming-patterns/index.md) zawiera przegląd trzech asynchronicznych wzorców programowania obsługiwanych w programie .NET:</span><span class="sxs-lookup"><span data-stu-id="49da3-124">The [Asynchronous Programming Patterns](asynchronous-programming-patterns/index.md) topic provides an overview of the three asynchronous programming patterns supported in .NET:</span></span>  
  
- <span data-ttu-id="49da3-125">[Model programowania asynchronicznego (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (starsza wersja)</span><span class="sxs-lookup"><span data-stu-id="49da3-125">[Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (legacy)</span></span>  
  
- <span data-ttu-id="49da3-126">[Wzorzec asynchroniczny oparty na zdarzeniach (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (starsza wersja)</span><span class="sxs-lookup"><span data-stu-id="49da3-126">[Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (legacy)</span></span>  
  
- <span data-ttu-id="49da3-127">[Wzorzec asynchroniczny oparty na zadaniach (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (zalecany dla nowego programowania)</span><span class="sxs-lookup"><span data-stu-id="49da3-127">[Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (recommended for new development)</span></span>  

<span data-ttu-id="49da3-128">Aby uzyskać więcej informacji na temat zalecanego modelu programowania opartego na zadaniach, zapoznaj się z tematem [programowanie asynchroniczne oparte na zadaniach](parallel-programming/task-based-asynchronous-programming.md) .</span><span class="sxs-lookup"><span data-stu-id="49da3-128">For more information about recommended task-based programming model, see the [Task-based asynchronous programming](parallel-programming/task-based-asynchronous-programming.md) topic.</span></span>
