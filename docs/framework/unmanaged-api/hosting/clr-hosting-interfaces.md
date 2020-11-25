---
title: Interfejsy hostingu środowiska CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: 77f2ba64d9bdbe9793d56e88dae46fd506119ab8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719050"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="5dcf7-102">Interfejsy hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="5dcf7-102">CLR Hosting Interfaces</span></span>

<span data-ttu-id="5dcf7-103">W tej sekcji opisano interfejsy, które mogą być używane przez niezarządzane hosty do integrowania środowiska uruchomieniowego języka wspólnego (CLR) z aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="5dcf7-104">Informacje dotyczą .NET Framework w wersji 2,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="5dcf7-105">Te interfejsy umożliwiają hostowi kontrolowanie wielu innych aspektów środowiska uruchomieniowego niż było możliwe w wersjach 1,0 i 1,1 i zapewniają znacznie ściślejszą integrację między środowiskiem CLR a modelem wykonywania hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="5dcf7-106">W .NET Framework w wersji 1,0 i 1,1 model hostingu włączył niezarządzany host do załadowania środowiska CLR do procesu, skonfigurowania pewnych ustawień i otrzymywania powiadomień o zdarzeniach.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="5dcf7-107">Ogólnie rzecz biorąc, Host i środowisko CLR działały niezależnie w tym procesie.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="5dcf7-108">W .NET Framework w wersji 2,0 i nowszych nowe warstwy abstrakcji umożliwiają hostowi udostępnianie wielu zasobów, które są obecnie udostępniane przez typy w zestawie Win32, i poszerzają zestaw funkcji, które mogą być konfigurowane przez hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5dcf7-109">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="5dcf7-109">In This Section</span></span>  

 [<span data-ttu-id="5dcf7-110">IActionOnCLREvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-110">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)  
 <span data-ttu-id="5dcf7-111">Zapewnia metodę, która wykonuje wywołanie zwrotne dla zarejestrowanego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="5dcf7-112">IApartmentCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-112">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)  
 <span data-ttu-id="5dcf7-113">Zapewnia metody tworzenia wywołań zwrotnych w obrębie apartamentu.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="5dcf7-114">IAppDomainBinding — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-114">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)  
 <span data-ttu-id="5dcf7-115">Zapewnia metody ustawiania konfiguracji czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="5dcf7-116">ICatalogServices — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-116">ICatalogServices Interface</span></span>](icatalogservices-interface.md)  
 <span data-ttu-id="5dcf7-117">Dostarcza metody dla usług katalogowych.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="5dcf7-118">(Ten interfejs obsługuje infrastrukturę .NET Framework i nie jest przeznaczony do użycia bezpośrednio w kodzie).</span><span class="sxs-lookup"><span data-stu-id="5dcf7-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="5dcf7-119">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="5dcf7-120">Dostarcza metody, które obsługują komunikację między hostem i środowiskiem CLR o zestawach.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="5dcf7-121">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="5dcf7-122">Zarządza listą zestawów, które są ładowane przez środowisko CLR, a nie przez hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="5dcf7-123">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-123">ICLRControl Interface</span></span>](iclrcontrol-interface.md)  
 <span data-ttu-id="5dcf7-124">Zapewnia metody do uzyskiwania dostępu do hosta i konfigurowania różnych aspektów środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="5dcf7-125">ICLRDebugManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)  
 <span data-ttu-id="5dcf7-126">Dostarcza metody, które umożliwiają hostowi kojarzenie zestawu zadań z identyfikatorem i przyjazną nazwą.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="5dcf7-127">ICLRErrorReportingManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-127">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="5dcf7-128">Dostarcza metody, które umożliwiają hostowi skonfigurowanie niestandardowych zrzutów sterty na potrzeby raportowania błędów.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="5dcf7-129">ICLRGCManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-129">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)  
 <span data-ttu-id="5dcf7-130">Dostarcza metody, które umożliwiają hostowi współdziałanie z systemem odzyskiwania pamięci CLR.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="5dcf7-131">ICLRHostBindingPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-131">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="5dcf7-132">Zapewnia metody dla hosta do szacowania i przekazywania zmian w informacjach o zasadach dla zestawów.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="5dcf7-133">ICLRHostProtectionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-133">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="5dcf7-134">Umożliwia hostowi blokowanie określonych zarządzanych klas, metod, właściwości i pól z uruchamiania w częściowo zaufanym kodzie.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="5dcf7-135">ICLRIoCompletionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-135">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)  
 <span data-ttu-id="5dcf7-136">Implementuje metodę wywołania zwrotnego, która umożliwia hostowi powiadomienie środowiska CLR o stanie określonych żądań we/wy.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="5dcf7-137">ICLRMemoryNotificationCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-137">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="5dcf7-138">Umożliwia hostowi zgłaszanie warunków ciśnienia pamięci przy użyciu podejścia podobnego do `CreateMemoryResourceNotification` funkcji Win32.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="5dcf7-139">ICLROnEventManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-139">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)  
 <span data-ttu-id="5dcf7-140">Dostarcza metody, które umożliwiają hostowi rejestrowanie i Wyrejestrowywanie wywołań zwrotnych dla zdarzeń CLR.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="5dcf7-141">ICLRPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-141">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)  
 <span data-ttu-id="5dcf7-142">Dostarcza metody, które umożliwiają hostowi określenie akcji zasad, które mają być podejmowane w przypadku awarii i przekroczeń limitu czasu.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="5dcf7-143">ICLRProbingAssemblyEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-143">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="5dcf7-144">Dostarcza metody, które umożliwiają hostowi pobieranie tożsamości dla zestawu przy użyciu informacji o tożsamości zestawu, które są wewnętrzne dla środowiska CLR, bez konieczności tworzenia lub zrozumienia tożsamości.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="5dcf7-145">ICLRReferenceAssemblyEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-145">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="5dcf7-146">Dostarcza metody, które umożliwiają hostowi manipulowanie zestawem zestawów, do których odwołuje się plik lub strumień przy użyciu danych tożsamości zestawu, które są wewnętrzne dla środowiska CLR, bez konieczności tworzenia lub zrozumienia tych tożsamości.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="5dcf7-147">ICLRRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-147">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)  
 <span data-ttu-id="5dcf7-148">Oferuje funkcje podobne do [ICorRuntimeHost](icorruntimehost-interface.md)z dodatkową metodą ustawiania interfejsu sterowania hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-148">Provides capabilities similar to [ICorRuntimeHost](icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="5dcf7-149">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-149">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)  
 <span data-ttu-id="5dcf7-150">Zapewnia metody dla hosta do uzyskiwania informacji o żądanych zadaniach i wykrywania zakleszczenii w jego implementacji synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="5dcf7-151">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-151">ICLRTask Interface</span></span>](iclrtask-interface.md)  
 <span data-ttu-id="5dcf7-152">Dostarcza metody, które umożliwiają hostowi wykonywanie żądań CLR lub dostarczenie do środowiska CLR powiadomienia o skojarzonym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="5dcf7-153">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-153">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)  
 <span data-ttu-id="5dcf7-154">Dostarcza metody, które umożliwiają hostowi jawne żądanie, aby środowisko CLR utworzyło nowe zadanie, pobrać aktualnie wykonywane zadanie i ustawić język geograficzny i kulturę dla zadania.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="5dcf7-155">ICLRValidator — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-155">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)  
 <span data-ttu-id="5dcf7-156">Zapewnia metody sprawdzania poprawności przenośnych obrazów wykonywalnych (PE) i raportowania błędów walidacji.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="5dcf7-157">ICorConfiguration — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-157">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)  
 <span data-ttu-id="5dcf7-158">Zapewnia metody konfigurowania środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="5dcf7-159">ICorThreadpool — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-159">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)  
 <span data-ttu-id="5dcf7-160">Zapewnia metody uzyskiwania dostępu do puli wątków.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="5dcf7-161">IDebuggerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-161">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)  
 <span data-ttu-id="5dcf7-162">Zapewnia metody uzyskiwania informacji o stanie usług debugowania.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="5dcf7-163">IDebuggerThreadControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-163">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="5dcf7-164">Zapewnia metody powiadamiania hosta o blokowaniu i odblokowywaniu wątków przez usługi debugowania.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="5dcf7-165">IGCHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-165">IGCHost Interface</span></span>](igchost-interface.md)  
 <span data-ttu-id="5dcf7-166">Zapewnia metody uzyskiwania informacji o systemie odzyskiwania pamięci i kontrolowania niektórych aspektów wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="5dcf7-167">IGCHost2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-167">IGCHost2 Interface</span></span>](igchost2-interface.md)  
 <span data-ttu-id="5dcf7-168">Udostępnia metodę [SetGCStartupLimitsEx —](igchost2-setgcstartuplimitsex-method.md) , która umożliwia hostowi Ustawianie rozmiaru segmentu wyrzucania elementów bezużytecznych i maksymalnego rozmiaru generacji wynoszącego system wyrzucania elementów bezużytecznych do wartości większej niż `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="5dcf7-168">Provides the [SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="5dcf7-169">IGCHostControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-169">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)  
 <span data-ttu-id="5dcf7-170">Zapewnia metodę, która umożliwia modułowi wyrzucania elementów bezużytecznych żądanie zmiany limitów pamięci wirtualnej przez hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="5dcf7-171">IGCThreadControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-171">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)  
 <span data-ttu-id="5dcf7-172">Zapewnia metody uczestnictwa w planowaniu wątków, które w przeciwnym razie byłyby blokowane do wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="5dcf7-173">IHostAssemblyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-173">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)  
 <span data-ttu-id="5dcf7-174">Dostarcza metody, które umożliwiają hostowi określenie zestawów zestawów, które powinny być ładowane przez środowisko CLR lub przez hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="5dcf7-175">IHostAssemblyStore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-175">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)  
 <span data-ttu-id="5dcf7-176">Dostarcza metody, które umożliwiają hostowi załadowanie zestawów i modułów niezależnie od środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="5dcf7-177">IHostAutoEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-177">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)  
 <span data-ttu-id="5dcf7-178">Przedstawia reprezentację zdarzenia autoresetowania zaimplementowanego przez hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="5dcf7-179">IHostControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-179">IHostControl Interface</span></span>](ihostcontrol-interface.md)  
 <span data-ttu-id="5dcf7-180">Zapewnia metody konfigurowania ładowania zestawów i określania interfejsów hostingu obsługiwanych przez hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="5dcf7-181">IHostCrst — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-181">IHostCrst Interface</span></span>](ihostcrst-interface.md)  
 <span data-ttu-id="5dcf7-182">Służy jako reprezentacja hosta sekcji krytycznej dla wątków.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="5dcf7-183">IHostGCManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-183">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)  
 <span data-ttu-id="5dcf7-184">Dostarcza metody, które powiadamiają hosta zdarzeń w mechanizmie wyrzucania elementów bezużytecznych zaimplementowane przez środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="5dcf7-185">IHostIoCompletionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-185">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="5dcf7-186">Dostarcza metody, które umożliwiają współpracującie środowiska CLR z portami zakończenia we/wy dostarczonymi przez hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="5dcf7-187">IHostMalloc — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-187">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)  
 <span data-ttu-id="5dcf7-188">Dostarcza metody dla środowiska CLR do żądania szczegółowych alokacji ze sterty za pośrednictwem hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="5dcf7-189">IHostManualEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-189">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)  
 <span data-ttu-id="5dcf7-190">Zapewnia implementację hosta reprezentacji zdarzenia resetowania ręcznego.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="5dcf7-191">IHostMemoryManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-191">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)  
 <span data-ttu-id="5dcf7-192">Zapewnia metody środowiska CLR do przydzielenia żądań pamięci wirtualnej za pośrednictwem hosta zamiast używania standardowych funkcji pamięci wirtualnej Win32.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="5dcf7-193">IHostPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-193">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)  
 <span data-ttu-id="5dcf7-194">Dostarcza metody, które powiadamiają hosta o akcjach wykonywanych przez środowisko CLR w przypadku przerwań, przekroczeń limitu czasu lub niepowodzeń.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="5dcf7-195">IHostSecurityContext — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-195">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)  
 <span data-ttu-id="5dcf7-196">Włącza środowisko CLR do obsługi informacji kontekstu zabezpieczeń implementowanych przez hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="5dcf7-197">IHostSecurityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-197">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)  
 <span data-ttu-id="5dcf7-198">Zapewnia metody umożliwiające dostęp do i kontrolę nad kontekstem zabezpieczeń aktualnie wykonywanego wątku.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="5dcf7-199">IHostSemaphore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-199">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)  
 <span data-ttu-id="5dcf7-200">Przedstawia reprezentację semafora zaimplementowanego przez hosta.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="5dcf7-201">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-201">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="5dcf7-202">Zapewnia metody dla środowiska CLR do tworzenia elementów pierwotnych synchronizacji przez wywołanie hosta zamiast korzystania z funkcji synchronizacji Win32.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="5dcf7-203">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-203">IHostTask Interface</span></span>](ihosttask-interface.md)  
 <span data-ttu-id="5dcf7-204">Zapewnia metody umożliwiające komunikację środowiska CLR z hostem w celu zarządzania zadaniami.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="5dcf7-205">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-205">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)  
 <span data-ttu-id="5dcf7-206">Zapewnia metody umożliwiające współdziałanie środowiska CLR z zadaniami za pośrednictwem hosta zamiast korzystania ze standardowego wątku lub funkcji światłowodowych systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="5dcf7-207">IHostThreadPoolManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-207">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="5dcf7-208">Zapewnia metody dla środowiska CLR w celu skonfigurowania puli wątków i umieszczania w kolejce elementów roboczych w puli wątków.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="5dcf7-209">IManagedObject — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-209">IManagedObject Interface</span></span>](imanagedobject-interface.md)  
 <span data-ttu-id="5dcf7-210">Zapewnia metody kontrolowania obiektu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="5dcf7-211">IObjectHandle</span><span class="sxs-lookup"><span data-stu-id="5dcf7-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="5dcf7-212">Zapewnia metodę odpakowania obiektów marshal-by-Value z operatora pośredni.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="5dcf7-213">ITypeName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-213">ITypeName Interface</span></span>](itypename-interface.md)  
 <span data-ttu-id="5dcf7-214">Zapewnia metody uzyskiwania informacji o nazwie typu.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="5dcf7-215">(Ten interfejs obsługuje infrastrukturę .NET Framework i nie jest przeznaczony do użycia bezpośrednio w kodzie).</span><span class="sxs-lookup"><span data-stu-id="5dcf7-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="5dcf7-216">ITypeNameBuilder — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-216">ITypeNameBuilder Interface</span></span>](itypenamebuilder-interface.md)  
 <span data-ttu-id="5dcf7-217">Zapewnia metody tworzenia nazwy typu.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-217">Provides methods for building a type name.</span></span> <span data-ttu-id="5dcf7-218">(Ten interfejs obsługuje infrastrukturę .NET Framework i nie jest przeznaczony do użycia bezpośrednio w kodzie).</span><span class="sxs-lookup"><span data-stu-id="5dcf7-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="5dcf7-219">ITypeNameFactory — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5dcf7-219">ITypeNameFactory Interface</span></span>](itypenamefactory-interface.md)  
 <span data-ttu-id="5dcf7-220">Dostarcza metody służące do dekonstrukcji nazwy typu.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="5dcf7-221">(Ten interfejs obsługuje infrastrukturę .NET Framework i nie jest przeznaczony do użycia bezpośrednio w kodzie).</span><span class="sxs-lookup"><span data-stu-id="5dcf7-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="5dcf7-222">IValidator</span><span class="sxs-lookup"><span data-stu-id="5dcf7-222">"IValidator"</span></span>  
 <span data-ttu-id="5dcf7-223">Zapewnia metody sprawdzania poprawności przenośnych obrazów wykonywalnych (PE) i raportowania błędów walidacji.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5dcf7-224">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="5dcf7-224">Related Sections</span></span>  

 [<span data-ttu-id="5dcf7-225">Przestarzałe klasy coclass i interfejsy hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="5dcf7-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="5dcf7-226">Zawiera tematy opisujące Interfejsy hostingu dostępne w .NET Framework w wersji 1,0 i 1,1.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="5dcf7-227">Interfejsy hostingu środowiska CLR dodane w programie .NET Framework 4 i 4.5</span><span class="sxs-lookup"><span data-stu-id="5dcf7-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="5dcf7-228">Zawiera tematy opisujące Interfejsy hostingu dostępne w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5dcf7-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>
