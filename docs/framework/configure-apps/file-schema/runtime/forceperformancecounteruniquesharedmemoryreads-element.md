---
title: <forcePerformanceCounterUniqueSharedMemoryReads> Element
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 719448ba3de2aca0621fc17b9fadbdd3b8588f2e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178245"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="a33d7-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span><span class="sxs-lookup"><span data-stu-id="a33d7-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>

<span data-ttu-id="a33d7-103">Określa, czy PerfCounter.dll używa ustawienia rejestru CategoryOptions w aplikacji .NET Framework w wersji 1,1, aby określić, czy dane liczników wydajności mają być ładowane z pamięci współdzielonej określonej dla kategorii, czy z pamięci globalnej.</span><span class="sxs-lookup"><span data-stu-id="a33d7-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a><span data-ttu-id="a33d7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a33d7-104">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a33d7-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a33d7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a33d7-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a33d7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a33d7-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a33d7-107">Attributes</span></span>  
  
|<span data-ttu-id="a33d7-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a33d7-108">Attribute</span></span>|<span data-ttu-id="a33d7-109">Opis</span><span class="sxs-lookup"><span data-stu-id="a33d7-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a33d7-110">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="a33d7-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="a33d7-111">Wskazuje, czy PerfCounter.dll używa ustawienia rejestru CategoryOptions, aby określić, czy załadować dane liczników wydajności z pamięci współdzielonej określonej dla kategorii lub pamięci globalnej.</span><span class="sxs-lookup"><span data-stu-id="a33d7-111">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a33d7-112">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="a33d7-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="a33d7-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="a33d7-113">Value</span></span>|<span data-ttu-id="a33d7-114">Opis</span><span class="sxs-lookup"><span data-stu-id="a33d7-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a33d7-115">PerfCounter.dll nie używa ustawienia rejestru CategoryOptions. jest to ustawienie domyślne.</span><span class="sxs-lookup"><span data-stu-id="a33d7-115">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="a33d7-116">PerfCounter.dll używa ustawienia rejestru CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="a33d7-116">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a33d7-117">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a33d7-117">Child Elements</span></span>  

 <span data-ttu-id="a33d7-118">Brak.</span><span class="sxs-lookup"><span data-stu-id="a33d7-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a33d7-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a33d7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a33d7-120">Element</span><span class="sxs-lookup"><span data-stu-id="a33d7-120">Element</span></span>|<span data-ttu-id="a33d7-121">Opis</span><span class="sxs-lookup"><span data-stu-id="a33d7-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a33d7-122">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a33d7-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a33d7-123">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="a33d7-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a33d7-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a33d7-124">Remarks</span></span>  

 <span data-ttu-id="a33d7-125">W wersjach .NET Framework przed .NET Framework 4, załadowana wersja PerfCounter.dll odnosi się do środowiska uruchomieniowego, które zostało załadowane w procesie.</span><span class="sxs-lookup"><span data-stu-id="a33d7-125">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="a33d7-126">Jeśli na komputerze zainstalowano zarówno .NET Framework w wersji 1,1, jak i .NET Framework 2,0, aplikacja .NET Framework 1,1 załaduje .NET Framework 1,1 wersja PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="a33d7-126">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="a33d7-127">Począwszy od .NET Framework 4 Najnowsza zainstalowana wersja PerfCounter.dll zostanie załadowana.</span><span class="sxs-lookup"><span data-stu-id="a33d7-127">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="a33d7-128">Oznacza to, że aplikacja .NET Framework 1,1 będzie ładować wersję PerfCounter.dll .NET Framework 4, jeśli na komputerze zainstalowano .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a33d7-128">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="a33d7-129">Począwszy od .NET Framework 4, podczas zużywania liczników wydajności, PerfCounter.dll sprawdza wpis rejestru CategoryOptions dla każdego dostawcy, aby określić, czy powinien on zostać odczytany z udostępnionej pamięci lub globalnej pamięci współdzielonej według kategorii.</span><span class="sxs-lookup"><span data-stu-id="a33d7-129">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="a33d7-130">PerfCounter.dll .NET Framework 1,1 nie odczytuje tego wpisu rejestru, ponieważ nie ma on informacji o pamięci współdzielonej określonej dla kategorii; zawsze odczytuje z globalnej pamięci współdzielonej.</span><span class="sxs-lookup"><span data-stu-id="a33d7-130">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="a33d7-131">W celu zapewnienia zgodności z poprzednimi wersjami PerfCounter.dll .NET Framework 4 nie sprawdza wpisu rejestru CategoryOptions podczas uruchamiania w aplikacji .NET Framework 1,1.</span><span class="sxs-lookup"><span data-stu-id="a33d7-131">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="a33d7-132">Po prostu używa globalnej pamięci współdzielonej, podobnie jak .NET Framework 1,1 PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="a33d7-132">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="a33d7-133">Można jednak wydać polecenie .NET Framework 4 PerfCounter.dll do sprawdzenia ustawienia rejestru przez włączenie `<forcePerformanceCounterUniqueSharedMemoryReads>` elementu.</span><span class="sxs-lookup"><span data-stu-id="a33d7-133">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a33d7-134">Włączenie `<forcePerformanceCounterUniqueSharedMemoryReads>` elementu nie gwarantuje, że zostanie użyta udostępniona pamięć określona w kategorii.</span><span class="sxs-lookup"><span data-stu-id="a33d7-134">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="a33d7-135">Ustawienie Enabled `true` tylko powoduje, że PerfCounter.dll odwołujące się do ustawienia rejestru CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="a33d7-135">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="a33d7-136">Ustawieniem domyślnym dla CategoryOptions jest użycie pamięci współużytkowanej określonej dla kategorii; można jednak zmienić CategoryOptions, aby wskazać, że powinna być używana globalna pamięć współdzielona.</span><span class="sxs-lookup"><span data-stu-id="a33d7-136">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="a33d7-137">Klucz rejestru, który zawiera ustawienie CategoryOptions, to HKEY_LOCAL_MACHINE \System\CurrentControlSet\Services \\<CategoryName \> \Performance.</span><span class="sxs-lookup"><span data-stu-id="a33d7-137">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="a33d7-138">Domyślnie CategoryOptions jest ustawiony na 3, który instruuje PerfCounter.dll, aby użyć udostępnionej pamięci specyficznej dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="a33d7-138">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="a33d7-139">Jeśli wartość CategoryOptions jest równa 0, PerfCounter.dll używa globalnej pamięci współdzielonej.</span><span class="sxs-lookup"><span data-stu-id="a33d7-139">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="a33d7-140">Dane wystąpienia będą ponownie używane tylko wtedy, gdy nazwa tworzonego wystąpienia jest identyczna z ponownie używanym wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="a33d7-140">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="a33d7-141">Wszystkie wersje będą mogły zapisywać w kategorii.</span><span class="sxs-lookup"><span data-stu-id="a33d7-141">All versions will be able to write to the category.</span></span> <span data-ttu-id="a33d7-142">Jeśli CategoryOptions jest ustawiona na 1, używana jest globalna pamięć współdzielona, ale dane wystąpienia mogą być ponownie używane, jeśli nazwa kategorii ma taką samą długość jak kategoria używana ponownie.</span><span class="sxs-lookup"><span data-stu-id="a33d7-142">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="a33d7-143">Ustawienia 0 i 1 mogą prowadzić do przecieków pamięci i wypełniania pamięci licznika wydajności.</span><span class="sxs-lookup"><span data-stu-id="a33d7-143">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a33d7-144">Przykład</span><span class="sxs-lookup"><span data-stu-id="a33d7-144">Example</span></span>  

 <span data-ttu-id="a33d7-145">Poniższy przykład pokazuje, jak określić, że PerfCounter.dll powinien odwoływać się do wpisu rejestru CategoryOptions, aby określić, czy powinien on używać pamięci współdzielonej specyficznej dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="a33d7-145">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a33d7-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a33d7-146">See also</span></span>

- [<span data-ttu-id="a33d7-147">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="a33d7-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a33d7-148">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="a33d7-148">Configuration File Schema</span></span>](../index.md)
