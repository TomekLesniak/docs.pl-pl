---
title: fatalExecutionEngineError MDA
description: Zapoznaj się z asystentem debugowania zarządzanego fatalExecutionEngineError (MDA) w programie .NET, który może zostać aktywowany z powodu nieoczekiwanego zakończenia procesu.
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
ms.openlocfilehash: a9347338d53755b74b3ff291f75cb6b221134130
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244278"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="0c289-103">fatalExecutionEngineError MDA</span><span class="sxs-lookup"><span data-stu-id="0c289-103">fatalExecutionEngineError MDA</span></span>

<span data-ttu-id="0c289-104">`fatalExecutionEngineError`Asystent debugowania zarządzanego (MDA) jest uaktywniany w przypadku wykrycia błędu krytycznego w środowisku uruchomieniowym języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="0c289-104">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="0c289-105">Proces zostanie zakończony.</span><span class="sxs-lookup"><span data-stu-id="0c289-105">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0c289-106">Objawy</span><span class="sxs-lookup"><span data-stu-id="0c289-106">Symptoms</span></span>  

 <span data-ttu-id="0c289-107">Nieoczekiwane zakończenie procesu.</span><span class="sxs-lookup"><span data-stu-id="0c289-107">Unexpected process termination.</span></span> <span data-ttu-id="0c289-108">Nie można ustalić innych objawów, ponieważ awaria środowiska CLR może wystąpić z różnych powodów.</span><span class="sxs-lookup"><span data-stu-id="0c289-108">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0c289-109">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="0c289-109">Cause</span></span>  

 <span data-ttu-id="0c289-110">Środowisko CLR zostało uszkodzone w sposób krytyczny.</span><span class="sxs-lookup"><span data-stu-id="0c289-110">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="0c289-111">Jest to najczęściej spowodowane uszkodzeniem danych, które może być spowodowane przez wiele problemów, takich jak wywołania źle sformułowanej platformy wywołania funkcji i przekazywanie nieprawidłowych danych do środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="0c289-111">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0c289-112">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="0c289-112">Resolution</span></span>  

 <span data-ttu-id="0c289-113">Włączenie dodatkowych MDA może pomóc w zidentyfikowaniu problemu.</span><span class="sxs-lookup"><span data-stu-id="0c289-113">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="0c289-114">Następujący MDA może być szczególnie przydatny w diagnozowaniu problemu:</span><span class="sxs-lookup"><span data-stu-id="0c289-114">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="0c289-115">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="0c289-115">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="0c289-116">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="0c289-116">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="0c289-117">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="0c289-117">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="0c289-118">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="0c289-118">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="0c289-119">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="0c289-119">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="0c289-120">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="0c289-120">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="0c289-121">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="0c289-121">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="0c289-122">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="0c289-122">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="0c289-123">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="0c289-123">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="0c289-124">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="0c289-124">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="0c289-125">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="0c289-125">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="0c289-126">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="0c289-126">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0c289-127">Wpływ na środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="0c289-127">Effect on the Runtime</span></span>  

 <span data-ttu-id="0c289-128">To zdarzenie MDA nie ma wpływu na zachowanie środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="0c289-128">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0c289-129">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="0c289-129">Output</span></span>  

 <span data-ttu-id="0c289-130">Adres funkcji CLR, która spowodowała błąd krytyczny, identyfikator wątku, w którym wystąpił błąd, oraz kod błędu.</span><span class="sxs-lookup"><span data-stu-id="0c289-130">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0c289-131">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="0c289-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c289-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0c289-132">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="0c289-133">Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="0c289-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
