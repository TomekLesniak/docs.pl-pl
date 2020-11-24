---
title: Debugowanie — Interfejsy
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: a3dd81ceaab2ba467d4c8ca091c1c2219040a273
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676299"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="a605f-102">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="a605f-102">Debugging Interfaces</span></span>

<span data-ttu-id="a605f-103">W tej sekcji opisano niezarządzane interfejsy obsługujące debugowanie programu wykonywanego w środowisku uruchomieniowym języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="a605f-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a605f-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="a605f-104">In This Section</span></span>  

 <span data-ttu-id="a605f-105">[ICLRDataEnumMemoryRegions, interfejs](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="a605f-106">Zapewnia metodę pozwalającą wyliczyć obszary pamięci, które są określone przez obiekty wywołujące.</span><span class="sxs-lookup"><span data-stu-id="a605f-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="a605f-107">[ICLRDataEnumMemoryRegionsCallback, interfejs](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)</span></span>\
 <span data-ttu-id="a605f-108">Udostępnia metodę wywołania zwrotnego dla programu w `EnumMemoryRegions` celu zgłaszania do debugera, wynik próby wyliczenia określonego regionu pamięci.</span><span class="sxs-lookup"><span data-stu-id="a605f-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="a605f-109">[ICLRDataTarget, interfejs](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="a605f-110">Zapewnia metody interakcji z obiektem docelowym procesu CLR.</span><span class="sxs-lookup"><span data-stu-id="a605f-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="a605f-111">[ICLRDataTarget2, interfejs](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="a605f-112">Podklasa `ICLRDataTarget` , która jest używana przez warstwę usług dostępu do danych do manipulowania regionami pamięci wirtualnej w procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="a605f-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="a605f-113">[ICLRDataTarget3, interfejs](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="a605f-114">Podklasa elementu [ICLRDataTarget2](iclrdatatarget2-interface.md) , która zapewnia dostęp do informacji o wyjątku.</span><span class="sxs-lookup"><span data-stu-id="a605f-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="a605f-115">[ICLRDebugging, interfejs](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-115">[ICLRDebugging Interface](iclrdebugging-interface.md)</span></span>\
 <span data-ttu-id="a605f-116">Zapewnia metody obsługujące ładowanie i wyładowanie modułów do debugowania.</span><span class="sxs-lookup"><span data-stu-id="a605f-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="a605f-117">[ICLRDebuggingLibraryProvider, interfejs](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)</span></span>\
 <span data-ttu-id="a605f-118">Obejmuje metodę [metody ProvideLibrary —](iclrdebugginglibraryprovider-providelibrary-method.md) , która pobiera interfejs wywołania zwrotnego dostawcy biblioteki, który umożliwia zlokalizowanie i załadowanie bibliotek debugowania specyficznych dla wersji środowiska uruchomieniowego języka wspólnego na żądanie.</span><span class="sxs-lookup"><span data-stu-id="a605f-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="a605f-119">[ICLRMetadataLocator, interfejs](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="a605f-120">Interfejs używany przez warstwę usług dostępu do danych do lokalizowania metadane zestawów w procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="a605f-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="a605f-121">[ICorDebug, interfejs](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="a605f-122">Dostarcza metody, które umożliwiają programistom debugowanie aplikacji w środowisku CLR.</span><span class="sxs-lookup"><span data-stu-id="a605f-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="a605f-123">[ICorDebugAppDomain, interfejs](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="a605f-124">Dostarcza metody do debugowania domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a605f-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="a605f-125">[ICorDebugAppDomain2, interfejs](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)</span></span>\
 <span data-ttu-id="a605f-126">Dostarcza metody do pracy z tablicami, wskaźnikami, wskaźnikami funkcji i typami ByRef.</span><span class="sxs-lookup"><span data-stu-id="a605f-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="a605f-127">Ten interfejs jest rozszerzeniem `ICorDebugAppDomain` interfejsu.</span><span class="sxs-lookup"><span data-stu-id="a605f-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="a605f-128">[ICorDebugAppDomain3, interfejs](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)</span></span>\
 <span data-ttu-id="a605f-129">Zapewnia metody do pracy z typami środowisko wykonawcze systemu Windows w domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a605f-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="a605f-130">Ten interfejs jest rozszerzeniem `ICorDebugAppDomain` `ICorDebugAppDomain2` interfejsów i.</span><span class="sxs-lookup"><span data-stu-id="a605f-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="a605f-131">[ICorDebugAppDomain4, interfejs](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)</span></span>\
 <span data-ttu-id="a605f-132">Logicznie rozszerza interfejs [ICorDebugAppDomain](icordebugappdomain-interface.md) w celu uzyskania obiektu zarządzanego z przywywoływanej otoki com.</span><span class="sxs-lookup"><span data-stu-id="a605f-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="a605f-133">[ICorDebugAppDomainEnum, interfejs](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-134">Zapewnia metodę, która zwraca określoną liczbę wartości, `ICorDebugAppDomain` Zaczynając od następnej lokalizacji w wyliczeniu.</span><span class="sxs-lookup"><span data-stu-id="a605f-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="a605f-135">[ICorDebugArrayValue, interfejs](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-136">Podklasa `ICorDebugHeapValue` reprezentująca tablicę jednowymiarową lub wielowymiarową.</span><span class="sxs-lookup"><span data-stu-id="a605f-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="a605f-137">[ICorDebugAssembly, interfejs](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="a605f-138">Reprezentuje zestaw.</span><span class="sxs-lookup"><span data-stu-id="a605f-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="a605f-139">[ICorDebugAssembly2, interfejs](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)</span></span>\
 <span data-ttu-id="a605f-140">Reprezentuje zestaw.</span><span class="sxs-lookup"><span data-stu-id="a605f-140">Represents an assembly.</span></span> <span data-ttu-id="a605f-141">Ten interfejs jest rozszerzeniem `ICorDebugAssembly` interfejsu.</span><span class="sxs-lookup"><span data-stu-id="a605f-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="a605f-142">[ICorDebugAssembly3, interfejs](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)</span></span>\
 <span data-ttu-id="a605f-143">Logicznie rozszerza interfejs [ICorDebugAssembly](icordebugassembly-interface.md) w celu zapewnienia obsługi zestawów kontenerów i zawartych w nich zestawów.</span><span class="sxs-lookup"><span data-stu-id="a605f-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="a605f-144">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-145">[ICorDebugAssemblyEnum, interfejs](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-146">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugAssembly` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="a605f-147">[ICorDebugBlockingObjectEnum, interfejs](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-148">Dostarcza moduł wyliczający listę struktur [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="a605f-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="a605f-149">[ICorDebugBoxValue, interfejs](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-150">Podklasa `ICorDebugHeapValue` reprezentująca obiekt klasy wartości w ramce.</span><span class="sxs-lookup"><span data-stu-id="a605f-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="a605f-151">[ICorDebugBreakpoint, interfejs](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="a605f-152">Reprezentuje punkt przerwania w funkcji lub punkt obserwacji wartości.</span><span class="sxs-lookup"><span data-stu-id="a605f-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="a605f-153">[ICorDebugBreakpointEnum, interfejs](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-154">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugBreakpoint` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="a605f-155">[ICorDebugChain, interfejs](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-155">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="a605f-156">Reprezentuje segment stosu wywołań fizycznych lub logicznych.</span><span class="sxs-lookup"><span data-stu-id="a605f-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="a605f-157">[ICorDebugChainEnum, interfejs](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-158">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugChain` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="a605f-159">[ICorDebugClass, interfejs](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-159">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="a605f-160">Reprezentuje typ, który może być podstawowy lub złożony (to jest zdefiniowany przez użytkownika).</span><span class="sxs-lookup"><span data-stu-id="a605f-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="a605f-161">Jeśli typ jest ogólny, `ICorDebugClass` reprezentuje typ ogólny bez wystąpień.</span><span class="sxs-lookup"><span data-stu-id="a605f-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="a605f-162">[ICorDebugClass2, interfejs](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)</span></span>\
 <span data-ttu-id="a605f-163">Reprezentuje klasę generyczną lub klasę z parametrem metody typu <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="a605f-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="a605f-164">Ten interfejs rozszerza `ICorDebugClass` .</span><span class="sxs-lookup"><span data-stu-id="a605f-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="a605f-165">[ICorDebugCode, interfejs](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="a605f-166">Reprezentuje segment kodu języka pośredniego firmy Microsoft (MSIL) lub kodu natywnego.</span><span class="sxs-lookup"><span data-stu-id="a605f-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="a605f-167">[ICorDebugCode2, interfejs](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)</span></span>\
 <span data-ttu-id="a605f-168">Dostarcza metody, które zwiększają możliwości programu `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="a605f-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="a605f-169">[ICorDebugCode3, interfejs](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)</span></span>\
 <span data-ttu-id="a605f-170">Zapewnia metodę, która rozszerza [ICorDebugCode](icordebugcode-interface1.md) i [ICorDebugCode2](icordebugcode2-interface.md) , aby zapewnić informacje o zarządzanej wartości zwracanej.</span><span class="sxs-lookup"><span data-stu-id="a605f-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="a605f-171">[ICorDebugCode4, interfejs](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)</span></span>\
 <span data-ttu-id="a605f-172">Zapewnia metodę, która umożliwia debugerowi Wyliczenie zmiennych lokalnych i argumentów w funkcji.</span><span class="sxs-lookup"><span data-stu-id="a605f-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="a605f-173">[ICorDebugCodeEnum, interfejs](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-174">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugCode` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="a605f-175">[ICorDebugComObjectValue, interfejs](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-176">Dostarcza metody pobierania obiektów interfejsu w pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="a605f-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="a605f-177">[ICorDebugContext —, interfejs](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-177">[ICorDebugContext Interface](icordebugcontext-interface.md)</span></span>\
 <span data-ttu-id="a605f-178">Reprezentuje obiekt kontekstu.</span><span class="sxs-lookup"><span data-stu-id="a605f-178">Represents a context object.</span></span> <span data-ttu-id="a605f-179">Ten Interfejs nie został jeszcze implementowany.</span><span class="sxs-lookup"><span data-stu-id="a605f-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="a605f-180">[ICorDebugController, interfejs](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-180">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="a605f-181">Reprezentuje zakres, albo <xref:System.Diagnostics.Process> lub <xref:System.AppDomain> , w którym można kontrolować kontekst wykonywania kodu.</span><span class="sxs-lookup"><span data-stu-id="a605f-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="a605f-182">[ICorDebugDataTarget, interfejs](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)</span></span>\
 <span data-ttu-id="a605f-183">Dostarcza interfejs wywołania zwrotnego, który zapewnia dostęp do konkretnego procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="a605f-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="a605f-184">[Metoda ICorDebugDataTarget2, interfejs](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="a605f-185">Logicznie rozszerza interfejs [ICorDebugDataTarget](icordebugdatatarget-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a605f-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="a605f-186">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-187">[ICorDebugDataTarget3, interfejs](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="a605f-188">Logicznie rozszerza interfejs [ICorDebugDataTarget](icordebugdatatarget-interface.md) w celu dostarczenia informacji o załadowanych modułach.</span><span class="sxs-lookup"><span data-stu-id="a605f-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="a605f-189">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-190">[ICorDebugDebugEvent, interfejs](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)</span></span>\
 <span data-ttu-id="a605f-191">Definiuje interfejs podstawowy, z którego `ICorDebug` pochodzą wszystkie zdarzenia debugowania.</span><span class="sxs-lookup"><span data-stu-id="a605f-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="a605f-192">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-193">[ICorDebugEditAndContinueErrorInfo, interfejs](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)</span></span>\
 <span data-ttu-id="a605f-194">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="a605f-194">Obsolete.</span></span> <span data-ttu-id="a605f-195">Nie używaj tego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="a605f-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="a605f-196">[ICorDebugEditAndContinueSnapshot, interfejs](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)</span></span>\
 <span data-ttu-id="a605f-197">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="a605f-197">Obsolete.</span></span> <span data-ttu-id="a605f-198">Nie używaj tego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="a605f-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="a605f-199">[ICorDebugEnum, interfejs](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="a605f-200">Służy jako abstrakcyjny interfejs podstawowy do debugowania modułów wyliczających.</span><span class="sxs-lookup"><span data-stu-id="a605f-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="a605f-201">[ICorDebugErrorInfoEnum, interfejs](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-202">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="a605f-202">Obsolete.</span></span> <span data-ttu-id="a605f-203">Nie używaj tego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="a605f-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="a605f-204">[ICorDebugEval, interfejs](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-204">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="a605f-205">Dostarcza metody umożliwiające debugerowi wykonywanie kodu w kontekście debugowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="a605f-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="a605f-206">[ICorDebugEval2, interfejs](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)</span></span>\
 <span data-ttu-id="a605f-207">Rozszerza `ICorDebugEval` , aby zapewnić obsługę typów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="a605f-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="a605f-208">[ICorDebugExceptionDebugEvent, interfejs](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)</span></span>\
 <span data-ttu-id="a605f-209">Rozszerza interfejs [ICorDebugDebugEvent](icordebugdebugevent-interface.md) w celu obsługi zdarzeń wyjątków.</span><span class="sxs-lookup"><span data-stu-id="a605f-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="a605f-210">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-211">[ICorDebugExceptionObjectCallStackEnum, interfejs](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-212">Dostarcza moduł wyliczający informacje stosu wywołań, który jest wbudowany w obiekt wyjątku.</span><span class="sxs-lookup"><span data-stu-id="a605f-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="a605f-213">[ICorDebugExceptionObjectValue, interfejs](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-214">Rozszerza interfejs [ICorDebugObjectValue](icordebugobjectvalue-interface.md) w celu udostępnienia informacji o śledzeniu stosu z obiektu wyjątku zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="a605f-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="a605f-215">[ICorDebugFrame, interfejs](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="a605f-216">Reprezentuje ramkę na bieżącym stosie.</span><span class="sxs-lookup"><span data-stu-id="a605f-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="a605f-217">[ICorDebugFrameEnum, interfejs](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-218">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugFrame` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="a605f-219">[ICorDebugFunction, interfejs](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="a605f-220">Reprezentuje zarządzaną funkcję lub metodę.</span><span class="sxs-lookup"><span data-stu-id="a605f-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="a605f-221">[ICorDebugFunction2, interfejs](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="a605f-222">Rozszerzenie logicznie rozszerza `ICorDebugFunction` , aby zapewnić obsługę tylko mój kod debugowania krok po kroku.</span><span class="sxs-lookup"><span data-stu-id="a605f-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="a605f-223">[ICorDebugFunction3, interfejs](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)</span></span>\
 <span data-ttu-id="a605f-224">Logicznie rozszerza interfejs [ICorDebugFunction](icordebugfunction-interface1.md) w celu zapewnienia dostępu do kodu z żądania ReJIT.</span><span class="sxs-lookup"><span data-stu-id="a605f-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="a605f-225">[ICorDebugFunctionBreakpoint, interfejs](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="a605f-226">Rozszerza `ICorDebugBreakpoint` do obsługi punktów przerwania w funkcjach.</span><span class="sxs-lookup"><span data-stu-id="a605f-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="a605f-227">[ICorDebugGCReferenceEnum, interfejs](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-228">Dostarcza moduł wyliczający dla obiektów, które zostaną usunięte jako elementy bezużyteczne.</span><span class="sxs-lookup"><span data-stu-id="a605f-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="a605f-229">[ICorDebugGenericValue, interfejs](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-230">Podklasa `ICorDebugValue` , która ma zastosowanie do wszystkich wartości.</span><span class="sxs-lookup"><span data-stu-id="a605f-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="a605f-231">Ten interfejs zapewnia metody Get i Set dla wartości.</span><span class="sxs-lookup"><span data-stu-id="a605f-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="a605f-232">[ICorDebugGuidToTypeEnum, interfejs](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-233">Dostarcza moduł wyliczający dla obiektu, który mapuje identyfikatory GUID i odpowiadające im `ICorDebugType` obiekty.</span><span class="sxs-lookup"><span data-stu-id="a605f-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="a605f-234">[ICorDebugHandleValue, interfejs](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-235">Podklasa `ICorDebugReferenceValue` reprezentująca wartość odniesienia, do której debuger utworzył dojście do wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="a605f-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="a605f-236">[ICorDebugHeapEnum, interfejs](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-237">Dostarcza moduł wyliczający dla obiektów na zarządzanej stercie.</span><span class="sxs-lookup"><span data-stu-id="a605f-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="a605f-238">[ICorDebugHeapSegmentEnum, interfejs](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-239">Zawiera moduł wyliczający dla obszarów pamięci zarządzanej sterty.</span><span class="sxs-lookup"><span data-stu-id="a605f-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="a605f-240">[ICorDebugHeapValue, interfejs](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-241">Podklasa `ICorDebugValue` reprezentująca obiekt, który został zebrany przez moduł wyrzucania elementów bezużytecznych CLR.</span><span class="sxs-lookup"><span data-stu-id="a605f-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="a605f-242">[ICorDebugHeapValue2, interfejs](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)</span></span>\
 <span data-ttu-id="a605f-243">Rozszerzenie `ICorDebugHeapValue` , które zapewnia obsługę uchwytów środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="a605f-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="a605f-244">[ICorDebugHeapValue3, interfejs](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)</span></span>\
 <span data-ttu-id="a605f-245">Udostępnia właściwości blokady monitora obiektów.</span><span class="sxs-lookup"><span data-stu-id="a605f-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="a605f-246">[ICorDebugILCode, interfejs](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)</span></span>\
 <span data-ttu-id="a605f-247">Reprezentuje segment kodu języka pośredniego (IL).</span><span class="sxs-lookup"><span data-stu-id="a605f-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="a605f-248">[ICorDebugILCode2, interfejs](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)</span></span>\
 <span data-ttu-id="a605f-249">Logicznie rozszerza interfejs [ICorDebugILCode](icordebugilcode-interface.md) w celu zapewnienia metod, które zwracają token dla sygnatury zmiennej lokalnej funkcji, i mapuje przesunięcia języka pośredniego (IL) narzędzia profilera do oryginalnej metody do przesunięcia Il.</span><span class="sxs-lookup"><span data-stu-id="a605f-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="a605f-250">[ICorDebugILFrame, interfejs](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="a605f-251">Reprezentuje ramkę stosu kodu MSIL.</span><span class="sxs-lookup"><span data-stu-id="a605f-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="a605f-252">[ICorDebugILFrame2, interfejs](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)</span></span>\
 <span data-ttu-id="a605f-253">Logiczne rozszerzenie `ICorDebugILFrame` .</span><span class="sxs-lookup"><span data-stu-id="a605f-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="a605f-254">[ICorDebugILFrame3, interfejs](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)</span></span>\
 <span data-ttu-id="a605f-255">Dostarcza metodę, która hermetyzuje wartość zwracaną przez funkcję.</span><span class="sxs-lookup"><span data-stu-id="a605f-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="a605f-256">[Metoda ICorDebugILFrame4, interfejs](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)</span></span>\
 <span data-ttu-id="a605f-257">Zapewnia metody umożliwiające dostęp do zmiennych lokalnych i kodu w ramce stosu kodu języka pośredniego (IL).</span><span class="sxs-lookup"><span data-stu-id="a605f-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="a605f-258">Parametr określa, czy debuger ma dostęp do zmiennych i kodu dodanych w Instrumentacji ReJIT profilera.</span><span class="sxs-lookup"><span data-stu-id="a605f-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="a605f-259">[ICorDebugInstanceFieldSymbol, interfejs](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="a605f-260">Przedstawia informacje o symbolu debugowania dla pola wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="a605f-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="a605f-261">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-262">[ICorDebugInternalFrame, interfejs](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)</span></span>\
 <span data-ttu-id="a605f-263">Identyfikuje typy ramek dla debugera.</span><span class="sxs-lookup"><span data-stu-id="a605f-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="a605f-264">[ICorDebugInternalFrame2, interfejs](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)</span></span>\
 <span data-ttu-id="a605f-265">Zawiera informacje o ramkach wewnętrznych, łącznie z adresem stosu i pozycją w odniesieniu do obiektów [ICorDebugFrame](icordebugframe-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a605f-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="a605f-266">[ICorDebugLoadedModule, interfejs](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)</span></span>\
 <span data-ttu-id="a605f-267">Zawiera informacje o załadowanym module.</span><span class="sxs-lookup"><span data-stu-id="a605f-267">Provides information about a loaded module.</span></span> <span data-ttu-id="a605f-268">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-269">[ICorDebugManagedCallback, interfejs](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="a605f-270">Dostarcza metody do przetwarzania wywołań zwrotnych debugera.</span><span class="sxs-lookup"><span data-stu-id="a605f-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="a605f-271">[ICorDebugManagedCallback2, interfejs](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)</span></span>\
 <span data-ttu-id="a605f-272">Dostarcza metody umożliwiające obsługę wyjątków debugera i obsługujące asystentów zarządzanego debugowania (MDA).</span><span class="sxs-lookup"><span data-stu-id="a605f-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="a605f-273">`ICorDebugManagedCallback2` jest logicznym rozszerzeniem `ICorDebugManagedCallback` .</span><span class="sxs-lookup"><span data-stu-id="a605f-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="a605f-274">[ICorDebugManagedCallback3, interfejs](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)</span></span>\
 <span data-ttu-id="a605f-275">Dostarcza metodę wywołania zwrotnego, która wskazuje, że zgłoszono powiadomienie włączenia niestandardowego debugera.</span><span class="sxs-lookup"><span data-stu-id="a605f-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="a605f-276">[ICorDebugMDA, interfejs](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-276">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="a605f-277">Reprezentuje komunikat asystenta zarządzanego debugowania (MDA).</span><span class="sxs-lookup"><span data-stu-id="a605f-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="a605f-278">[ICorDebugMemoryBuffer, interfejs](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)</span></span>\
 <span data-ttu-id="a605f-279">Reprezentuje bufor w pamięci.</span><span class="sxs-lookup"><span data-stu-id="a605f-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="a605f-280">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-281">[ICorDebugMergedAssemblyRecord, interfejs](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)</span></span>\
 <span data-ttu-id="a605f-282">Zawiera informacje o scalonym zestawie.</span><span class="sxs-lookup"><span data-stu-id="a605f-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="a605f-283">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-284">[ICorDebugMetaDataLocator, interfejs](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="a605f-285">Dostarcza informacje o metadanych do debugera.</span><span class="sxs-lookup"><span data-stu-id="a605f-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="a605f-286">[ICorDebugModule, interfejs](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-286">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="a605f-287">Reprezentuje moduł CLR, który jest albo plikiem wykonywalnym lub biblioteką DLL.</span><span class="sxs-lookup"><span data-stu-id="a605f-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="a605f-288">[ICorDebugModule2, interfejs](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)</span></span>\
 <span data-ttu-id="a605f-289">Służy jako rozszerzenie logiczne do `ICorDebugModule` .</span><span class="sxs-lookup"><span data-stu-id="a605f-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="a605f-290">[ICorDebugModule3, interfejs](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)</span></span>\
 <span data-ttu-id="a605f-291">Tworzy czytnik symbolu dla modułu dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="a605f-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="a605f-292">[ICorDebugModuleBreakpoint, interfejs](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="a605f-293">Rozszerza `ICorDebugBreakpoint` , aby zapewnić dostęp do określonych modułów.</span><span class="sxs-lookup"><span data-stu-id="a605f-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="a605f-294">[ICorDebugModuleDebugEvent, interfejs](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)</span></span>\
 <span data-ttu-id="a605f-295">Rozszerza interfejs [ICorDebugDebugEvent](icordebugdebugevent-interface.md) w celu obsługi zdarzeń na poziomie modułu.</span><span class="sxs-lookup"><span data-stu-id="a605f-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="a605f-296">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-297">[ICorDebugModuleEnum, interfejs](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-298">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugModule` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="a605f-299">[ICorDebugMutableDataTarget, interfejs](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)</span></span>\
 <span data-ttu-id="a605f-300">Rozszerza interfejs [ICorDebugDataTarget](icordebugdatatarget-interface.md) w celu obsługi modyfikowalnych obiektów docelowych danych.</span><span class="sxs-lookup"><span data-stu-id="a605f-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="a605f-301">[ICorDebugNativeFrame, interfejs](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="a605f-302">Wyspecjalizowana implementacja `ICorDebugFrame` używana dla ramek natywnych.</span><span class="sxs-lookup"><span data-stu-id="a605f-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="a605f-303">[ICorDebugNativeFrame2, interfejs](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)</span></span>\
 <span data-ttu-id="a605f-304">Dostarcza metody testowania relacji podrzędnych i nadrzędnych ramek.</span><span class="sxs-lookup"><span data-stu-id="a605f-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="a605f-305">[ICorDebugObjectEnum, interfejs](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-306">Implementuje `ICorDebugEnum` metody i wylicza tablice obiektów według ich względnych adresów wirtualnych (RVA).</span><span class="sxs-lookup"><span data-stu-id="a605f-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="a605f-307">[ICorDebugObjectValue, interfejs](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-308">Podklasa `ICorDebugValue` reprezentująca wartość, która zawiera obiekt.</span><span class="sxs-lookup"><span data-stu-id="a605f-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="a605f-309">[ICorDebugObjectValue2, interfejs](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)</span></span>\
 <span data-ttu-id="a605f-310">Rozszerza `ICorDebugObjectValue` do obsługi dziedziczenia i zastąpień.</span><span class="sxs-lookup"><span data-stu-id="a605f-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="a605f-311">[ICorDebugProcess, interfejs](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="a605f-312">Reprezentuje proces, który wykonuje kod zarządzany.</span><span class="sxs-lookup"><span data-stu-id="a605f-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="a605f-313">[ICorDebugProcess2, interfejs](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)</span></span>\
 <span data-ttu-id="a605f-314">Logiczne rozszerzenie `ICorDebugProcess` .</span><span class="sxs-lookup"><span data-stu-id="a605f-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="a605f-315">[ICorDebugProcess3, interfejs](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)</span></span>\
 <span data-ttu-id="a605f-316">Steruje niestandardowymi powiadomieniami debugera.</span><span class="sxs-lookup"><span data-stu-id="a605f-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="a605f-317">[ICorDebugProcess4, interfejs](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)</span></span>\
 <span data-ttu-id="a605f-318">Zapewnia obsługę kontroli wykonywania poza procesem.</span><span class="sxs-lookup"><span data-stu-id="a605f-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="a605f-319">[ICorDebugProcess5, interfejs](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)</span></span>\
 <span data-ttu-id="a605f-320">Rozszerza interfejs [ICorDebugProcess](icordebugprocess-interface.md) w celu obsługi dostępu do zarządzanej sterty, zapewnia informacje o wyrzucaniu elementów bezużytecznych obiektów zarządzanych i określa, czy debuger ładuje obrazy z lokalnej pamięci podręcznej obrazów natywnych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a605f-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="a605f-321">[Metoda ICorDebugProcess6, interfejs](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)</span></span>\
 <span data-ttu-id="a605f-322">Logicznie rozszerza interfejs [ICorDebugProcess](icordebugprocess-interface.md) w celu włączenia takich funkcji, jak dekodowanie zdarzeń debugowania zarządzanego, które są kodowane w natywnych zdarzeniach debugowania wyjątków i dzielenia modułu wirtualnego.</span><span class="sxs-lookup"><span data-stu-id="a605f-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="a605f-323">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-324">[ICorDebugProcess7, interfejs](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)</span></span>\
 <span data-ttu-id="a605f-325">Zapewnia metodę, która umożliwia skonfigurowanie debugera do obsługi aktualizacji metadanych w pamięci w procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="a605f-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="a605f-326">[ICorDebugProcess8, interfejs](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)</span></span>\
 <span data-ttu-id="a605f-327">Logicznie rozszerza interfejs [ICorDebugProcess](icordebugprocess-interface.md) w celu włączenia lub wyłączenia niektórych typów wywołań zwrotnych wyjątków [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a605f-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="a605f-328">[ICorDebugProcessEnum, interfejs](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-329">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugProcess` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="a605f-330">[ICorDebugReferenceValue, interfejs](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-331">Podklasa `ICorDebugValue` , która obsługuje typy odwołań.</span><span class="sxs-lookup"><span data-stu-id="a605f-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="a605f-332">[ICorDebugRegisterSet, interfejs](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="a605f-333">Reprezentuje zestaw rejestrów dostępnych na komputerze, który aktualnie wykonuje kod.</span><span class="sxs-lookup"><span data-stu-id="a605f-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="a605f-334">[ICorDebugRegisterSet2, interfejs](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)</span></span>\
 <span data-ttu-id="a605f-335">Rozszerza możliwości programu `ICorDebugRegisterSet` dla platform sprzętowych, które mają ponad 64 rejestrów.</span><span class="sxs-lookup"><span data-stu-id="a605f-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="a605f-336">[ICorDebugRemote, interfejs](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-336">[ICorDebugRemote Interface](icordebugremote-interface.md)</span></span>\
 <span data-ttu-id="a605f-337">Zapewnia zdalnemu procesowi docelowemu możliwość uruchamiania lub dołączenia zarządzanych debugerów.</span><span class="sxs-lookup"><span data-stu-id="a605f-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="a605f-338">[ICorDebugRemoteTarget, interfejs](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)</span></span>\
 <span data-ttu-id="a605f-339">Dostarcza metody, które umożliwiają debugowania aplikacji opartych na dodatku Silverlight w środowisku CLR.</span><span class="sxs-lookup"><span data-stu-id="a605f-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="a605f-340">[ICorDebugRuntimeUnwindableFrame, interfejs](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)</span></span>\
 <span data-ttu-id="a605f-341">Zapewnia obsługę niezarządzanych metod, które wymagają środowiska uruchomieniowego języka wspólnego (CLR), aby zwolnić ramkę.</span><span class="sxs-lookup"><span data-stu-id="a605f-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="a605f-342">[ICorDebugStackWalk, interfejs](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="a605f-343">Dostarcza metody pobierania zarządzanych metod, lub ramek, znajdujących się na stosie wątku.</span><span class="sxs-lookup"><span data-stu-id="a605f-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="a605f-344">[ICorDebugStaticFieldSymbol, interfejs](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="a605f-345">Przedstawia informacje o symbolu debugowania dla pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="a605f-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="a605f-346">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-347">[ICorDebugStepper, interfejs](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="a605f-348">Reprezentuje krok wykonaniu kodu, który jest realizowany przez debuger; służy jako identyfikator między wydaniem i zakończeniem polecenia i zapewnia sposób anulowania kroku.</span><span class="sxs-lookup"><span data-stu-id="a605f-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="a605f-349">[ICorDebugStepper2, interfejs](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)</span></span>\
 <span data-ttu-id="a605f-350">Zapewnia obsługę debugowania Tylko mój kod (JMC).</span><span class="sxs-lookup"><span data-stu-id="a605f-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="a605f-351">[ICorDebugStepperEnum, interfejs](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-352">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugStepper` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="a605f-353">[ICorDebugStringValue, interfejs](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-354">Podklasa `ICorDebugHeapValue` , która ma zastosowanie do wartości ciągu.</span><span class="sxs-lookup"><span data-stu-id="a605f-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="a605f-355">[ICorDebugSymbolProvider, interfejs](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)</span></span>\
 <span data-ttu-id="a605f-356">Dostarcza metody, których można użyć do pobrania informacji o symbolach debugowania.</span><span class="sxs-lookup"><span data-stu-id="a605f-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="a605f-357">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-358">[ICorDebugSymbolProvider2, interfejs](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)</span></span>\
 <span data-ttu-id="a605f-359">Logicznie rozszerza interfejs [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) w celu pobrania dodatkowych informacji o symbolach debugowania.</span><span class="sxs-lookup"><span data-stu-id="a605f-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="a605f-360">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-361">[ICorDebugThread, interfejs](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-361">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="a605f-362">Reprezentuje wątek w procesie.</span><span class="sxs-lookup"><span data-stu-id="a605f-362">Represents a thread in a process.</span></span> <span data-ttu-id="a605f-363">Okres istnienia `ICorDebugThread` wystąpienia jest taki sam jak okres istnienia wątku, który reprezentuje.</span><span class="sxs-lookup"><span data-stu-id="a605f-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="a605f-364">[ICorDebugThread2, interfejs](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)</span></span>\
 <span data-ttu-id="a605f-365">Służy jako rozszerzenie logiczne do `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="a605f-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="a605f-366">[ICorDebugThread3, interfejs](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)</span></span>\
 <span data-ttu-id="a605f-367">Udostępnia punkt wejścia do [ICorDebugStackWalk](icordebugstackwalk-interface.md) i odpowiednich interfejsów.</span><span class="sxs-lookup"><span data-stu-id="a605f-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="a605f-368">[ICorDebugThread4, interfejs](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)</span></span>\
 <span data-ttu-id="a605f-369">Dostarcza informacje o blokowaniu wątku.</span><span class="sxs-lookup"><span data-stu-id="a605f-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="a605f-370">[ICorDebugThreadEnum, interfejs](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)</span></span>\
 <span data-ttu-id="a605f-371">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugThread` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="a605f-372">[ICorDebugType, interfejs](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-372">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="a605f-373">Reprezentuje typ, który może być podstawowy lub złożony (to jest zdefiniowany przez użytkownika).</span><span class="sxs-lookup"><span data-stu-id="a605f-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="a605f-374">Jeśli typ jest ogólny, `ICorDebugType` reprezentuje typ ogólny wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="a605f-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="a605f-375">[ICorDebugType2, interfejs](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)</span></span>\
 <span data-ttu-id="a605f-376">Rozszerza interfejs [ICorDebugType](icordebugtype-interface.md) w celu pobrania identyfikatora typu podstawowego lub złożonego (zdefiniowanego przez użytkownika).</span><span class="sxs-lookup"><span data-stu-id="a605f-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="a605f-377">[ICorDebugTypeEnum, interfejs](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-378">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugType` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="a605f-379">[ICorDebugUnmanagedCallback, interfejs](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="a605f-380">Zapewnia powiadomienie macierzystych zdarzeń, które nie dotyczą bezpośrednio środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="a605f-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="a605f-381">[ICorDebugValue](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-381">[ICorDebugValue](icordebugvalue-interface.md)</span></span>\
 <span data-ttu-id="a605f-382">Reprezentuje wartość odczytu lub zapisu w procesie debugowania.</span><span class="sxs-lookup"><span data-stu-id="a605f-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="a605f-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span></span>\
 <span data-ttu-id="a605f-384">Rozszerza `ICorDebugValue` , aby zapewnić pomoc techniczną `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="a605f-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="a605f-385">[ICorDebugValue3, interfejs](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)</span></span>\
 <span data-ttu-id="a605f-386">Rozszerza interfejsy "ICorDebugValue" i "ICorDebugValue2", aby zapewnić obsługę tablic o rozmiarze większym niż 2 GB.</span><span class="sxs-lookup"><span data-stu-id="a605f-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="a605f-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="a605f-388">Rozszerza `ICorDebugBreakpoint` , aby zapewnić dostęp do określonych wartości.</span><span class="sxs-lookup"><span data-stu-id="a605f-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="a605f-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-390">Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugValue` tablice.</span><span class="sxs-lookup"><span data-stu-id="a605f-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="a605f-391">[ICorDebugVariableHome, interfejs](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)</span></span>\
 <span data-ttu-id="a605f-392">Reprezentuje zmienną lokalną lub argument funkcji.</span><span class="sxs-lookup"><span data-stu-id="a605f-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="a605f-393">[ICorDebugVariableHomeEnum, interfejs](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-394">Dostarcza moduł wyliczający do zmiennych lokalnych i argumentów w funkcji.</span><span class="sxs-lookup"><span data-stu-id="a605f-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="a605f-395">[ICorDebugVariableSymbol, interfejs](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)</span></span>\
 <span data-ttu-id="a605f-396">Pobiera informacje o symbolach debugowania dla zmiennej.</span><span class="sxs-lookup"><span data-stu-id="a605f-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="a605f-397">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-398">[ICorDebugVirtualUnwinder, interfejs](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)</span></span>\
 <span data-ttu-id="a605f-399">Zapewnia metody pomagające w rozwinięcia stosu.</span><span class="sxs-lookup"><span data-stu-id="a605f-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="a605f-400">**Dostępne tylko .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a605f-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="a605f-401">[ICorPublish, interfejs](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-401">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="a605f-402">Służy jako ogólny interfejs dla procesów publikowania.</span><span class="sxs-lookup"><span data-stu-id="a605f-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="a605f-403">[ICorPublishAppDomain, interfejs](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="a605f-404">Reprezentuje i dostarcza informacje dotyczące domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a605f-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="a605f-405">[ICorPublishAppDomainEnum, interfejs](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-406">Dostarcza metody, które przechodzą kolekcję `ICorPublishAppDomain` obiektów, które aktualnie istnieją w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="a605f-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="a605f-407">[ICorPublishEnum, interfejs](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-408">Służy jako abstrakcyjna podstawowa do publikowania modułów wyliczających.</span><span class="sxs-lookup"><span data-stu-id="a605f-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="a605f-409">[ICorPublishProcess, interfejs](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="a605f-410">Dostarcza metody, które mają dostęp do informacji dotyczących procesu.</span><span class="sxs-lookup"><span data-stu-id="a605f-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="a605f-411">[ICorPublishProcessEnum, interfejs](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)</span></span>\
 <span data-ttu-id="a605f-412">Dostarcza metody, które przechodzą przez kolekcję `ICorPublishProcess` obiektów.</span><span class="sxs-lookup"><span data-stu-id="a605f-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="a605f-413">[ISOSDacInterface, interfejs](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)</span></span>\
 <span data-ttu-id="a605f-414">Zapewnia metody pomocnika do uzyskiwania dostępu do danych `SOS` .</span><span class="sxs-lookup"><span data-stu-id="a605f-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="a605f-415">[IXCLRDataMethodDefinition, interfejs](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)</span></span>\
 <span data-ttu-id="a605f-416">Zapewnia metody wykonywania zapytań dotyczących informacji o definicji metody.</span><span class="sxs-lookup"><span data-stu-id="a605f-416">Provides methods for querying information about a method definition.</span></span>

 <span data-ttu-id="a605f-417">[IXCLRDataMethodInstance, interfejs](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)</span></span>\
 <span data-ttu-id="a605f-418">Zapewnia metody wykonywania zapytań dotyczących informacji o wystąpieniu metody.</span><span class="sxs-lookup"><span data-stu-id="a605f-418">Provides methods for querying information about a method instance.</span></span>

 <span data-ttu-id="a605f-419">[IXCLRDataModule, interfejs](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)</span></span>\
 <span data-ttu-id="a605f-420">Zapewnia metody wykonywania zapytania o informacje o załadowanym module.</span><span class="sxs-lookup"><span data-stu-id="a605f-420">Provides methods for querying information about a loaded module.</span></span>

 <span data-ttu-id="a605f-421">[IXCLRDataProcess, interfejs](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)</span></span>\
 <span data-ttu-id="a605f-422">Dostarcza metody do wykonywania zapytań dotyczących informacji o procesie.</span><span class="sxs-lookup"><span data-stu-id="a605f-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="a605f-423">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="a605f-423">Related Sections</span></span>  

 <span data-ttu-id="a605f-424">[Klasy coclass debugowania](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="a605f-425">[Debugowanie globalnych funkcji statycznych](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="a605f-426">[Wyliczenia debugowania](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-426">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="a605f-427">[Struktury debugowania](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="a605f-427">[Debugging Structures](debugging-structures.md)</span></span>\
