---
title: disconnectedContext MDA
description: Zapoznaj się z asystentem debugowania zarządzanego disconnectedContext w programie .NET, który jest wywoływany, gdy środowisko CLR podejmie próbę przejścia do odłączonego apartamentu lub kontekstu.
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
ms.openlocfilehash: 35e393ab6af2e2c14425dc50a164332120e3fa1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273545"
---
# <a name="disconnectedcontext-mda"></a><span data-ttu-id="dd9c3-103">disconnectedContext MDA</span><span class="sxs-lookup"><span data-stu-id="dd9c3-103">disconnectedContext MDA</span></span>

<span data-ttu-id="dd9c3-104">`disconnectedContext`Asystent debugowania zarządzanego (MDA) jest uaktywniany, gdy środowisko CLR próbuje przejść do odłączonego apartamentu lub kontekstu podczas obsługi żądania dotyczącego obiektu com.</span><span class="sxs-lookup"><span data-stu-id="dd9c3-104">The `disconnectedContext` managed debugging assistant (MDA) is activated when the CLR attempts to transition into a disconnected apartment or context while servicing a request concerning a COM object.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="dd9c3-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="dd9c3-105">Symptoms</span></span>  

 <span data-ttu-id="dd9c3-106">Wywołania wywoływanej [otoki środowiska uruchomieniowego](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) są dostarczane do źródłowego składnika COM w bieżącym elemencie Apartment lub Context, a nie na tym, w którym istnieją.</span><span class="sxs-lookup"><span data-stu-id="dd9c3-106">Calls made on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) are delivered to the underlying COM component in the current apartment or context instead of the one in which they exist.</span></span> <span data-ttu-id="dd9c3-107">Może to spowodować uszkodzenie lub utratę danych, jeśli składnik COM nie jest wielowątkowy, tak jak w przypadku składników jednowątkowego apartamentu (STA).</span><span class="sxs-lookup"><span data-stu-id="dd9c3-107">This can cause corruption and or data loss if the COM component is not multithreaded, as in the case of single-threaded apartment (STA) components.</span></span> <span data-ttu-id="dd9c3-108">Alternatywnie, jeśli OTOKa jest samodzielnym serwerem proxy, wywołanie może spowodować wyrzucanie z wynikami <xref:System.Runtime.InteropServices.COMException> HRESULT RPC_E_WRONG_THREAD.</span><span class="sxs-lookup"><span data-stu-id="dd9c3-108">Alternatively, if the RCW is itself a proxy, the call might result in the throwing of a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="dd9c3-109">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="dd9c3-109">Cause</span></span>  

 <span data-ttu-id="dd9c3-110">Obiekt OLE Apartment lub kontekst został zamknięty, gdy środowisko CLR podejmie próbę przejścia do niego.</span><span class="sxs-lookup"><span data-stu-id="dd9c3-110">The OLE apartment or context has been shut down when the CLR attempts to transition into it.</span></span> <span data-ttu-id="dd9c3-111">Jest to najczęściej spowodowane tym, że STA apartamentach jest zamykany przed całkowitym udostępnieniem wszystkich składników modelu COM należących do apartamentu. może się to zdarzyć w wyniku jawnego wywołania kodu użytkownika na otoki RCW lub gdy środowisko CLR operuje na składniku COM, na przykład gdy środowisko CLR zwalnia składnik COM, gdy skojarzona Otoka RCW została odtworzona.</span><span class="sxs-lookup"><span data-stu-id="dd9c3-111">This is most commonly caused by STA apartments being shut down before all the COM components owned by the apartment were completely released This can occur as a result of an explicit call from user code on an RCW or while the CLR itself is manipulating the COM component, for example when the CLR is releasing the COM component when the associated RCW has been garbage collected.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="dd9c3-112">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="dd9c3-112">Resolution</span></span>  

 <span data-ttu-id="dd9c3-113">Aby uniknąć tego problemu, upewnij się, że wątek, który jest właścicielem STA, nie zakończy się przed zakończeniem działania aplikacji ze wszystkimi obiektami, które znajdują się w apartamentu.</span><span class="sxs-lookup"><span data-stu-id="dd9c3-113">To avoid this problem, ensure the thread that owns the STA does not terminate before the application has finished with all the objects that live in the apartment.</span></span> <span data-ttu-id="dd9c3-114">To samo dotyczy kontekstów; Upewnij się, że konteksty nie są zamykane, zanim aplikacja zostanie całkowicie zakończona wszystkimi składnikami COM znajdującymi się wewnątrz tego kontekstu.</span><span class="sxs-lookup"><span data-stu-id="dd9c3-114">The same applies to contexts; ensure contexts are not shut down before the application is completely finished with any COM components that live inside the context.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="dd9c3-115">Wpływ na środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="dd9c3-115">Effect on the Runtime</span></span>  

 <span data-ttu-id="dd9c3-116">To zdarzenie MDA nie ma wpływu na środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="dd9c3-116">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="dd9c3-117">Raport dotyczy tylko danych o rozłączonym kontekście.</span><span class="sxs-lookup"><span data-stu-id="dd9c3-117">It only reports data about the disconnected context.</span></span>  
  
## <a name="output"></a><span data-ttu-id="dd9c3-118">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="dd9c3-118">Output</span></span>  

 <span data-ttu-id="dd9c3-119">Raportuje plik cookie kontekstu odłączonego apartamentu lub kontekstu.</span><span class="sxs-lookup"><span data-stu-id="dd9c3-119">Reports the context cookie of the disconnected apartment or context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="dd9c3-120">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="dd9c3-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd9c3-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dd9c3-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="dd9c3-122">Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="dd9c3-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="dd9c3-123">Organizowanie międzyoperacyjne</span><span class="sxs-lookup"><span data-stu-id="dd9c3-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
