---
title: Przegląd wdrażania ReadyToRun
description: Dowiedz się, jakie wdrożenia ReadyToRun są i dlaczego należy rozważyć użycie jej jako części publikowania aplikacji z .NET 5 i .NET Core 3,0 i nowszych.
author: davidwr
ms.author: davidwr
ms.date: 09/21/2020
ms.openlocfilehash: b4052a0c0f4ed9f6cfd273abe5ef45d018bd0ae0
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654964"
---
# <a name="readytorun-compilation"></a><span data-ttu-id="d037f-103">Kompilacja ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="d037f-103">ReadyToRun Compilation</span></span>

<span data-ttu-id="d037f-104">Czas uruchamiania aplikacji .NET i opóźnienia można ulepszyć, kompilując zestawy aplikacji jako ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="d037f-104">.NET application startup time and latency can be improved by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="d037f-105">R2R to forma kompilacji z wyprzedzeniem (AOT).</span><span class="sxs-lookup"><span data-stu-id="d037f-105">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="d037f-106">Pliki binarne R2R zwiększają wydajność uruchamiania przez zmniejszenie ilości pracy kompilatora, który jest potrzebny do załadowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d037f-106">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="d037f-107">Pliki binarne zawierają podobny kod natywny w porównaniu z przeznaczeniem JIT.</span><span class="sxs-lookup"><span data-stu-id="d037f-107">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="d037f-108">R2R pliki binarne są jednak większe, ponieważ zawierają kod języka pośredniego (IL), który jest nadal wymagany w niektórych scenariuszach i natywną wersję tego samego kodu.</span><span class="sxs-lookup"><span data-stu-id="d037f-108">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="d037f-109">R2R jest dostępna tylko w przypadku publikowania aplikacji, która jest przeznaczona dla określonych środowisk uruchomieniowych (RID), takich jak Linux x64 lub Windows x64.</span><span class="sxs-lookup"><span data-stu-id="d037f-109">R2R is only available when you publish an app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="d037f-110">Aby skompilować projekt jako ReadyToRun, aplikacja musi być opublikowana z właściwością PublishReadyToRun ustawioną na wartość true.</span><span class="sxs-lookup"><span data-stu-id="d037f-110">To compile your project as ReadyToRun, the application must be published with the PublishReadyToRun property set to true.</span></span>

<span data-ttu-id="d037f-111">Istnieją dwa sposoby publikowania aplikacji jako ReadyToRun:</span><span class="sxs-lookup"><span data-stu-id="d037f-111">There are two ways to publish your app as ReadyToRun:</span></span>

01. <span data-ttu-id="d037f-112">Określ flagę PublishReadyToRun bezpośrednio w poleceniu dotnet publish.</span><span class="sxs-lookup"><span data-stu-id="d037f-112">Specify the PublishReadyToRun flag directly to the dotnet publish command.</span></span> <span data-ttu-id="d037f-113">Aby uzyskać szczegółowe informacje, zobacz [dotnet Publish](../tools/dotnet-publish.md) .</span><span class="sxs-lookup"><span data-stu-id="d037f-113">See [dotnet publish](../tools/dotnet-publish.md) for details.</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 -p:PublishReadyToRun=true
    ```

02. <span data-ttu-id="d037f-114">Określ właściwość w projekcie</span><span class="sxs-lookup"><span data-stu-id="d037f-114">Specify the property in the project</span></span>

    - <span data-ttu-id="d037f-115">Dodaj `<PublishReadyToRun>` ustawienie do projektu.</span><span class="sxs-lookup"><span data-stu-id="d037f-115">Add the `<PublishReadyToRun>` setting to your project.</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

    - <span data-ttu-id="d037f-116">Opublikuj aplikację bez żadnych specjalnych parametrów.</span><span class="sxs-lookup"><span data-stu-id="d037f-116">Publish the application without any special parameters.</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64
    ```

## <a name="impact-of-using-the-readytorun-feature"></a><span data-ttu-id="d037f-117">Wpływ używania funkcji ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="d037f-117">Impact of using the ReadyToRun feature</span></span>

