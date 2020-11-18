---
title: Wątki pierwszego planu i tła
description: Określ lub Zmień, czy wątek jest wątkiem w tle, czy też wątkiem pierwszego planu przy użyciu właściwości Thread. IsBackground w programie .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- threading [.NET], foreground
- threading [.NET], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
ms.openlocfilehash: 9f0ea1d53eb2f96b8a56cacc089cf90eb2f079a0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819906"
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="b4d2c-103">Wątki pierwszego planu i tła</span><span class="sxs-lookup"><span data-stu-id="b4d2c-103">Foreground and background threads</span></span>

<span data-ttu-id="b4d2c-104">Zarządzany wątek jest wątkiem w tle lub wątkiem pierwszego planu.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-104">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="b4d2c-105">Wątki w tle są takie same jak wątki pierwszego planu z jednym wyjątkiem: wątek w tle nie utrzymuje uruchomionego środowiska wykonywania zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-105">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="b4d2c-106">Po zatrzymaniu wszystkich wątków pierwszego planu w procesie zarządzanym (gdzie plik exe jest zestawem zarządzanym) system zatrzymuje wszystkie wątki w tle i zamyka.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-106">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4d2c-107">Gdy środowisko uruchomieniowe zatrzyma wątek w tle, ponieważ trwa zamykanie procesu, w wątku nie jest zgłaszany żaden wyjątek.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-107">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="b4d2c-108">Jeśli jednak wątki są zatrzymane, ponieważ <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> metoda zwalnia domenę aplikacji, <xref:System.Threading.ThreadAbortException> jest zgłaszany zarówno w wątku na pierwszym planie, jak i w tle.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-108">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="b4d2c-109">Użyj <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> właściwości, aby określić, czy wątek jest wątkiem w tle, czy na pierwszym planie czy zmienić jego stan.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-109">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="b4d2c-110">Wątek można w dowolnym momencie zmienić na wątek w tle przez ustawienie jego <xref:System.Threading.Thread.IsBackground%2A> właściwości na `true` .</span><span class="sxs-lookup"><span data-stu-id="b4d2c-110">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b4d2c-111">Stan pierwszego planu lub tła wątku nie wpływa na wynik nieobsługiwanego wyjątku w wątku.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-111">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="b4d2c-112">Nieobsłużony wyjątek w wątkach na pierwszym planie lub w tle powoduje zakończenie działania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-112">An unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="b4d2c-113">Zobacz [wyjątki w zarządzanych wątkach](exceptions-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="b4d2c-113">See [Exceptions in Managed Threads](exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="b4d2c-114">Wątki należące do puli wątków zarządzanych (czyli wątki, których <xref:System.Threading.Thread.IsThreadPoolThread%2A> Właściwość jest `true` ) są wątkami w tle.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-114">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="b4d2c-115">Wszystkie wątki, które wprowadzają zarządzane środowisko wykonawcze z kodu niezarządzanego, są oznaczane jako wątki w tle.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-115">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="b4d2c-116">Wszystkie wątki wygenerowane przez tworzenie i uruchamianie nowego <xref:System.Threading.Thread> obiektu są domyślnie wątki pierwszego planu.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-116">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="b4d2c-117">Jeśli użyjesz wątku do monitorowania działania, takiego jak połączenie gniazda, ustaw jego <xref:System.Threading.Thread.IsBackground%2A> Właściwość na `true` tak, aby wątek nie uniemożliwił przerwania procesu.</span><span class="sxs-lookup"><span data-stu-id="b4d2c-117">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d2c-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b4d2c-118">See also</span></span>

- <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>
- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadAbortException>
