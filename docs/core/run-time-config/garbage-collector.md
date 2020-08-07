---
title: Ustawienia konfiguracji modułu wyrzucania elementów bezużytecznych
description: Informacje o ustawieniach czasu wykonywania w celu skonfigurowania sposobu, w jaki moduł zbierający elementy bezużyteczne zarządza pamięcią dla aplikacji platformy .NET Core.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 91d155b638c7e69b3d2c0216266a7c0c0410db4c
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915992"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="83a84-103">Opcje konfiguracji czasu wykonywania dla wyrzucania elementów bezużytecznych</span><span class="sxs-lookup"><span data-stu-id="83a84-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="83a84-104">Ta strona zawiera informacje na temat ustawień modułu zbierającego elementy bezużyteczne (GC), które można zmienić w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="83a84-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="83a84-105">Jeśli próbujesz osiągnąć szczytową wydajność uruchomionej aplikacji, rozważ użycie tych ustawień.</span><span class="sxs-lookup"><span data-stu-id="83a84-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="83a84-106">Jednak wartości domyślne zapewniają optymalną wydajność większości aplikacji w typowych sytuacjach.</span><span class="sxs-lookup"><span data-stu-id="83a84-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="83a84-107">Ustawienia są ułożone w grupach na tej stronie.</span><span class="sxs-lookup"><span data-stu-id="83a84-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="83a84-108">Ustawienia w ramach każdej grupy są często używane w połączeniu ze sobą, aby osiągnąć konkretny wynik.</span><span class="sxs-lookup"><span data-stu-id="83a84-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="83a84-109">Te ustawienia mogą być również dynamicznie zmieniane przez aplikację w trakcie działania, więc wszystkie ustawione ustawienia czasu wykonywania mogą zostać zastąpione.</span><span class="sxs-lookup"><span data-stu-id="83a84-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="83a84-110">Niektóre ustawienia, takie jak [poziom opóźnienia](../../standard/garbage-collection/latency.md), są zazwyczaj ustawiane tylko za pomocą interfejsu API w czasie projektowania.</span><span class="sxs-lookup"><span data-stu-id="83a84-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="83a84-111">Takie ustawienia zostały pominięte na tej stronie.</span><span class="sxs-lookup"><span data-stu-id="83a84-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="83a84-112">W przypadku wartości liczbowych Użyj notacji dziesiętnej dla ustawień w *runtimeconfig.jsw* notacji plik i szesnastkowy dla ustawień zmiennych środowiskowych.</span><span class="sxs-lookup"><span data-stu-id="83a84-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="83a84-113">W przypadku wartości szesnastkowych można je określić z prefiksem "0x" lub bez niego.</span><span class="sxs-lookup"><span data-stu-id="83a84-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="83a84-114">Typy wyrzucania elementów bezużytecznych</span><span class="sxs-lookup"><span data-stu-id="83a84-114">Flavors of garbage collection</span></span>

<span data-ttu-id="83a84-115">Dwa główne typy wyrzucania elementów bezużytecznych to stacja robocza i serwer GC.</span><span class="sxs-lookup"><span data-stu-id="83a84-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="83a84-116">Aby uzyskać więcej informacji o różnicach między tymi dwoma, zobacz [stacja robocza i odzyskiwanie pamięci serwera](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="83a84-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="83a84-117">Podelementy wyrzucania elementów bezużytecznych są tła i niewspółbieżne.</span><span class="sxs-lookup"><span data-stu-id="83a84-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="83a84-118">Użyj następujących ustawień, aby wybrać typy wyrzucania elementów bezużytecznych:</span><span class="sxs-lookup"><span data-stu-id="83a84-118">Use the following settings to select flavors of garbage collection:</span></span>

