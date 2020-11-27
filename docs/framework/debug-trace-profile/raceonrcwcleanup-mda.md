---
title: raceOnRCWCleanup MDA
description: Zapoznaj się z asystentem debugowania zarządzanego raceOnRCWCleanup (MDA), który jest uaktywniany, gdy Otoka RCW jest używana w innym wątku lub na wolnym stosie wątków w programie .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
ms.openlocfilehash: 393c5ea44108445a9a1a9d16e7d1d192eced5740
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271450"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="cdde1-103">raceOnRCWCleanup MDA</span><span class="sxs-lookup"><span data-stu-id="cdde1-103">raceOnRCWCleanup MDA</span></span>

<span data-ttu-id="cdde1-104">`raceOnRCWCleanup`Asystent debugowania zarządzanego (MDA) jest uaktywniany, gdy środowisko uruchomieniowe języka wspólnego (CLR) wykryje, że w [środowisku uruchomieniowym](../../standard/native-interop/runtime-callable-wrapper.md) (otoka), gdy wywołanie do wydania jest używane, za pomocą polecenia, takiego jak <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> Metoda.</span><span class="sxs-lookup"><span data-stu-id="cdde1-104">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="cdde1-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="cdde1-105">Symptoms</span></span>  

 <span data-ttu-id="cdde1-106">Naruszenia zasad dostępu lub uszkodzenia pamięci w trakcie lub po zwolnieniu otoki RCW przy użyciu <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> metody lub podobnej.</span><span class="sxs-lookup"><span data-stu-id="cdde1-106">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="cdde1-107">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="cdde1-107">Cause</span></span>  

 <span data-ttu-id="cdde1-108">Otoka RCW jest używana w innym wątku lub na stosie wolnego wątku.</span><span class="sxs-lookup"><span data-stu-id="cdde1-108">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="cdde1-109">Nie można zwolnić otoki RCW, która jest używana.</span><span class="sxs-lookup"><span data-stu-id="cdde1-109">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="cdde1-110">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="cdde1-110">Resolution</span></span>  

 <span data-ttu-id="cdde1-111">Nie zwalniaj otoki RCW, która może być używana w bieżącym lub w innych wątkach.</span><span class="sxs-lookup"><span data-stu-id="cdde1-111">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="cdde1-112">Wpływ na środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="cdde1-112">Effect on the Runtime</span></span>  

 <span data-ttu-id="cdde1-113">To zdarzenie MDA nie ma wpływu na środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="cdde1-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="cdde1-114">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="cdde1-114">Output</span></span>  

 <span data-ttu-id="cdde1-115">Komunikat z opisem błędu.</span><span class="sxs-lookup"><span data-stu-id="cdde1-115">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="cdde1-116">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="cdde1-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdde1-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cdde1-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="cdde1-118">Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="cdde1-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="cdde1-119">Organizowanie międzyoperacyjne</span><span class="sxs-lookup"><span data-stu-id="cdde1-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
