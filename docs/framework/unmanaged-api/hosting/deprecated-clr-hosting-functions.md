---
title: Przestarzałe funkcje hostingu środowiska CLR
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 9e19502672973f292991b72c7ea9b4fdc17f5707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673127"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="dabfe-102">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="dabfe-102">Deprecated CLR Hosting Functions</span></span>

<span data-ttu-id="dabfe-103">W tej sekcji opisano niezarządzane globalne funkcje statyczne, które są używane we wcześniejszych wersjach interfejsu API hostingu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="dabfe-104">Z wyjątkiem funkcji infrastruktury ( `_Cor*` funkcji), które są używane tylko przez .NET Framework, funkcje te zostały zaniechane w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="dabfe-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="dabfe-105">Funkcje aktywacji</span><span class="sxs-lookup"><span data-stu-id="dabfe-105">Activation functions</span></span>  

 [<span data-ttu-id="dabfe-106">ClrCreateManagedInstance — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-106">ClrCreateManagedInstance Function</span></span>](clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="dabfe-107">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-107">Deprecated.</span></span> <span data-ttu-id="dabfe-108">Tworzy wystąpienie określonego typu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="dabfe-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="dabfe-109">CoInitializeCor — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-109">CoInitializeCor Function</span></span>](coinitializecor-function.md)  
 <span data-ttu-id="dabfe-110">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="dabfe-110">Obsolete.</span></span> <span data-ttu-id="dabfe-111">Aby zainicjować środowisko uruchomieniowe języka wspólnego (CLR), użyj opcji [CorBindToRuntimeEx](corbindtoruntimeex-function.md) lub [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="dabfe-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="dabfe-112">CoInitializeEE — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-112">CoInitializeEE Function</span></span>](coinitializeee-function.md)  
 <span data-ttu-id="dabfe-113">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-113">Deprecated.</span></span> <span data-ttu-id="dabfe-114">Zapewnia, że aparat wykonywania CLR jest ładowany do procesu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="dabfe-115">Zamiast tego użyj metody [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dabfe-115">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="dabfe-116">CorBindToCurrentRuntime — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-116">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)  
 <span data-ttu-id="dabfe-117">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-117">Deprecated.</span></span> <span data-ttu-id="dabfe-118">Ładuje środowisko uruchomieniowe języka wspólnego (CLR) do procesu przy użyciu informacji o wersji przechowywanych w pliku XML.</span><span class="sxs-lookup"><span data-stu-id="dabfe-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="dabfe-119">CorBindToRuntime — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-119">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)  
 <span data-ttu-id="dabfe-120">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-120">Deprecated.</span></span> <span data-ttu-id="dabfe-121">Umożliwia niezarządzanym hostom ładowanie środowiska CLR do procesu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="dabfe-122">CorBindToRuntimeByCfg — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-122">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="dabfe-123">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-123">Deprecated.</span></span> <span data-ttu-id="dabfe-124">Ładuje środowisko CLR do procesu przy użyciu informacji o wersji, które są odczytywane z pliku XML.</span><span class="sxs-lookup"><span data-stu-id="dabfe-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="dabfe-125">CorBindToRuntimeEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-125">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)  
 <span data-ttu-id="dabfe-126">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-126">Deprecated.</span></span> <span data-ttu-id="dabfe-127">Włącza niezarządzane hosty do załadowania środowiska CLR do procesu i pozwala ustawić flagi, aby określić zachowanie środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="dabfe-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="dabfe-128">CorBindToRuntimeHost — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)  
 <span data-ttu-id="dabfe-129">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-129">Deprecated.</span></span> <span data-ttu-id="dabfe-130">Włącza hosty do załadowania określonej wersji środowiska CLR do procesu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="dabfe-131">GetCORRequiredVersion — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-131">GetCORRequiredVersion Function</span></span>](getcorrequiredversion-function.md)  
 <span data-ttu-id="dabfe-132">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-132">Deprecated.</span></span> <span data-ttu-id="dabfe-133">Pobiera wymagany numer wersji środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="dabfe-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="dabfe-134">GetCORSystemDirectory — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-134">GetCORSystemDirectory Function</span></span>](getcorsystemdirectory-function.md)  
 <span data-ttu-id="dabfe-135">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-135">Deprecated.</span></span> <span data-ttu-id="dabfe-136">Zwraca katalog instalacyjny środowiska CLR, który jest ładowany do procesu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="dabfe-137">GetRealProcAddress — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-137">GetRealProcAddress Function</span></span>](getrealprocaddress-function.md)  
 <span data-ttu-id="dabfe-138">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-138">Deprecated.</span></span> <span data-ttu-id="dabfe-139">Pobiera adres określonej funkcji wyeksportowanej z najnowszej zainstalowanej wersji środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="dabfe-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="dabfe-140">GetRequestedRuntimeInfo — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-140">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="dabfe-141">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-141">Deprecated.</span></span> <span data-ttu-id="dabfe-142">Pobiera informacje o wersji i katalogu dla środowiska CLR żądanego przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="dabfe-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="dabfe-143">Funkcje wersji środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="dabfe-143">CLR version functions</span></span>  

 <span data-ttu-id="dabfe-144">Funkcje w tej sekcji zwracają wersję środowiska CLR; nie aktywuje środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="dabfe-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="dabfe-145">GetCORVersion — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-145">GetCORVersion Function</span></span>](getcorversion-function.md)  
 <span data-ttu-id="dabfe-146">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-146">Deprecated.</span></span> <span data-ttu-id="dabfe-147">Zwraca numer wersji środowiska CLR uruchomionego w bieżącym procesie.</span><span class="sxs-lookup"><span data-stu-id="dabfe-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="dabfe-148">GetFileVersion — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-148">GetFileVersion Function</span></span>](getfileversion-function.md)  
 <span data-ttu-id="dabfe-149">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-149">Deprecated.</span></span> <span data-ttu-id="dabfe-150">Pobiera informacje o wersji środowiska CLR określonego pliku przy użyciu określonego buforu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="dabfe-151">GetRequestedRuntimeVersion — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-151">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)  
 <span data-ttu-id="dabfe-152">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-152">Deprecated.</span></span> <span data-ttu-id="dabfe-153">Pobiera numer wersji środowiska CLR żądanego przez określoną aplikację.</span><span class="sxs-lookup"><span data-stu-id="dabfe-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="dabfe-154">Jeśli ta wersja nie jest zainstalowana, program pobierze najnowszą wersję, która jest zainstalowana przed żądaną wersją.</span><span class="sxs-lookup"><span data-stu-id="dabfe-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="dabfe-155">GetRequestedRuntimeVersionForCLSID — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="dabfe-156">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-156">Deprecated.</span></span> <span data-ttu-id="dabfe-157">Pobiera odpowiednie informacje o wersji środowiska CLR dla klasy o określonym identyfikatorze CLSID.</span><span class="sxs-lookup"><span data-stu-id="dabfe-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="dabfe-158">GetVersionFromProcess — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-158">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)  
 <span data-ttu-id="dabfe-159">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-159">Deprecated.</span></span> <span data-ttu-id="dabfe-160">Pobiera numer wersji środowiska CLR skojarzonego z określonym dojściem do procesu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="dabfe-161">LockClrVersion — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-161">LockClrVersion Function</span></span>](lockclrversion-function.md)  
 <span data-ttu-id="dabfe-162">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-162">Deprecated.</span></span> <span data-ttu-id="dabfe-163">Umożliwia hostowi określenie, która wersja środowiska CLR zostanie użyta w procesie przed jawnym inicjalizacją środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="dabfe-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="dabfe-164">Funkcje hostingu</span><span class="sxs-lookup"><span data-stu-id="dabfe-164">Hosting functions</span></span>  

 [<span data-ttu-id="dabfe-165">CallFunctionShim — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-165">CallFunctionShim Function</span></span>](callfunctionshim-function.md)  
 <span data-ttu-id="dabfe-166">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-166">Deprecated.</span></span> <span data-ttu-id="dabfe-167">Wywołuje funkcję, która ma określoną nazwę i parametry w określonej bibliotece.</span><span class="sxs-lookup"><span data-stu-id="dabfe-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="dabfe-168">CoEEShutDownCOM — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-168">CoEEShutDownCOM Function</span></span>](coeeshutdowncom-function.md)  
 <span data-ttu-id="dabfe-169">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-169">Deprecated.</span></span> <span data-ttu-id="dabfe-170">Zwalnia zestaw COM z procesu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="dabfe-171">CorExitProcess — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-171">CorExitProcess Function</span></span>](corexitprocess-function.md)  
 <span data-ttu-id="dabfe-172">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-172">Deprecated.</span></span> <span data-ttu-id="dabfe-173">Zamyka bieżący proces niezarządzany.</span><span class="sxs-lookup"><span data-stu-id="dabfe-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="dabfe-174">CorLaunchApplication — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-174">CorLaunchApplication Function</span></span>](corlaunchapplication-function.md)  
 <span data-ttu-id="dabfe-175">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-175">Deprecated.</span></span> <span data-ttu-id="dabfe-176">Uruchamia aplikację pod określoną ścieżką sieciową przy użyciu określonych manifestów i innych danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="dabfe-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="dabfe-177">CorMarkThreadInThreadPool — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-177">CorMarkThreadInThreadPool Function</span></span>](cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="dabfe-178">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-178">Deprecated.</span></span> <span data-ttu-id="dabfe-179">Oznacza aktualnie wykonywany wątek puli wątków na potrzeby wykonywania kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="dabfe-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="dabfe-180">Począwszy od .NET Framework w wersji 2,0, ta funkcja nie ma żadnego wpływu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="dabfe-181">Nie jest to wymagane i można je usunąć z kodu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="dabfe-182">CoUninitializeCor — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-182">CoUninitializeCor Function</span></span>](couninitializecor-function.md)  
 <span data-ttu-id="dabfe-183">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="dabfe-183">Obsolete.</span></span> <span data-ttu-id="dabfe-184">Nie można zwolnić środowiska CLR z procesu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="dabfe-185">CoUninitializeEE — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-185">CoUninitializeEE Function</span></span>](couninitializeee-function.md)  
 <span data-ttu-id="dabfe-186">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="dabfe-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="dabfe-187">CreateDebuggingInterfaceFromVersion — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-187">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="dabfe-188">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-188">Deprecated.</span></span> <span data-ttu-id="dabfe-189">Tworzy obiekt [ICorDebug](../debugging/icordebug-interface.md) na podstawie informacji o określonej wersji.</span><span class="sxs-lookup"><span data-stu-id="dabfe-189">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="dabfe-190">CreateICeeFileGen — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-190">CreateICeeFileGen Function</span></span>](createiceefilegen-function.md)  
 <span data-ttu-id="dabfe-191">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-191">Deprecated.</span></span> <span data-ttu-id="dabfe-192">Tworzy obiekt [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="dabfe-192">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="dabfe-193">DestroyICeeFileGen — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-193">DestroyICeeFileGen Function</span></span>](destroyiceefilegen-function.md)  
 <span data-ttu-id="dabfe-194">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-194">Deprecated.</span></span> <span data-ttu-id="dabfe-195">Niszczy obiekt [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="dabfe-195">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="dabfe-196">FExecuteInAppDomainCallback — Wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="dabfe-196">FExecuteInAppDomainCallback Function Pointer</span></span>](fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="dabfe-197">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-197">Deprecated.</span></span> <span data-ttu-id="dabfe-198">Wskazuje funkcję, którą środowisko CLR wywołuje do wykonywania kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="dabfe-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="dabfe-199">FLockClrVersionCallback — Wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="dabfe-199">FLockClrVersionCallback Function Pointer</span></span>](flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="dabfe-200">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-200">Deprecated.</span></span> <span data-ttu-id="dabfe-201">Wskazuje funkcję, którą wywołuje środowisko CLR w celu powiadomienia hosta, że inicjalizacja została uruchomiona lub została ukończona.</span><span class="sxs-lookup"><span data-stu-id="dabfe-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="dabfe-202">GetCLRIdentityManager — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-202">GetCLRIdentityManager Function</span></span>](getclridentitymanager-function.md)  
 <span data-ttu-id="dabfe-203">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-203">Deprecated.</span></span> <span data-ttu-id="dabfe-204">Pobiera wskaźnik do interfejsu, który umożliwia CLR Zarządzanie tożsamościami.</span><span class="sxs-lookup"><span data-stu-id="dabfe-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="dabfe-205">LoadLibraryShim — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-205">LoadLibraryShim Function</span></span>](loadlibraryshim-function.md)  
 <span data-ttu-id="dabfe-206">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-206">Deprecated.</span></span> <span data-ttu-id="dabfe-207">Ładuje określoną wersję biblioteki DLL .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dabfe-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="dabfe-208">LoadStringRC — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-208">LoadStringRC Function</span></span>](loadstringrc-function.md)  
 <span data-ttu-id="dabfe-209">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-209">Deprecated.</span></span> <span data-ttu-id="dabfe-210">Tłumaczy wartość HRESULT na komunikat o błędzie przy użyciu domyślnej kultury bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="dabfe-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="dabfe-211">LoadStringRCEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-211">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)  
 <span data-ttu-id="dabfe-212">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-212">Deprecated.</span></span> <span data-ttu-id="dabfe-213">Tłumaczy wartość HRESULT na odpowiedni komunikat o błędzie dla określonej kultury.</span><span class="sxs-lookup"><span data-stu-id="dabfe-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="dabfe-214">LPOVERLAPPED_COMPLETION_ROUTINE — Wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="dabfe-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="dabfe-215">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-215">Deprecated.</span></span> <span data-ttu-id="dabfe-216">Wskazuje funkcję, która powiadamia hosta, gdy nakładają się (czyli asynchroniczne) operacje wejścia/wyjścia do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="dabfe-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="dabfe-217">LPTHREAD_START_ROUTINE — Wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="dabfe-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="dabfe-218">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-218">Deprecated.</span></span> <span data-ttu-id="dabfe-219">Wskazuje funkcję, która powiadamia hosta o rozpoczęciu wykonywania wątku.</span><span class="sxs-lookup"><span data-stu-id="dabfe-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="dabfe-220">RunDll32ShimW — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-220">RunDll32ShimW Function</span></span>](rundll32shimw-function.md)  
 <span data-ttu-id="dabfe-221">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-221">Deprecated.</span></span> <span data-ttu-id="dabfe-222">Wykonuje określone polecenie.</span><span class="sxs-lookup"><span data-stu-id="dabfe-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="dabfe-223">WAITORTIMERCALLBACK — Wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="dabfe-223">WAITORTIMERCALLBACK Function Pointer</span></span>](waitortimercallback-function-pointer.md)  
 <span data-ttu-id="dabfe-224">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="dabfe-224">Deprecated.</span></span> <span data-ttu-id="dabfe-225">Wskazuje funkcję, która powiadamia hosta o zasygnalizowaniu lub przekroczeniu limitu czasu dojścia oczekiwania.</span><span class="sxs-lookup"><span data-stu-id="dabfe-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="dabfe-226">Funkcje infrastruktury</span><span class="sxs-lookup"><span data-stu-id="dabfe-226">Infrastructure functions</span></span>  

 <span data-ttu-id="dabfe-227">Funkcje w tej sekcji służą wyłącznie do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dabfe-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="dabfe-228">_CorDllMain — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-228">_CorDllMain Function</span></span>](cordllmain-function.md)  
 <span data-ttu-id="dabfe-229">Inicjuje środowisko CLR, lokalizuje zarządzany punkt wejścia w nagłówku CLR zestawu DLL i rozpoczyna wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="dabfe-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="dabfe-230">_CorExeMain — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-230">_CorExeMain Function</span></span>](corexemain-function.md)  
 <span data-ttu-id="dabfe-231">Inicjuje środowisko CLR, lokalizuje zarządzany punkt wejścia w nagłówku CLR zestawu wykonywalnego i rozpoczyna wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="dabfe-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="dabfe-232">_CorExeMain2 — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-232">_CorExeMain2 Function</span></span>](corexemain2-function.md)  
 <span data-ttu-id="dabfe-233">Wykonuje punkt wejścia w określonym kodzie mapowanym w pamięci.</span><span class="sxs-lookup"><span data-stu-id="dabfe-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="dabfe-234">Ta funkcja jest wywoływana przez program ładujący systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="dabfe-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="dabfe-235">_CorImageUnloading — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-235">_CorImageUnloading Function</span></span>](corimageunloading-function.md)  
 <span data-ttu-id="dabfe-236">Powiadamia moduł ładujący, gdy obrazy modułu zarządzanego są zwolnione.</span><span class="sxs-lookup"><span data-stu-id="dabfe-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="dabfe-237">_CorValidateImage — Funkcja</span><span class="sxs-lookup"><span data-stu-id="dabfe-237">_CorValidateImage Function</span></span>](corvalidateimage-function.md)  
 <span data-ttu-id="dabfe-238">Sprawdza poprawność obrazów modułu zarządzanego i powiadamia program ładujący system operacyjny po ich załadowaniu.</span><span class="sxs-lookup"><span data-stu-id="dabfe-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dabfe-239">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dabfe-239">See also</span></span>

- [<span data-ttu-id="dabfe-240">.NET Framework 4 — statyczne funkcje globalne hostingu</span><span class="sxs-lookup"><span data-stu-id="dabfe-240">.NET Framework 4 Hosting Global Static Functions</span></span>](net-framework-4-hosting-global-static-functions.md)