<span data-ttu-id="d037f-118">Kompilacja przed czasem ma skomplikowany wpływ na wydajność aplikacji, co może być trudne do przewidywania.</span><span class="sxs-lookup"><span data-stu-id="d037f-118">Ahead-of-time compilation has complex performance impact on application performance, which may be difficult to predict.</span></span> <span data-ttu-id="d037f-119">Ogólnie rzecz biorąc, rozmiar zestawu zostanie powiększony do wartości z przedziału od dwóch do trzech razy większych.</span><span class="sxs-lookup"><span data-stu-id="d037f-119">In general, the size of an assembly will grow to between two to three times larger.</span></span> <span data-ttu-id="d037f-120">Ten wzrost rozmiaru fizycznego pliku może zmniejszyć wydajność ładowania zestawu z dysku i zwiększyć zestaw roboczy procesu.</span><span class="sxs-lookup"><span data-stu-id="d037f-120">This increase in the physical size of the file may reduce the performance of loading the assembly from disk, and increase working set of the process.</span></span> <span data-ttu-id="d037f-121">Jednak w przypadku zwracania Liczba metod skompilowanych w czasie wykonywania jest zwykle ograniczona.</span><span class="sxs-lookup"><span data-stu-id="d037f-121">However, in return the number of methods compiled at runtime is typically reduced substantially.</span></span> <span data-ttu-id="d037f-122">Wynika to z tego, że większość aplikacji, które mają duże ilości kodu, uzyskuje korzyści z używania funkcji ReadyToRun.</span><span class="sxs-lookup"><span data-stu-id="d037f-122">The result is that most applications that large amounts of code receive large performance benefits from enabling ReadyToRun.</span></span> <span data-ttu-id="d037f-123">Aplikacje, które mają niewielkie ilości kodu, prawdopodobnie nie wystąpią znaczącej poprawy dotyczącej włączania ReadyToRun, ponieważ biblioteki środowiska uruchomieniowego platformy .NET zostały już wstępnie skompilowane z ReadyToRun.</span><span class="sxs-lookup"><span data-stu-id="d037f-123">Applications, which have small amounts of code will likely not experience a significant improvement from enabling ReadyToRun, as the .NET runtime libraries have already been precompiled with ReadyToRun.</span></span>

<span data-ttu-id="d037f-124">Ulepszenia uruchamiania omówione tutaj dotyczą tylko uruchamiania aplikacji, ale również do pierwszego użycia dowolnego kodu w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d037f-124">The startup improvement discussed here applies not only to application startup, but also to the first use of any code in the application.</span></span> <span data-ttu-id="d037f-125">Na przykład można użyć ReadyToRun, aby zmniejszyć opóźnienie odpowiedzi pierwszego użycia internetowego interfejsu API w aplikacji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d037f-125">For instance, ReadyToRun can be used to reduce the response latency of the first use  of Web API in an ASP.NET application.</span></span>

### <a name="interaction-with-tiered-compilation"></a><span data-ttu-id="d037f-126">Interakcja z kompilacją warstwową</span><span class="sxs-lookup"><span data-stu-id="d037f-126">Interaction with tiered compilation</span></span>

<span data-ttu-id="d037f-127">Wygenerowane przed chwilą nie jest tak wysoce zoptymalizowany jak kod generowany przez JIT.</span><span class="sxs-lookup"><span data-stu-id="d037f-127">Ahead-of-time generated is not as highly optimized as code produced by the JIT.</span></span> <span data-ttu-id="d037f-128">Aby rozwiązać ten problem, kompilacja warstwowa zastępuje często używane metody ReadyToRun z metodami generowanymi przez JIT.</span><span class="sxs-lookup"><span data-stu-id="d037f-128">To address this issue, tiered compilation will replace commonly used ReadyToRun methods with JIT-generated methods.</span></span>

## <a name="how-is-the-set-of-precompiled-assemblies-chosen"></a><span data-ttu-id="d037f-129">Jak wybierany jest zestaw wstępnie skompilowanych zestawów?</span><span class="sxs-lookup"><span data-stu-id="d037f-129">How is the set of precompiled assemblies chosen?</span></span>

<span data-ttu-id="d037f-130">Zestaw SDK kompiluje zestawy, które są dystrybuowane z aplikacją.</span><span class="sxs-lookup"><span data-stu-id="d037f-130">The SDK will precompile the assemblies that are distributed with the application.</span></span> <span data-ttu-id="d037f-131">W przypadku aplikacji samodzielnych zestaw zestawów będzie obejmował strukturę.</span><span class="sxs-lookup"><span data-stu-id="d037f-131">For self-contained applications, this set of assemblies will include the framework.</span></span> <span data-ttu-id="d037f-132">Pliki binarne języka C++/CLI nie kwalifikują się do kompilacji ReadyToRun.</span><span class="sxs-lookup"><span data-stu-id="d037f-132">C++/CLI binaries are not eligible for ReadyToRun compilation.</span></span>

## <a name="how-is-the-set-of-methods-to-precompile-chosen"></a><span data-ttu-id="d037f-133">Jak wybierany jest zestaw metod do wstępnej kompilacji?</span><span class="sxs-lookup"><span data-stu-id="d037f-133">How is the set of methods to precompile chosen?</span></span>

<span data-ttu-id="d037f-134">Kompilator podejmie próbę wstępnego skompilowania możliwie największej liczby metod.</span><span class="sxs-lookup"><span data-stu-id="d037f-134">The compiler will attempt to pre-compile as many methods as it can.</span></span> <span data-ttu-id="d037f-135">Jednak z różnych powodów nie jest oczekiwane, że użycie funkcji ReadyToRun spowoduje uniemożliwienie wykonania JIT.</span><span class="sxs-lookup"><span data-stu-id="d037f-135">However various reasons it is not expected that using the ReadyToRun feature will result in preventing the JIT from executing.</span></span>