- [<span data-ttu-id="83a84-119">Stacja robocza a serwer GC</span><span class="sxs-lookup"><span data-stu-id="83a84-119">Workstation vs. server GC</span></span>](#workstation-vs-server)
- [<span data-ttu-id="83a84-120">Odzyskiwanie pamięci w tle</span><span class="sxs-lookup"><span data-stu-id="83a84-120">Background GC</span></span>](#background-gc)

### <a name="workstation-vs-server"></a><span data-ttu-id="83a84-121">Stacja robocza a serwer</span><span class="sxs-lookup"><span data-stu-id="83a84-121">Workstation vs. server</span></span>

- <span data-ttu-id="83a84-122">Określa, czy aplikacja używa wyrzucania elementów bezużytecznych stacji roboczej lub odzyskiwania pamięci serwera.</span><span class="sxs-lookup"><span data-stu-id="83a84-122">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="83a84-123">Domyślnie: wyrzucanie elementów bezużytecznych stacji roboczej.</span><span class="sxs-lookup"><span data-stu-id="83a84-123">Default: Workstation garbage collection.</span></span> <span data-ttu-id="83a84-124">Jest to równoznaczne z ustawieniem wartości `false` .</span><span class="sxs-lookup"><span data-stu-id="83a84-124">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="83a84-125">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-125">Setting name</span></span> | <span data-ttu-id="83a84-126">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-126">Values</span></span> | <span data-ttu-id="83a84-127">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-127">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-128">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-128">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="83a84-129">`false`-Stacja robocza</span><span class="sxs-lookup"><span data-stu-id="83a84-129">`false` - workstation</span></span><br/><span data-ttu-id="83a84-130">`true`— serwer</span><span class="sxs-lookup"><span data-stu-id="83a84-130">`true` - server</span></span> | <span data-ttu-id="83a84-131">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-131">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-132">**Właściwość programu MSBuild**</span><span class="sxs-lookup"><span data-stu-id="83a84-132">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="83a84-133">`false`-Stacja robocza</span><span class="sxs-lookup"><span data-stu-id="83a84-133">`false` - workstation</span></span><br/><span data-ttu-id="83a84-134">`true`— serwer</span><span class="sxs-lookup"><span data-stu-id="83a84-134">`true` - server</span></span> | <span data-ttu-id="83a84-135">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-135">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-136">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-136">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="83a84-137">`0`-Stacja robocza</span><span class="sxs-lookup"><span data-stu-id="83a84-137">`0` - workstation</span></span><br/><span data-ttu-id="83a84-138">`1`— serwer</span><span class="sxs-lookup"><span data-stu-id="83a84-138">`1` - server</span></span> | <span data-ttu-id="83a84-139">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-139">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-140">**app.config .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="83a84-140">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="83a84-141">GCServer</span><span class="sxs-lookup"><span data-stu-id="83a84-141">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="83a84-142">`false`-Stacja robocza</span><span class="sxs-lookup"><span data-stu-id="83a84-142">`false` - workstation</span></span><br/><span data-ttu-id="83a84-143">`true`— serwer</span><span class="sxs-lookup"><span data-stu-id="83a84-143">`true` - server</span></span> |  |

#### <a name="examples"></a><span data-ttu-id="83a84-144">Przykłady</span><span class="sxs-lookup"><span data-stu-id="83a84-144">Examples</span></span>

<span data-ttu-id="83a84-145">*runtimeconfig.js* pliku:</span><span class="sxs-lookup"><span data-stu-id="83a84-145">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="83a84-146">Plik projektu:</span><span class="sxs-lookup"><span data-stu-id="83a84-146">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="background-gc"></a><span data-ttu-id="83a84-147">Odzyskiwanie pamięci w tle</span><span class="sxs-lookup"><span data-stu-id="83a84-147">Background GC</span></span>

- <span data-ttu-id="83a84-148">Określa, czy jest włączone wyrzucanie elementów bezużytecznych w tle.</span><span class="sxs-lookup"><span data-stu-id="83a84-148">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="83a84-149">Domyślne: Użyj w tle GC.</span><span class="sxs-lookup"><span data-stu-id="83a84-149">Default: Use background GC.</span></span> <span data-ttu-id="83a84-150">Jest to równoznaczne z ustawieniem wartości `true` .</span><span class="sxs-lookup"><span data-stu-id="83a84-150">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="83a84-151">Aby uzyskać więcej informacji, zobacz [wyrzucanie elementów bezużytecznych w tle](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="83a84-151">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="83a84-152">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-152">Setting name</span></span> | <span data-ttu-id="83a84-153">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-153">Values</span></span> | <span data-ttu-id="83a84-154">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-154">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-155">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-155">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="83a84-156">`true`-w tle GC</span><span class="sxs-lookup"><span data-stu-id="83a84-156">`true` - background GC</span></span><br/><span data-ttu-id="83a84-157">`false`-niewspółbieżne GC</span><span class="sxs-lookup"><span data-stu-id="83a84-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="83a84-158">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-159">**Właściwość programu MSBuild**</span><span class="sxs-lookup"><span data-stu-id="83a84-159">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="83a84-160">`true`-w tle GC</span><span class="sxs-lookup"><span data-stu-id="83a84-160">`true` - background GC</span></span><br/><span data-ttu-id="83a84-161">`false`-niewspółbieżne GC</span><span class="sxs-lookup"><span data-stu-id="83a84-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="83a84-162">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-163">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-163">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="83a84-164">`1`-w tle GC</span><span class="sxs-lookup"><span data-stu-id="83a84-164">`1` - background GC</span></span><br/><span data-ttu-id="83a84-165">`0`-niewspółbieżne GC</span><span class="sxs-lookup"><span data-stu-id="83a84-165">`0` - non-concurrent GC</span></span> | <span data-ttu-id="83a84-166">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-166">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-167">**app.config .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="83a84-167">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="83a84-168">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="83a84-168">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="83a84-169">`true`-w tle GC</span><span class="sxs-lookup"><span data-stu-id="83a84-169">`true` - background GC</span></span><br/><span data-ttu-id="83a84-170">`false`-niewspółbieżne GC</span><span class="sxs-lookup"><span data-stu-id="83a84-170">`false` - non-concurrent GC</span></span> |  |

#### <a name="examples"></a><span data-ttu-id="83a84-171">Przykłady</span><span class="sxs-lookup"><span data-stu-id="83a84-171">Examples</span></span>

<span data-ttu-id="83a84-172">*runtimeconfig.js* pliku:</span><span class="sxs-lookup"><span data-stu-id="83a84-172">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="83a84-173">Plik projektu:</span><span class="sxs-lookup"><span data-stu-id="83a84-173">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="83a84-174">Zarządzanie użyciem zasobów</span><span class="sxs-lookup"><span data-stu-id="83a84-174">Manage resource usage</span></span>

<span data-ttu-id="83a84-175">Użyj następujących ustawień, aby zarządzać pamięcią i użyciem procesora przez moduł wyrzucania elementów bezużytecznych:</span><span class="sxs-lookup"><span data-stu-id="83a84-175">Use the following settings to manage the garbage collector's memory and processor usage:</span></span>

- [<span data-ttu-id="83a84-176">Koligacji</span><span class="sxs-lookup"><span data-stu-id="83a84-176">Affinitize</span></span>](#affinitize)
- [<span data-ttu-id="83a84-177">Koligacji, maska</span><span class="sxs-lookup"><span data-stu-id="83a84-177">Affinitize mask</span></span>](#affinitize-mask)
- [<span data-ttu-id="83a84-178">Zakresy koligacji</span><span class="sxs-lookup"><span data-stu-id="83a84-178">Affinitize ranges</span></span>](#affinitize-ranges)
- [<span data-ttu-id="83a84-179">Grupy CPU</span><span class="sxs-lookup"><span data-stu-id="83a84-179">CPU groups</span></span>](#cpu-groups)
- [<span data-ttu-id="83a84-180">Liczba stert</span><span class="sxs-lookup"><span data-stu-id="83a84-180">Heap count</span></span>](#heap-count)
- [<span data-ttu-id="83a84-181">Limit sterty</span><span class="sxs-lookup"><span data-stu-id="83a84-181">Heap limit</span></span>](#heap-limit)
- [<span data-ttu-id="83a84-182">Procent limitu sterty</span><span class="sxs-lookup"><span data-stu-id="83a84-182">Heap limit percent</span></span>](#heap-limit-percent)
- [<span data-ttu-id="83a84-183">Duża ilość pamięci (%)</span><span class="sxs-lookup"><span data-stu-id="83a84-183">High memory percent</span></span>](#high-memory-percent)
- [<span data-ttu-id="83a84-184">Limity sterty dla poszczególnych obiektów</span><span class="sxs-lookup"><span data-stu-id="83a84-184">Per-object-heap limits</span></span>](#per-object-heap-limits)
- [<span data-ttu-id="83a84-185">Procent limitów sterty dla poszczególnych obiektów</span><span class="sxs-lookup"><span data-stu-id="83a84-185">Per-object-heap limit percents</span></span>](#per-object-heap-limit-percents)
- [<span data-ttu-id="83a84-186">Zachowaj maszynę wirtualną</span><span class="sxs-lookup"><span data-stu-id="83a84-186">Retain VM</span></span>](#retain-vm)

<span data-ttu-id="83a84-187">Aby uzyskać więcej informacji na temat niektórych z tych ustawień, zapoznaj się z wpisem na blogu centrum [robocze i serwer GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) .</span><span class="sxs-lookup"><span data-stu-id="83a84-187">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="heap-count"></a><span data-ttu-id="83a84-188">Liczba stert</span><span class="sxs-lookup"><span data-stu-id="83a84-188">Heap count</span></span>

- <span data-ttu-id="83a84-189">Ogranicza liczbę stert utworzonych przez moduł wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="83a84-189">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="83a84-190">Dotyczy tylko wyrzucania elementów bezużytecznych serwera.</span><span class="sxs-lookup"><span data-stu-id="83a84-190">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="83a84-191">Jeśli [koligacja procesora GC](#affinitize) jest włączona, co jest ustawieniem domyślnym, licznik sterty ustawia `n` sterty/wątki skoligacony GC na pierwszy `n` procesor.</span><span class="sxs-lookup"><span data-stu-id="83a84-191">If [GC processor affinity](#affinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="83a84-192">(Użyj [koligacji maska](#affinitize-mask) lub ustawienia [zakresów koligacji](#affinitize-ranges) , aby określić, które procesory mają być koligacji).</span><span class="sxs-lookup"><span data-stu-id="83a84-192">(Use the [affinitize mask](#affinitize-mask) or [affinitize ranges](#affinitize-ranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="83a84-193">Jeśli [koligacja procesora GC](#affinitize) jest wyłączona, to ustawienie ogranicza liczbę stert GC.</span><span class="sxs-lookup"><span data-stu-id="83a84-193">If [GC processor affinity](#affinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="83a84-194">Aby uzyskać więcej informacji, zobacz [uwagi GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="83a84-194">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="83a84-195">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-195">Setting name</span></span> | <span data-ttu-id="83a84-196">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-196">Values</span></span> | <span data-ttu-id="83a84-197">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-197">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-198">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-198">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="83a84-199">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-199">*decimal value*</span></span> | <span data-ttu-id="83a84-200">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-200">.NET Core 3.0</span></span> |
| <span data-ttu-id="83a84-201">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-201">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="83a84-202">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-202">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-203">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-203">.NET Core 3.0</span></span> |
| <span data-ttu-id="83a84-204">**app.config .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="83a84-204">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="83a84-205">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="83a84-205">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="83a84-206">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-206">*decimal value*</span></span> | <span data-ttu-id="83a84-207">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="83a84-207">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="83a84-208">Przykład:</span><span class="sxs-lookup"><span data-stu-id="83a84-208">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="83a84-209">Jeśli ustawiasz opcję w *runtimeconfig.jsna*, określ wartość dziesiętną.</span><span class="sxs-lookup"><span data-stu-id="83a84-209">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="83a84-210">Jeśli ustawiasz opcję jako zmienną środowiskową, określ wartość szesnastkową.</span><span class="sxs-lookup"><span data-stu-id="83a84-210">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="83a84-211">Na przykład aby ograniczyć liczbę stert do 16, wartości dla pliku JSON i 0x10 lub 10 dla zmiennej środowiskowej.</span><span class="sxs-lookup"><span data-stu-id="83a84-211">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="affinitize-mask"></a><span data-ttu-id="83a84-212">Koligacji, maska</span><span class="sxs-lookup"><span data-stu-id="83a84-212">Affinitize mask</span></span>

- <span data-ttu-id="83a84-213">Określa dokładne procesory, które powinny być używane przez wątki modułu wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="83a84-213">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="83a84-214">Jeśli [koligacja procesora GC](#affinitize) jest wyłączona, to ustawienie jest ignorowane.</span><span class="sxs-lookup"><span data-stu-id="83a84-214">If [GC processor affinity](#affinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="83a84-215">Dotyczy tylko wyrzucania elementów bezużytecznych serwera.</span><span class="sxs-lookup"><span data-stu-id="83a84-215">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="83a84-216">Wartość jest maską bitową, która definiuje procesory, które są dostępne dla procesu.</span><span class="sxs-lookup"><span data-stu-id="83a84-216">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="83a84-217">Na przykład wartość dziesiętna 1023 (lub wartość szesnastkowa 0x3FF lub 3FF, jeśli używana jest zmienna środowiskowa) to 0011 1111 1111 w notacji binarnej.</span><span class="sxs-lookup"><span data-stu-id="83a84-217">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="83a84-218">Oznacza to, że pierwsze 10 procesorów ma być używany.</span><span class="sxs-lookup"><span data-stu-id="83a84-218">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="83a84-219">Aby określić następne 10 procesorów, czyli procesorów 10-19, określ wartość dziesiętną 1047552 (lub wartość szesnastkową 0xFFC00 lub FFC00), która jest równoważna z wartością binarną 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="83a84-219">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="83a84-220">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-220">Setting name</span></span> | <span data-ttu-id="83a84-221">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-221">Values</span></span> | <span data-ttu-id="83a84-222">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-222">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-223">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-223">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="83a84-224">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-224">*decimal value*</span></span> | <span data-ttu-id="83a84-225">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-225">.NET Core 3.0</span></span> |
| <span data-ttu-id="83a84-226">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-226">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="83a84-227">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-227">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-228">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-228">.NET Core 3.0</span></span> |
| <span data-ttu-id="83a84-229">**app.config .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="83a84-229">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="83a84-230">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="83a84-230">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="83a84-231">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-231">*decimal value*</span></span> | <span data-ttu-id="83a84-232">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="83a84-232">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="83a84-233">Przykład:</span><span class="sxs-lookup"><span data-stu-id="83a84-233">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="affinitize-ranges"></a><span data-ttu-id="83a84-234">Zakresy koligacji</span><span class="sxs-lookup"><span data-stu-id="83a84-234">Affinitize ranges</span></span>

- <span data-ttu-id="83a84-235">Określa listę procesorów, które mają być używane na potrzeby wątków modułu wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="83a84-235">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="83a84-236">To ustawienie jest podobne do [System. GC. HeapAffinitizeMask](#affinitize-mask), z tą różnicą, że umożliwia określenie więcej niż 64 procesorów.</span><span class="sxs-lookup"><span data-stu-id="83a84-236">This setting is similar to [System.GC.HeapAffinitizeMask](#affinitize-mask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="83a84-237">W przypadku systemów operacyjnych Windows należy prefiksować numer procesora lub zakres z odpowiednią [grupą procesorów CPU](/windows/win32/procthread/processor-groups), na przykład "0:1-10, 0:12, 1:50-52, 1:70".</span><span class="sxs-lookup"><span data-stu-id="83a84-237">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="83a84-238">Jeśli [koligacja procesora GC](#affinitize) jest wyłączona, to ustawienie jest ignorowane.</span><span class="sxs-lookup"><span data-stu-id="83a84-238">If [GC processor affinity](#affinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="83a84-239">Dotyczy tylko wyrzucania elementów bezużytecznych serwera.</span><span class="sxs-lookup"><span data-stu-id="83a84-239">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="83a84-240">Aby uzyskać więcej informacji, zobacz temat [Zapewnianie lepszej konfiguracji procesora dla GC na maszynach z > 64 procesorów CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) na blogu Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="83a84-240">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="83a84-241">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-241">Setting name</span></span> | <span data-ttu-id="83a84-242">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-242">Values</span></span> | <span data-ttu-id="83a84-243">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-243">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-244">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-244">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="83a84-245">Rozdzielana przecinkami lista numerów procesorów lub zakresów numerów procesorów.</span><span class="sxs-lookup"><span data-stu-id="83a84-245">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="83a84-246">Przykład UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="83a84-246">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="83a84-247">Przykład systemu Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="83a84-247">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="83a84-248">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-248">.NET Core 3.0</span></span> |
| <span data-ttu-id="83a84-249">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-249">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="83a84-250">Rozdzielana przecinkami lista numerów procesorów lub zakresów numerów procesorów.</span><span class="sxs-lookup"><span data-stu-id="83a84-250">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="83a84-251">Przykład UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="83a84-251">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="83a84-252">Przykład systemu Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="83a84-252">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="83a84-253">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-253">.NET Core 3.0</span></span> |

<span data-ttu-id="83a84-254">Przykład:</span><span class="sxs-lookup"><span data-stu-id="83a84-254">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="cpu-groups"></a><span data-ttu-id="83a84-255">Grupy CPU</span><span class="sxs-lookup"><span data-stu-id="83a84-255">CPU groups</span></span>

- <span data-ttu-id="83a84-256">Określa, czy moduł wyrzucania elementów bezużytecznych używa [grup CPU](/windows/win32/procthread/processor-groups) , czy nie.</span><span class="sxs-lookup"><span data-stu-id="83a84-256">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="83a84-257">Gdy 64-bitowy komputer z systemem Windows ma wiele grup CPU, oznacza to, że istnieje więcej niż 64 procesorów, włączając ten element rozszerza wyrzucanie elementów bezużytecznych we wszystkich grupach CPU.</span><span class="sxs-lookup"><span data-stu-id="83a84-257">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="83a84-258">Moduł wyrzucania elementów bezużytecznych używa wszystkich rdzeni do tworzenia i równoważenia sterty.</span><span class="sxs-lookup"><span data-stu-id="83a84-258">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="83a84-259">Stosuje się do wyrzucania elementów bezużytecznych serwera w 64-bitowych systemach operacyjnych Windows.</span><span class="sxs-lookup"><span data-stu-id="83a84-259">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="83a84-260">Domyślnie: GC nie rozciąga się między grupami CPU.</span><span class="sxs-lookup"><span data-stu-id="83a84-260">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="83a84-261">Jest to równoznaczne z ustawieniem wartości `0` .</span><span class="sxs-lookup"><span data-stu-id="83a84-261">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="83a84-262">Aby uzyskać więcej informacji, zobacz temat [Zapewnianie lepszej konfiguracji procesora dla GC na maszynach z > 64 procesorów CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) na blogu Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="83a84-262">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="83a84-263">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-263">Setting name</span></span> | <span data-ttu-id="83a84-264">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-264">Values</span></span> | <span data-ttu-id="83a84-265">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-265">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-266">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-266">**runtimeconfig.json**</span></span> | `System.GC.CpuGroup` | <span data-ttu-id="83a84-267">`0`-wyłączone</span><span class="sxs-lookup"><span data-stu-id="83a84-267">`0` - disabled</span></span><br/><span data-ttu-id="83a84-268">`1`-włączone</span><span class="sxs-lookup"><span data-stu-id="83a84-268">`1` - enabled</span></span> | <span data-ttu-id="83a84-269">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-269">.NET 5.0</span></span> |
| <span data-ttu-id="83a84-270">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-270">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="83a84-271">`0`-wyłączone</span><span class="sxs-lookup"><span data-stu-id="83a84-271">`0` - disabled</span></span><br/><span data-ttu-id="83a84-272">`1`-włączone</span><span class="sxs-lookup"><span data-stu-id="83a84-272">`1` - enabled</span></span> | <span data-ttu-id="83a84-273">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-273">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-274">**app.config .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="83a84-274">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="83a84-275">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="83a84-275">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="83a84-276">`false`-wyłączone</span><span class="sxs-lookup"><span data-stu-id="83a84-276">`false` - disabled</span></span><br/><span data-ttu-id="83a84-277">`true`-włączone</span><span class="sxs-lookup"><span data-stu-id="83a84-277">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="83a84-278">Aby skonfigurować środowisko uruchomieniowe języka wspólnego (CLR) do dystrybucji wątków z puli wątków we wszystkich grupach procesora, Włącz opcję [Thread_UseAllCpuGroups elementu](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="83a84-278">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="83a84-279">W przypadku aplikacji platformy .NET Core można włączyć tę opcję, ustawiając wartość `COMPlus_Thread_UseAllCpuGroups` zmiennej środowiskowej na `1` .</span><span class="sxs-lookup"><span data-stu-id="83a84-279">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="affinitize"></a><span data-ttu-id="83a84-280">Koligacji</span><span class="sxs-lookup"><span data-stu-id="83a84-280">Affinitize</span></span>

- <span data-ttu-id="83a84-281">Określa, czy *koligacji* wątki odzyskiwania pamięci z procesorami.</span><span class="sxs-lookup"><span data-stu-id="83a84-281">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="83a84-282">Aby koligacji wątek GC, oznacza to, że można go uruchomić tylko w określonym procesorze CPU.</span><span class="sxs-lookup"><span data-stu-id="83a84-282">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="83a84-283">Sterta jest tworzona dla każdego wątku GC.</span><span class="sxs-lookup"><span data-stu-id="83a84-283">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="83a84-284">Dotyczy tylko wyrzucania elementów bezużytecznych serwera.</span><span class="sxs-lookup"><span data-stu-id="83a84-284">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="83a84-285">Domyślnie: koligacji wątki odzyskiwania pamięci z procesorami.</span><span class="sxs-lookup"><span data-stu-id="83a84-285">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="83a84-286">Jest to równoznaczne z ustawieniem wartości `false` .</span><span class="sxs-lookup"><span data-stu-id="83a84-286">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="83a84-287">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-287">Setting name</span></span> | <span data-ttu-id="83a84-288">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-288">Values</span></span> | <span data-ttu-id="83a84-289">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-289">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-290">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-290">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="83a84-291">`false`-koligacji</span><span class="sxs-lookup"><span data-stu-id="83a84-291">`false` - affinitize</span></span><br/><span data-ttu-id="83a84-292">`true`-nie koligacji</span><span class="sxs-lookup"><span data-stu-id="83a84-292">`true` - don't affinitize</span></span> | <span data-ttu-id="83a84-293">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-293">.NET Core 3.0</span></span> |
| <span data-ttu-id="83a84-294">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-294">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="83a84-295">`0`-koligacji</span><span class="sxs-lookup"><span data-stu-id="83a84-295">`0` - affinitize</span></span><br/><span data-ttu-id="83a84-296">`1`-nie koligacji</span><span class="sxs-lookup"><span data-stu-id="83a84-296">`1` - don't affinitize</span></span> | <span data-ttu-id="83a84-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="83a84-298">**app.config .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="83a84-298">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="83a84-299">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="83a84-299">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="83a84-300">`false`-koligacji</span><span class="sxs-lookup"><span data-stu-id="83a84-300">`false` - affinitize</span></span><br/><span data-ttu-id="83a84-301">`true`-nie koligacji</span><span class="sxs-lookup"><span data-stu-id="83a84-301">`true` - don't affinitize</span></span> | <span data-ttu-id="83a84-302">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="83a84-302">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="83a84-303">Przykład:</span><span class="sxs-lookup"><span data-stu-id="83a84-303">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="heap-limit"></a><span data-ttu-id="83a84-304">Limit sterty</span><span class="sxs-lookup"><span data-stu-id="83a84-304">Heap limit</span></span>

- <span data-ttu-id="83a84-305">Określa maksymalny rozmiar zatwierdzeń w bajtach dla sterty GC i księgowości GC.</span><span class="sxs-lookup"><span data-stu-id="83a84-305">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="83a84-306">To ustawienie dotyczy tylko komputerów 64-bitowych.</span><span class="sxs-lookup"><span data-stu-id="83a84-306">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="83a84-307">To ustawienie jest ignorowane, jeśli skonfigurowano [limity sterty dla poszczególnych obiektów](#per-object-heap-limits) .</span><span class="sxs-lookup"><span data-stu-id="83a84-307">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="83a84-308">Wartość domyślna, która stosuje się tylko w niektórych przypadkach, jest większa niż 20 MB lub 75% limitu pamięci w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="83a84-308">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="83a84-309">Wartość domyślna ma zastosowanie, jeśli:</span><span class="sxs-lookup"><span data-stu-id="83a84-309">The default value applies if:</span></span>

  - <span data-ttu-id="83a84-310">Proces jest uruchomiony wewnątrz kontenera o określonym limicie pamięci.</span><span class="sxs-lookup"><span data-stu-id="83a84-310">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="83a84-311">Nie ustawiono wartości [System. GC. HeapHardLimitPercent](#heap-limit-percent) .</span><span class="sxs-lookup"><span data-stu-id="83a84-311">[System.GC.HeapHardLimitPercent](#heap-limit-percent) is not set.</span></span>

| | <span data-ttu-id="83a84-312">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-312">Setting name</span></span> | <span data-ttu-id="83a84-313">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-313">Values</span></span> | <span data-ttu-id="83a84-314">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-314">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-315">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-315">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="83a84-316">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-316">*decimal value*</span></span> | <span data-ttu-id="83a84-317">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-317">.NET Core 3.0</span></span> |
| <span data-ttu-id="83a84-318">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-318">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="83a84-319">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-319">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-320">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-320">.NET Core 3.0</span></span> |

<span data-ttu-id="83a84-321">Przykład:</span><span class="sxs-lookup"><span data-stu-id="83a84-321">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="83a84-322">Jeśli ustawiasz opcję w *runtimeconfig.jsna*, określ wartość dziesiętną.</span><span class="sxs-lookup"><span data-stu-id="83a84-322">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="83a84-323">Jeśli ustawiasz opcję jako zmienną środowiskową, określ wartość szesnastkową.</span><span class="sxs-lookup"><span data-stu-id="83a84-323">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="83a84-324">Na przykład aby określić stały limit sterty wynoszący 200 mebibytes (MiB), wartości byłyby 209715200 dla pliku JSON i 0xC800000 lub C800000 dla zmiennej środowiskowej.</span><span class="sxs-lookup"><span data-stu-id="83a84-324">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="heap-limit-percent"></a><span data-ttu-id="83a84-325">Procent limitu sterty</span><span class="sxs-lookup"><span data-stu-id="83a84-325">Heap limit percent</span></span>

- <span data-ttu-id="83a84-326">Określa dozwolone użycie sterty GC jako procent całkowitej ilości pamięci fizycznej.</span><span class="sxs-lookup"><span data-stu-id="83a84-326">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="83a84-327">Jeśli zostanie również ustawiona wartość [System. GC. HeapHardLimit](#heap-limit) , to ustawienie jest ignorowane.</span><span class="sxs-lookup"><span data-stu-id="83a84-327">If [System.GC.HeapHardLimit](#heap-limit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="83a84-328">To ustawienie dotyczy tylko komputerów 64-bitowych.</span><span class="sxs-lookup"><span data-stu-id="83a84-328">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="83a84-329">Jeśli proces jest uruchomiony wewnątrz kontenera o określonym limicie pamięci, wartość procentowa jest obliczana jako wartość procentowa tego limitu pamięci.</span><span class="sxs-lookup"><span data-stu-id="83a84-329">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="83a84-330">To ustawienie jest ignorowane, jeśli skonfigurowano [limity sterty dla poszczególnych obiektów](#per-object-heap-limits) .</span><span class="sxs-lookup"><span data-stu-id="83a84-330">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="83a84-331">Wartość domyślna, która jest stosowana tylko w niektórych przypadkach, jest mniejsza z 20 MB lub 75% limitu pamięci dla kontenera.</span><span class="sxs-lookup"><span data-stu-id="83a84-331">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="83a84-332">Wartość domyślna ma zastosowanie, jeśli:</span><span class="sxs-lookup"><span data-stu-id="83a84-332">The default value applies if:</span></span>

  - <span data-ttu-id="83a84-333">Proces jest uruchomiony wewnątrz kontenera o określonym limicie pamięci.</span><span class="sxs-lookup"><span data-stu-id="83a84-333">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="83a84-334">Nie ustawiono wartości [System. GC. HeapHardLimit](#heap-limit) .</span><span class="sxs-lookup"><span data-stu-id="83a84-334">[System.GC.HeapHardLimit](#heap-limit) is not set.</span></span>

| | <span data-ttu-id="83a84-335">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-335">Setting name</span></span> | <span data-ttu-id="83a84-336">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-336">Values</span></span> | <span data-ttu-id="83a84-337">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-337">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-338">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-338">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="83a84-339">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-339">*decimal value*</span></span> | <span data-ttu-id="83a84-340">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-340">.NET Core 3.0</span></span> |
| <span data-ttu-id="83a84-341">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-341">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="83a84-342">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-342">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-343">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-343">.NET Core 3.0</span></span> |

<span data-ttu-id="83a84-344">Przykład:</span><span class="sxs-lookup"><span data-stu-id="83a84-344">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="83a84-345">Jeśli ustawiasz opcję w *runtimeconfig.jsna*, określ wartość dziesiętną.</span><span class="sxs-lookup"><span data-stu-id="83a84-345">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="83a84-346">Jeśli ustawiasz opcję jako zmienną środowiskową, określ wartość szesnastkową.</span><span class="sxs-lookup"><span data-stu-id="83a84-346">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="83a84-347">Na przykład aby ograniczyć użycie sterty do 30%, wartości byłyby 30 dla pliku JSON i 0x1E lub 1E dla zmiennej środowiskowej.</span><span class="sxs-lookup"><span data-stu-id="83a84-347">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="83a84-348">Limity sterty dla poszczególnych obiektów</span><span class="sxs-lookup"><span data-stu-id="83a84-348">Per-object-heap limits</span></span>

<span data-ttu-id="83a84-349">Można określić możliwość użycia sterty w pamięci podręcznej na podstawie sterty dla poszczególnych obiektów.</span><span class="sxs-lookup"><span data-stu-id="83a84-349">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="83a84-350">Różne sterty to sterta dużego obiektu (LOH), sterta małego obiektu (raport o niewielkich obiektach) i przypięty stos obiektów (POH).</span><span class="sxs-lookup"><span data-stu-id="83a84-350">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

- <span data-ttu-id="83a84-351">W przypadku określenia wartości dla dowolnego z parametrów, `COMPLUS_GCHeapHardLimitSOH` `COMPLUS_GCHeapHardLimitLOH` lub `COMPLUS_GCHeapHardLimitPOH` , należy również określić wartość dla `COMPLUS_GCHeapHardLimitSOH` i `COMPLUS_GCHeapHardLimitLOH` .</span><span class="sxs-lookup"><span data-stu-id="83a84-351">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="83a84-352">Jeśli tego nie zrobisz, nie będzie można zainicjować środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="83a84-352">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="83a84-353">Wartość domyślna dla `COMPLUS_GCHeapHardLimitPOH` jest równa 0.</span><span class="sxs-lookup"><span data-stu-id="83a84-353">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="83a84-354">`COMPLUS_GCHeapHardLimitSOH`i `COMPLUS_GCHeapHardLimitLOH` nie mają wartości domyślnych.</span><span class="sxs-lookup"><span data-stu-id="83a84-354">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="83a84-355">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-355">Setting name</span></span> | <span data-ttu-id="83a84-356">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-356">Values</span></span> | <span data-ttu-id="83a84-357">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-358">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-358">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitSOH` | <span data-ttu-id="83a84-359">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-359">*decimal value*</span></span> | <span data-ttu-id="83a84-360">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-360">.NET 5.0</span></span> |
| <span data-ttu-id="83a84-361">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-361">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="83a84-362">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-362">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-363">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-363">.NET 5.0</span></span> |

| | <span data-ttu-id="83a84-364">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-364">Setting name</span></span> | <span data-ttu-id="83a84-365">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-365">Values</span></span> | <span data-ttu-id="83a84-366">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-366">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-367">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-367">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitLOH` | <span data-ttu-id="83a84-368">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-368">*decimal value*</span></span> | <span data-ttu-id="83a84-369">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-369">.NET 5.0</span></span> |
| <span data-ttu-id="83a84-370">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-370">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="83a84-371">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-371">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-372">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-372">.NET 5.0</span></span> |

| | <span data-ttu-id="83a84-373">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-373">Setting name</span></span> | <span data-ttu-id="83a84-374">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-374">Values</span></span> | <span data-ttu-id="83a84-375">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-375">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-376">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-376">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPOH` | <span data-ttu-id="83a84-377">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-377">*decimal value*</span></span> | <span data-ttu-id="83a84-378">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-378">.NET 5.0</span></span> |
| <span data-ttu-id="83a84-379">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-379">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="83a84-380">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-380">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-381">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-381">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="83a84-382">Jeśli ustawiasz opcję w *runtimeconfig.jsna*, określ wartość dziesiętną.</span><span class="sxs-lookup"><span data-stu-id="83a84-382">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="83a84-383">Jeśli ustawiasz opcję jako zmienną środowiskową, określ wartość szesnastkową.</span><span class="sxs-lookup"><span data-stu-id="83a84-383">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="83a84-384">Na przykład aby określić stały limit sterty wynoszący 200 mebibytes (MiB), wartości byłyby 209715200 dla pliku JSON i 0xC800000 lub C800000 dla zmiennej środowiskowej.</span><span class="sxs-lookup"><span data-stu-id="83a84-384">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="per-object-heap-limit-percents"></a><span data-ttu-id="83a84-385">Procent limitów sterty dla poszczególnych obiektów</span><span class="sxs-lookup"><span data-stu-id="83a84-385">Per-object-heap limit percents</span></span>

<span data-ttu-id="83a84-386">Można określić możliwość użycia sterty w pamięci podręcznej na podstawie sterty dla poszczególnych obiektów.</span><span class="sxs-lookup"><span data-stu-id="83a84-386">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="83a84-387">Różne sterty to sterta dużego obiektu (LOH), sterta małego obiektu (raport o niewielkich obiektach) i przypięty stos obiektów (POH).</span><span class="sxs-lookup"><span data-stu-id="83a84-387">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

- <span data-ttu-id="83a84-388">W przypadku określenia wartości dla dowolnego z parametrów, `COMPLUS_GCHeapHardLimitSOHPercent` `COMPLUS_GCHeapHardLimitLOHPercent` lub `COMPLUS_GCHeapHardLimitPOHPercent` , należy również określić wartość dla `COMPLUS_GCHeapHardLimitSOHPercent` i `COMPLUS_GCHeapHardLimitLOHPercent` .</span><span class="sxs-lookup"><span data-stu-id="83a84-388">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="83a84-389">Jeśli tego nie zrobisz, nie będzie można zainicjować środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="83a84-389">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="83a84-390">Te ustawienia są ignorowane `COMPLUS_GCHeapHardLimitSOH` w przypadku, gdy `COMPLUS_GCHeapHardLimitLOH` `COMPLUS_GCHeapHardLimitPOH` są określone.</span><span class="sxs-lookup"><span data-stu-id="83a84-390">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="83a84-391">Wartość 1 oznacza, że GC używa 1% całkowitej pamięci fizycznej dla sterty obiektu.</span><span class="sxs-lookup"><span data-stu-id="83a84-391">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="83a84-392">Każda wartość musi być większa niż zero i mniejsza niż 100.</span><span class="sxs-lookup"><span data-stu-id="83a84-392">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="83a84-393">Ponadto suma trzech wartości procentowych musi być mniejsza niż 100.</span><span class="sxs-lookup"><span data-stu-id="83a84-393">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="83a84-394">W przeciwnym razie nie będzie można zainicjować środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="83a84-394">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="83a84-395">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-395">Setting name</span></span> | <span data-ttu-id="83a84-396">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-396">Values</span></span> | <span data-ttu-id="83a84-397">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-397">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-398">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-398">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitSOHPercent` | <span data-ttu-id="83a84-399">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-399">*decimal value*</span></span> | <span data-ttu-id="83a84-400">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-400">.NET 5.0</span></span> |
| <span data-ttu-id="83a84-401">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-401">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="83a84-402">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-402">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-403">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-403">.NET 5.0</span></span> |

| | <span data-ttu-id="83a84-404">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-404">Setting name</span></span> | <span data-ttu-id="83a84-405">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-405">Values</span></span> | <span data-ttu-id="83a84-406">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-406">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-407">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-407">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitLOHPercent` | <span data-ttu-id="83a84-408">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-408">*decimal value*</span></span> | <span data-ttu-id="83a84-409">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-409">.NET 5.0</span></span> |
| <span data-ttu-id="83a84-410">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-410">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="83a84-411">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-411">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-412">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-412">.NET 5.0</span></span> |

| | <span data-ttu-id="83a84-413">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-413">Setting name</span></span> | <span data-ttu-id="83a84-414">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-414">Values</span></span> | <span data-ttu-id="83a84-415">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-416">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-416">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPOHPercent` | <span data-ttu-id="83a84-417">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-417">*decimal value*</span></span> | <span data-ttu-id="83a84-418">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-418">.NET 5.0</span></span> |
| <span data-ttu-id="83a84-419">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-419">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="83a84-420">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-420">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-421">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-421">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="83a84-422">Jeśli ustawiasz opcję w *runtimeconfig.jsna*, określ wartość dziesiętną.</span><span class="sxs-lookup"><span data-stu-id="83a84-422">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="83a84-423">Jeśli ustawiasz opcję jako zmienną środowiskową, określ wartość szesnastkową.</span><span class="sxs-lookup"><span data-stu-id="83a84-423">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="83a84-424">Na przykład aby ograniczyć użycie sterty do 30%, wartości byłyby 30 dla pliku JSON i 0x1E lub 1E dla zmiennej środowiskowej.</span><span class="sxs-lookup"><span data-stu-id="83a84-424">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="high-memory-percent"></a><span data-ttu-id="83a84-425">Duża ilość pamięci (%)</span><span class="sxs-lookup"><span data-stu-id="83a84-425">High memory percent</span></span>

<span data-ttu-id="83a84-426">Obciążenie pamięci jest wskazywane przez procent używanej pamięci fizycznej.</span><span class="sxs-lookup"><span data-stu-id="83a84-426">Memory load is indicated by the percentage of physical memory in use.</span></span> <span data-ttu-id="83a84-427">Domyślnie, gdy obciążenie pamięci fizycznej osiągnie **90%**, wyrzucanie elementów bezużytecznych jest bardziej agresywne na potrzeby tworzenia pełnych, kompaktowych kolekcji elementów bezużytecznych w celu uniknięcia stronicowania.</span><span class="sxs-lookup"><span data-stu-id="83a84-427">By default, when the physical memory load reaches **90%**, garbage collection becomes more aggressive about doing full, compacting garbage collections to avoid paging.</span></span> <span data-ttu-id="83a84-428">Gdy obciążenie pamięci jest poniżej 90%, system GC preferuje kolekcje w tle dla pełnych kolekcji elementów bezużytecznych, które mają krótsze przerwy, ale nie zmniejszają łącznego rozmiaru sterty o wiele.</span><span class="sxs-lookup"><span data-stu-id="83a84-428">When memory load is below 90%, GC favors background collections for full garbage collections, which have shorter pauses but don't reduce the total heap size by much.</span></span> <span data-ttu-id="83a84-429">Na maszynach ze znaczną ilością pamięci (80 GB lub więcej) domyślny próg obciążenia wynosi od 90% do 97%.</span><span class="sxs-lookup"><span data-stu-id="83a84-429">On machines with a significant amount of memory (80GB or more), the default load threshold is between 90% and 97%.</span></span>

<span data-ttu-id="83a84-430">Próg dużego obciążenia pamięci można dostosować za pomocą `COMPlus_GCHighMemPercent` Ustawienia zmienna środowiskowa lub `System.GC.HighMemoryPercent` Konfiguracja JSON.</span><span class="sxs-lookup"><span data-stu-id="83a84-430">The high memory load threshold can be adjusted by the `COMPlus_GCHighMemPercent` environment variable or `System.GC.HighMemoryPercent` JSON configuration setting.</span></span> <span data-ttu-id="83a84-431">Należy rozważyć dostosowanie progu, jeśli chcesz kontrolować rozmiar sterty.</span><span class="sxs-lookup"><span data-stu-id="83a84-431">Consider adjusting the threshold if you want to control heap size.</span></span> <span data-ttu-id="83a84-432">Na przykład w przypadku procesu dominującego na komputerze z 64 GB pamięci jest uzasadnione, aby system GC uruchomił odzyskiwanie, gdy jest dostępnych 10% pamięci.</span><span class="sxs-lookup"><span data-stu-id="83a84-432">For example, for the dominant process on a machine with 64GB of memory, it's reasonable for GC to start reacting when there's 10% of memory available.</span></span> <span data-ttu-id="83a84-433">Jednak w przypadku mniejszych procesów, na przykład proces, który zużywa tylko 1 GB pamięci, wykaz globalny może wygodnie działać z mniej niż 10% dostępnej pamięci.</span><span class="sxs-lookup"><span data-stu-id="83a84-433">But for smaller processes, for example, a process that only consumes 1GB of memory, GC can comfortably run with less than 10% of memory available.</span></span> <span data-ttu-id="83a84-434">W przypadku tych mniejszych procesów należy rozważyć ustawienie progu wyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="83a84-434">For these smaller processes, consider setting the threshold higher.</span></span> <span data-ttu-id="83a84-435">Z drugiej strony, jeśli chcesz, aby większa liczba procesów miała mniejsze rozmiary sterty (nawet w przypadku dużej ilości dostępnej pamięci fizycznej), obniżenie tego progu jest skutecznym sposobem, aby system GC mógł już reagować na kompaktowanie sterty.</span><span class="sxs-lookup"><span data-stu-id="83a84-435">On the other hand, if you want larger processes to have smaller heap sizes (even when there's plenty of physical memory available), lowering this threshold is an effective way for GC to react sooner to compact the heap down.</span></span>

> [!NOTE]
> <span data-ttu-id="83a84-436">W przypadku procesów uruchomionych w kontenerze GC traktuje pamięć fizyczną na podstawie limitu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="83a84-436">For processes running in a container, GC considers the physical memory based on the container limit.</span></span>

| | <span data-ttu-id="83a84-437">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-437">Setting name</span></span> | <span data-ttu-id="83a84-438">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-438">Values</span></span> | <span data-ttu-id="83a84-439">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-439">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-440">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-440">**runtimeconfig.json**</span></span> | `System.GC.HighMemoryPercent` | <span data-ttu-id="83a84-441">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-441">*decimal value*</span></span> | <span data-ttu-id="83a84-442">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="83a84-442">.NET 5.0</span></span> |
| <span data-ttu-id="83a84-443">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-443">**Environment variable**</span></span> | `COMPlus_GCHighMemPercent` | <span data-ttu-id="83a84-444">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-444">*hexadecimal value*</span></span> | |

> [!TIP]
> <span data-ttu-id="83a84-445">Jeśli ustawiasz opcję w *runtimeconfig.jsna*, określ wartość dziesiętną.</span><span class="sxs-lookup"><span data-stu-id="83a84-445">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="83a84-446">Jeśli ustawiasz opcję jako zmienną środowiskową, określ wartość szesnastkową.</span><span class="sxs-lookup"><span data-stu-id="83a84-446">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="83a84-447">Na przykład, aby ustawić wysoki próg pamięci na 75%, wartości byłyby 75 dla pliku JSON i 0x4B lub 4B dla zmiennej środowiskowej.</span><span class="sxs-lookup"><span data-stu-id="83a84-447">For example, to set the high memory threshold to 75%, the values would be 75 for the JSON file and 0x4B or 4B for the environment variable.</span></span>

### <a name="retain-vm"></a><span data-ttu-id="83a84-448">Zachowaj maszynę wirtualną</span><span class="sxs-lookup"><span data-stu-id="83a84-448">Retain VM</span></span>

- <span data-ttu-id="83a84-449">Określa, czy segmenty, które mają zostać usunięte, są umieszczane na liście gotowości do użycia w przyszłości lub są wyłączane z powrotem do systemu operacyjnego (OS).</span><span class="sxs-lookup"><span data-stu-id="83a84-449">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="83a84-450">Domyślnie: segmenty wydań z powrotem do systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="83a84-450">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="83a84-451">Jest to równoznaczne z ustawieniem wartości `false` .</span><span class="sxs-lookup"><span data-stu-id="83a84-451">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="83a84-452">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-452">Setting name</span></span> | <span data-ttu-id="83a84-453">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-453">Values</span></span> | <span data-ttu-id="83a84-454">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-454">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-455">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-455">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="83a84-456">`false`— wydanie do systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="83a84-456">`false` - release to OS</span></span><br/><span data-ttu-id="83a84-457">`true`— Umieść w stanie wstrzymania</span><span class="sxs-lookup"><span data-stu-id="83a84-457">`true` - put on standby</span></span> | <span data-ttu-id="83a84-458">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-458">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-459">**Właściwość programu MSBuild**</span><span class="sxs-lookup"><span data-stu-id="83a84-459">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="83a84-460">`false`— wydanie do systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="83a84-460">`false` - release to OS</span></span><br/><span data-ttu-id="83a84-461">`true`— Umieść w stanie wstrzymania</span><span class="sxs-lookup"><span data-stu-id="83a84-461">`true` - put on standby</span></span> | <span data-ttu-id="83a84-462">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-462">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-463">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-463">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="83a84-464">`0`— wydanie do systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="83a84-464">`0` - release to OS</span></span><br/><span data-ttu-id="83a84-465">`1`— Umieść w stanie wstrzymania</span><span class="sxs-lookup"><span data-stu-id="83a84-465">`1` - put on standby</span></span> | <span data-ttu-id="83a84-466">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-466">.NET Core 1.0</span></span> |

#### <a name="examples"></a><span data-ttu-id="83a84-467">Przykłady</span><span class="sxs-lookup"><span data-stu-id="83a84-467">Examples</span></span>

<span data-ttu-id="83a84-468">*runtimeconfig.js* pliku:</span><span class="sxs-lookup"><span data-stu-id="83a84-468">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="83a84-469">Plik projektu:</span><span class="sxs-lookup"><span data-stu-id="83a84-469">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="83a84-470">Duże strony</span><span class="sxs-lookup"><span data-stu-id="83a84-470">Large pages</span></span>

- <span data-ttu-id="83a84-471">Określa, czy mają być używane duże strony, gdy jest ustawiony limit sztywny sterty.</span><span class="sxs-lookup"><span data-stu-id="83a84-471">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="83a84-472">Domyślnie: nie używaj dużych stron, gdy jest ustawiony limit sztywny sterty.</span><span class="sxs-lookup"><span data-stu-id="83a84-472">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="83a84-473">Jest to równoznaczne z ustawieniem wartości `0` .</span><span class="sxs-lookup"><span data-stu-id="83a84-473">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="83a84-474">Jest to ustawienie eksperymentalne.</span><span class="sxs-lookup"><span data-stu-id="83a84-474">This is an experimental setting.</span></span>

| | <span data-ttu-id="83a84-475">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-475">Setting name</span></span> | <span data-ttu-id="83a84-476">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-476">Values</span></span> | <span data-ttu-id="83a84-477">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-477">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-478">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-478">**runtimeconfig.json**</span></span> | <span data-ttu-id="83a84-479">NIE DOTYCZY</span><span class="sxs-lookup"><span data-stu-id="83a84-479">N/A</span></span> | <span data-ttu-id="83a84-480">NIE DOTYCZY</span><span class="sxs-lookup"><span data-stu-id="83a84-480">N/A</span></span> | <span data-ttu-id="83a84-481">NIE DOTYCZY</span><span class="sxs-lookup"><span data-stu-id="83a84-481">N/A</span></span> |
| <span data-ttu-id="83a84-482">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-482">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="83a84-483">`0`-wyłączone</span><span class="sxs-lookup"><span data-stu-id="83a84-483">`0` - disabled</span></span><br/><span data-ttu-id="83a84-484">`1`-włączone</span><span class="sxs-lookup"><span data-stu-id="83a84-484">`1` - enabled</span></span> | <span data-ttu-id="83a84-485">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="83a84-485">.NET Core 3.0</span></span> |

## <a name="allow-large-objects"></a><span data-ttu-id="83a84-486">Zezwalaj na duże obiekty</span><span class="sxs-lookup"><span data-stu-id="83a84-486">Allow large objects</span></span>

- <span data-ttu-id="83a84-487">Konfiguruje obsługę modułu wyrzucania elementów bezużytecznych na platformach 64-bitowych dla tablic, które są większe niż 2 gigabajty (GB) w łącznym rozmiarze.</span><span class="sxs-lookup"><span data-stu-id="83a84-487">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="83a84-488">Domyślnie: GLOBALna obsługa tablic o pojemności większej niż 2 GB.</span><span class="sxs-lookup"><span data-stu-id="83a84-488">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="83a84-489">Jest to równoznaczne z ustawieniem wartości `1` .</span><span class="sxs-lookup"><span data-stu-id="83a84-489">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="83a84-490">Ta opcja może stać się przestarzała w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="83a84-490">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="83a84-491">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-491">Setting name</span></span> | <span data-ttu-id="83a84-492">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-492">Values</span></span> | <span data-ttu-id="83a84-493">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-493">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-494">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-494">**runtimeconfig.json**</span></span> | <span data-ttu-id="83a84-495">NIE DOTYCZY</span><span class="sxs-lookup"><span data-stu-id="83a84-495">N/A</span></span> | <span data-ttu-id="83a84-496">NIE DOTYCZY</span><span class="sxs-lookup"><span data-stu-id="83a84-496">N/A</span></span> | <span data-ttu-id="83a84-497">NIE DOTYCZY</span><span class="sxs-lookup"><span data-stu-id="83a84-497">N/A</span></span> |
| <span data-ttu-id="83a84-498">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-498">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="83a84-499">`1`-włączone</span><span class="sxs-lookup"><span data-stu-id="83a84-499">`1` - enabled</span></span><br/> <span data-ttu-id="83a84-500">`0`-wyłączone</span><span class="sxs-lookup"><span data-stu-id="83a84-500">`0` - disabled</span></span> | <span data-ttu-id="83a84-501">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-501">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-502">**app.config .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="83a84-502">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="83a84-503">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="83a84-503">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="83a84-504">`1`-włączone</span><span class="sxs-lookup"><span data-stu-id="83a84-504">`1` - enabled</span></span><br/> <span data-ttu-id="83a84-505">`0`-wyłączone</span><span class="sxs-lookup"><span data-stu-id="83a84-505">`0` - disabled</span></span> | <span data-ttu-id="83a84-506">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="83a84-506">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="83a84-507">Próg sterty dla dużego obiektu</span><span class="sxs-lookup"><span data-stu-id="83a84-507">Large object heap threshold</span></span>

- <span data-ttu-id="83a84-508">Określa rozmiar progu (w bajtach), który powoduje, że obiekty są na stosie dużego obiektu (LOH).</span><span class="sxs-lookup"><span data-stu-id="83a84-508">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="83a84-509">Domyślny próg to 85 000 bajtów.</span><span class="sxs-lookup"><span data-stu-id="83a84-509">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="83a84-510">Określona wartość musi być większa niż wartość progu domyślnego.</span><span class="sxs-lookup"><span data-stu-id="83a84-510">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="83a84-511">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-511">Setting name</span></span> | <span data-ttu-id="83a84-512">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-512">Values</span></span> | <span data-ttu-id="83a84-513">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-513">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-514">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-514">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="83a84-515">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-515">*decimal value*</span></span> | <span data-ttu-id="83a84-516">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-516">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-517">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-517">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="83a84-518">*wartość szesnastkowa*</span><span class="sxs-lookup"><span data-stu-id="83a84-518">*hexadecimal value*</span></span> | <span data-ttu-id="83a84-519">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="83a84-519">.NET Core 1.0</span></span> |
| <span data-ttu-id="83a84-520">**app.config .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="83a84-520">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="83a84-521">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="83a84-521">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="83a84-522">*wartość dziesiętna*</span><span class="sxs-lookup"><span data-stu-id="83a84-522">*decimal value*</span></span> | <span data-ttu-id="83a84-523"> .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="83a84-523">.NET Framework 4.8</span></span> |

<span data-ttu-id="83a84-524">Przykład:</span><span class="sxs-lookup"><span data-stu-id="83a84-524">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="83a84-525">Jeśli ustawiasz opcję w *runtimeconfig.jsna*, określ wartość dziesiętną.</span><span class="sxs-lookup"><span data-stu-id="83a84-525">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="83a84-526">Jeśli ustawiasz opcję jako zmienną środowiskową, określ wartość szesnastkową.</span><span class="sxs-lookup"><span data-stu-id="83a84-526">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="83a84-527">Na przykład, aby ustawić rozmiar progu 120 000 bajtów, wartości byłyby 120000 dla pliku JSON oraz 0x1D4C0 lub 1D4C0 dla zmiennej środowiskowej.</span><span class="sxs-lookup"><span data-stu-id="83a84-527">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="83a84-528">Autonomiczna GC</span><span class="sxs-lookup"><span data-stu-id="83a84-528">Standalone GC</span></span>

- <span data-ttu-id="83a84-529">Określa ścieżkę do biblioteki zawierającej Moduł wyrzucania elementów bezużytecznych, który środowisko uruchomieniowe zamierza załadować.</span><span class="sxs-lookup"><span data-stu-id="83a84-529">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="83a84-530">Aby uzyskać więcej informacji, zobacz [prekonstrukcja modułu ładującego GC](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="83a84-530">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="83a84-531">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="83a84-531">Setting name</span></span> | <span data-ttu-id="83a84-532">Wartości</span><span class="sxs-lookup"><span data-stu-id="83a84-532">Values</span></span> | <span data-ttu-id="83a84-533">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83a84-533">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="83a84-534">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="83a84-534">**runtimeconfig.json**</span></span> | <span data-ttu-id="83a84-535">NIE DOTYCZY</span><span class="sxs-lookup"><span data-stu-id="83a84-535">N/A</span></span> | <span data-ttu-id="83a84-536">NIE DOTYCZY</span><span class="sxs-lookup"><span data-stu-id="83a84-536">N/A</span></span> | <span data-ttu-id="83a84-537">NIE DOTYCZY</span><span class="sxs-lookup"><span data-stu-id="83a84-537">N/A</span></span> |
| <span data-ttu-id="83a84-538">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="83a84-538">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="83a84-539">*string_path*</span><span class="sxs-lookup"><span data-stu-id="83a84-539">*string_path*</span></span> | <span data-ttu-id="83a84-540">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="83a84-540">.NET Core 2.0</span></span> |