<span data-ttu-id="d037f-136">Takie przyczyny mogą obejmować, ale nie są ograniczone do:</span><span class="sxs-lookup"><span data-stu-id="d037f-136">Such reasons may include, but are not limited to:</span></span>

- <span data-ttu-id="d037f-137">Użycie typów ogólnych zdefiniowanych w oddzielnych zestawach</span><span class="sxs-lookup"><span data-stu-id="d037f-137">Use of generic types defined in separate assemblies</span></span>
- <span data-ttu-id="d037f-138">Współdziałanie z kodem natywnym</span><span class="sxs-lookup"><span data-stu-id="d037f-138">Interop with native code</span></span>
- <span data-ttu-id="d037f-139">Korzystanie z wewnętrznych elementów sprzętowych, których kompilator nie może udowodnić, jest bezpieczne do użycia na komputerze docelowym</span><span class="sxs-lookup"><span data-stu-id="d037f-139">Use of hardware intrinsics that the compiler cannot prove are safe to use on a target machine</span></span>
- <span data-ttu-id="d037f-140">Niektóre nietypowe wzorce IL</span><span class="sxs-lookup"><span data-stu-id="d037f-140">Certain unusual IL patterns</span></span>
- <span data-ttu-id="d037f-141">Dynamiczne tworzenie metod przy użyciu odbicia lub LINQ</span><span class="sxs-lookup"><span data-stu-id="d037f-141">Dynamic method creation via reflection, or LINQ</span></span>

## <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="d037f-142">Ograniczenia dotyczące wielu platform/architektury</span><span class="sxs-lookup"><span data-stu-id="d037f-142">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="d037f-143">W przypadku niektórych platform zestawu SDK kompilator ReadyToRun jest w stanie wykonać kompilację krzyżową dla innych platform docelowych.</span><span class="sxs-lookup"><span data-stu-id="d037f-143">For some SDK platforms, the ReadyToRun compiler is capable of cross-compiling for other target platforms.</span></span> <span data-ttu-id="d037f-144">Obsługiwane elementy docelowe kompilacji są opisane w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="d037f-144">Supported compilation targets are described in the table below.</span></span>

| <span data-ttu-id="d037f-145">Platforma SDK</span><span class="sxs-lookup"><span data-stu-id="d037f-145">SDK platform</span></span> | <span data-ttu-id="d037f-146">Obsługiwane platformy docelowe</span><span class="sxs-lookup"><span data-stu-id="d037f-146">Supported target platforms</span></span> |
| ------------ | --------------------------- |
| <span data-ttu-id="d037f-147">Windows x64</span><span class="sxs-lookup"><span data-stu-id="d037f-147">Windows X64</span></span>  | <span data-ttu-id="d037f-148">Windows x86, Windows x64, Windows ARM32, Windows ARM64</span><span class="sxs-lookup"><span data-stu-id="d037f-148">Windows X86, Windows X64, Windows ARM32, Windows ARM64</span></span> |
| <span data-ttu-id="d037f-149">Windows x86</span><span class="sxs-lookup"><span data-stu-id="d037f-149">Windows X86</span></span>  | <span data-ttu-id="d037f-150">Windows x86, Windows ARM32</span><span class="sxs-lookup"><span data-stu-id="d037f-150">Windows X86, Windows ARM32</span></span> |
| <span data-ttu-id="d037f-151">Linux x64</span><span class="sxs-lookup"><span data-stu-id="d037f-151">Linux X64</span></span>    | <span data-ttu-id="d037f-152">Linux x86, Linux x64, Linux ARM32, Linux ARM64</span><span class="sxs-lookup"><span data-stu-id="d037f-152">Linux X86, Linux X64, Linux ARM32, Linux ARM64</span></span> |
| <span data-ttu-id="d037f-153">Linux ARM32</span><span class="sxs-lookup"><span data-stu-id="d037f-153">Linux ARM32</span></span>  | <span data-ttu-id="d037f-154">Linux ARM32</span><span class="sxs-lookup"><span data-stu-id="d037f-154">Linux ARM32</span></span> |
| <span data-ttu-id="d037f-155">ARM64 systemu Linux</span><span class="sxs-lookup"><span data-stu-id="d037f-155">Linux ARM64</span></span>  | <span data-ttu-id="d037f-156">ARM64 systemu Linux</span><span class="sxs-lookup"><span data-stu-id="d037f-156">Linux ARM64</span></span> |
| <span data-ttu-id="d037f-157">macOS x64</span><span class="sxs-lookup"><span data-stu-id="d037f-157">macOS X64</span></span>    | <span data-ttu-id="d037f-158">macOS x64</span><span class="sxs-lookup"><span data-stu-id="d037f-158">macOS X64</span></span> |
