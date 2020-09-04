---
title: Ewolucja platformy .NET Core do platformy .NET 5
description: Dowiedz się więcej na temat platformy .NET 5 — platformy deweloperskiej obejmującej wiele platform i typu "open source", która jest kolejną ewolucją platformy .NET Core.
ms.date: 09/02/2020
ms.topic: overview
ms.author: dapine
author: IEvangelist
ms.openlocfilehash: f9fd0d09dbb65c2367ac268ea4a7055a299a7586
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89471990"
---
# <a name="the-evolution-of-net-core-to-net-5"></a><span data-ttu-id="2c41c-103">Ewolucja platformy .NET Core do platformy .NET 5</span><span class="sxs-lookup"><span data-stu-id="2c41c-103">The evolution of .NET Core to .NET 5</span></span>

<span data-ttu-id="2c41c-104">W tym artykule szczegółowo opisano, co obejmuje platforma .NET 5, która jest następną wersją programu .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="2c41c-104">This article details what is included in .NET 5, which is the next release of .NET Core following 3.1.</span></span> <span data-ttu-id="2c41c-105">Numer wersji to 5,0, aby uniknąć nieporozumień przy użyciu .NET Framework 4. x.</span><span class="sxs-lookup"><span data-stu-id="2c41c-105">The version number is 5.0 to avoid confusion with .NET Framework 4.x.</span></span> <span data-ttu-id="2c41c-106">I "rdzeń" został porzucony z nazwy, ponieważ jest to główna implementacja platformy .NET do przodu.</span><span class="sxs-lookup"><span data-stu-id="2c41c-106">And "Core" is dropped from the name because it is the main implementation of .NET going forward.</span></span> <span data-ttu-id="2c41c-107">Platforma .NET 5 obsługuje więcej typów aplikacji i więcej platform niż .NET Core lub .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2c41c-107">.NET 5 supports more types of apps and more platforms than .NET Core or .NET Framework.</span></span>

<span data-ttu-id="2c41c-108">Pojawieniu platformy .NET Core rozwinęły ekosystem platformy .NET w atrakcyjny sposób.</span><span class="sxs-lookup"><span data-stu-id="2c41c-108">The advent of .NET Core has evolved the .NET ecosystem in compelling ways.</span></span> <span data-ttu-id="2c41c-109">Zostało ono dojrzałe jako projekt Open Source w witrynie GitHub, świętujemy wkłady społecznościowe i humbly ulepszenie w miarę upływu czasu.</span><span class="sxs-lookup"><span data-stu-id="2c41c-109">It matured as an open-source project on GitHub, celebrating community contributions, and humbly improving over time.</span></span>

<span data-ttu-id="2c41c-110">Platforma .NET Core ma kilka podstawowych cech:</span><span class="sxs-lookup"><span data-stu-id="2c41c-110">.NET Core has several primary characteristics:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="2c41c-111">Wiele platform</span><span class="sxs-lookup"><span data-stu-id="2c41c-111">Cross-platform</span></span>
> - <span data-ttu-id="2c41c-112">Open source</span><span class="sxs-lookup"><span data-stu-id="2c41c-112">Open-source</span></span>
> - <span data-ttu-id="2c41c-113">Instalacja równoczesna</span><span class="sxs-lookup"><span data-stu-id="2c41c-113">Side-by-side installation</span></span>
> - <span data-ttu-id="2c41c-114">Małe pliki projektu (zestaw SDK)</span><span class="sxs-lookup"><span data-stu-id="2c41c-114">Small project files (SDK-style)</span></span>
> - <span data-ttu-id="2c41c-115">Elastyczne wdrażanie</span><span class="sxs-lookup"><span data-stu-id="2c41c-115">Flexible deployment</span></span>

<span data-ttu-id="2c41c-116">Platforma .NET 5 rozszerza te charakterystyki, wprowadzając przyrostowe ulepszenia:</span><span class="sxs-lookup"><span data-stu-id="2c41c-116">.NET 5 extends these characteristics, making incremental improvements:</span></span>

- <span data-ttu-id="2c41c-117">Aplikacje pojedynczego pliku</span><span class="sxs-lookup"><span data-stu-id="2c41c-117">Single file apps</span></span>
- <span data-ttu-id="2c41c-118">ARM64 z systemami Windows i ARM64</span><span class="sxs-lookup"><span data-stu-id="2c41c-118">Windows ARM64, and ARM64 intrinsics</span></span>
- <span data-ttu-id="2c41c-119">Udoskonalenia wydajności w celu:</span><span class="sxs-lookup"><span data-stu-id="2c41c-119">Sweeping performance improvements to:</span></span>
  - [<span data-ttu-id="2c41c-120">Odzyskiwanie pamięci (GC)</span><span class="sxs-lookup"><span data-stu-id="2c41c-120">Garbage Collection (GC)</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#gc)
  - [<span data-ttu-id="2c41c-121">System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="2c41c-121">System.Text.Json</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#json)
  - [<span data-ttu-id="2c41c-122">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="2c41c-122">System.Text.RegularExpressions</span></span>](https://devblogs.microsoft.com/dotnet/regex-performance-improvements-in-net-5)
  - [<span data-ttu-id="2c41c-123">Asynchroniczne buforowanie ValueTask</span><span class="sxs-lookup"><span data-stu-id="2c41c-123">Async ValueTask pooling</span></span>](https://devblogs.microsoft.com/dotnet/async-valuetask-pooling-in-net-5)
  - [<span data-ttu-id="2c41c-124">Wiele więcej obszarów</span><span class="sxs-lookup"><span data-stu-id="2c41c-124">Many more areas</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)
- <span data-ttu-id="2c41c-125">Optymalizacje rozmiaru kontenera</span><span class="sxs-lookup"><span data-stu-id="2c41c-125">Container size optimizations</span></span>
- [<span data-ttu-id="2c41c-126">Przycinanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="2c41c-126">App trimming</span></span>](https://devblogs.microsoft.com/dotnet/app-trimming-in-net-5)
- [<span data-ttu-id="2c41c-127">Udoskonalenia kompilatora języka C#</span><span class="sxs-lookup"><span data-stu-id="2c41c-127">C# compiler enhancements</span></span>](https://devblogs.microsoft.com/dotnet/automatically-find-latent-bugs-in-your-code-with-net-5)
- <span data-ttu-id="2c41c-128">Narzędzia obsługujące debugowanie zrzutów</span><span class="sxs-lookup"><span data-stu-id="2c41c-128">Tooling support for dump debugging</span></span>
- <span data-ttu-id="2c41c-129">Platforma to 80% adnotacji dla [typów referencyjnych dopuszczających wartości null](csharp/nullable-references.md)</span><span class="sxs-lookup"><span data-stu-id="2c41c-129">Platform is 80% annotated for [nullable reference types](csharp/nullable-references.md)</span></span>

### <a name="what-net-5-is-not"></a><span data-ttu-id="2c41c-130">Co to jest platforma .NET 5</span><span class="sxs-lookup"><span data-stu-id="2c41c-130">What .NET 5 is not</span></span>

<span data-ttu-id="2c41c-131">Platforma .NET 5 nie zastępuje .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2c41c-131">.NET 5 is not a replacement for .NET Framework.</span></span> <span data-ttu-id="2c41c-132">Nie istnieją plany dotyczące portów następujących technologii z .NET Framework do platformy .NET 5, ale istnieją obsługiwane alternatywy zawarte w programie .NET 5:</span><span class="sxs-lookup"><span data-stu-id="2c41c-132">There are no plans to port the following technologies from .NET Framework to .NET 5, but there are supported alternatives included in .NET 5:</span></span>

| <span data-ttu-id="2c41c-133">Technologia</span><span class="sxs-lookup"><span data-stu-id="2c41c-133">Technology</span></span>                             | <span data-ttu-id="2c41c-134">Zalecenie</span><span class="sxs-lookup"><span data-stu-id="2c41c-134">Recommendation</span></span>                                              |
|----------------------------------------|-------------------------------------------------------------|
| <span data-ttu-id="2c41c-135">Formularze sieci Web</span><span class="sxs-lookup"><span data-stu-id="2c41c-135">Web Forms</span></span>                              | [<span data-ttu-id="2c41c-136">ASP.NET Core Blazor</span><span class="sxs-lookup"><span data-stu-id="2c41c-136">ASP.NET Core Blazor</span></span>](/aspnet/core/blazor)                  |
| <span data-ttu-id="2c41c-137">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="2c41c-137">Windows Communication Foundation (WCF)</span></span> | [<span data-ttu-id="2c41c-138">gRPC</span><span class="sxs-lookup"><span data-stu-id="2c41c-138">gRPC</span></span>](/aspnet/core/grpc)                                   |
| <span data-ttu-id="2c41c-139">Windows Workflow (WF)</span><span class="sxs-lookup"><span data-stu-id="2c41c-139">Windows Workflow (WF)</span></span>                  | [<span data-ttu-id="2c41c-140">CoreWF "open source"</span><span class="sxs-lookup"><span data-stu-id="2c41c-140">Open-source CoreWF</span></span>](https://github.com/UiPath-Open/corewf) |

## <a name="net-standard"></a><span data-ttu-id="2c41c-141">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="2c41c-141">.NET Standard</span></span>

<span data-ttu-id="2c41c-142">Nowe opracowywanie aplikacji może określać `net5.0` moniker platformy docelowej (TFM) dla wszystkich typów projektów, w tym biblioteki klas.</span><span class="sxs-lookup"><span data-stu-id="2c41c-142">New application development can specify the `net5.0` target framework moniker (TFM) for all project types, including class libraries.</span></span> <span data-ttu-id="2c41c-143">Udostępnianie kodu między obciążeniami programu .NET 5 jest uproszczone w tym, że wszystko, co jest potrzebne, to `net5.0` TFM.</span><span class="sxs-lookup"><span data-stu-id="2c41c-143">Sharing code between .NET 5 workloads is simplified in that all you need is the `net5.0` TFM.</span></span>

<span data-ttu-id="2c41c-144">`net5.0`TFM łączy i zastępuje `netcoreapp` `netstandard` nazwy.</span><span class="sxs-lookup"><span data-stu-id="2c41c-144">The `net5.0` TFM combines and replaces `netcoreapp` and `netstandard` names.</span></span> <span data-ttu-id="2c41c-145">Ta TFM zazwyczaj obejmuje tylko technologie, które działają na wielu platformach, takich jak .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="2c41c-145">This TFM will generally only include technologies that work cross-platform, like was done with .NET Standard.</span></span> <span data-ttu-id="2c41c-146">Jeśli jednak planujesz udostępnianie kodu między obciążeniami .NET Framework, .NET Core i .NET 5 — możesz to zrobić, określając `netstandard2.0` jako TFM.</span><span class="sxs-lookup"><span data-stu-id="2c41c-146">However, if you're planning on sharing code between .NET Framework, .NET Core, and .NET 5 workloads - you can do so by specifying `netstandard2.0` as your TFM.</span></span> <span data-ttu-id="2c41c-147">Aby uzyskać więcej informacji, zobacz [jak określić Platformy docelowe](standard/frameworks.md#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="2c41c-147">For more information, see [How to specify target frameworks](standard/frameworks.md#how-to-specify-target-frameworks).</span></span>

## <a name="language-updates"></a><span data-ttu-id="2c41c-148">Aktualizacje języka</span><span class="sxs-lookup"><span data-stu-id="2c41c-148">Language updates</span></span>

<span data-ttu-id="2c41c-149">W przypadku platformy .NET 5 Języki programowania .NET są kontynuowane.</span><span class="sxs-lookup"><span data-stu-id="2c41c-149">With .NET 5, the .NET programming languages are continuing to improve.</span></span>

### <a name="c-updates"></a><span data-ttu-id="2c41c-150">Aktualizacje w języku C#</span><span class="sxs-lookup"><span data-stu-id="2c41c-150">C# updates</span></span>

<span data-ttu-id="2c41c-151">Deweloperzy piszący aplikacje .NET 5 będą mieli dostęp do najnowszej wersji i funkcji języka C#.</span><span class="sxs-lookup"><span data-stu-id="2c41c-151">Developers writing .NET 5 apps will have access to the latest C# version and features.</span></span> <span data-ttu-id="2c41c-152">Program .NET 5 jest sparowany z językiem C# 9.</span><span class="sxs-lookup"><span data-stu-id="2c41c-152">.NET 5 is paired with C# 9.</span></span> <span data-ttu-id="2c41c-153">W języku C# 9 wprowadzono wiele nowych funkcji, które są następujące:</span><span class="sxs-lookup"><span data-stu-id="2c41c-153">C# 9 brings many new features to the language, here are a few highlights:</span></span>

- <span data-ttu-id="2c41c-154">Rekordy: niezmienne typy odwołań, które zachowują się jak typy wartości, i wprowadzają nowe `with` słowo kluczowe do języka.</span><span class="sxs-lookup"><span data-stu-id="2c41c-154">Records: Immutable reference types that behave like value types, and introduce the new `with` keyword into the language.</span></span>
- <span data-ttu-id="2c41c-155">Dopasowywanie do wzorca relacyjnego: rozszerza możliwości dopasowania wzorców do operatorów relacyjnych dla obliczeń porównawczych i wyrażeń, w tym wzorców logicznych — nowe słowa kluczowe `and` , `or` i `not` .</span><span class="sxs-lookup"><span data-stu-id="2c41c-155">Relational pattern matching: Extends pattern matching capabilities to relational operators for comparative evaluations and expressions, including logical patterns - new keywords `and`, `or`, and `not`.</span></span>
- <span data-ttu-id="2c41c-156">Instrukcje najwyższego poziomu: jako metody przyspieszania wdrażania i uczenia się języka C#, `Main` Metoda może zostać pominięta, a aplikacja jako prosta jest prawidłowa:</span><span class="sxs-lookup"><span data-stu-id="2c41c-156">Top-level statements: As a means for accelerating adoption and learning of C#, the `Main` method can be omitted and application as simple as the following is valid:</span></span>

   ```csharp
   System.Console.Write("Hello world!");
   ```

- <span data-ttu-id="2c41c-157">Wskaźniki funkcjonalne: konstrukcje języka, które uwidaczniają język pośredni (IL) następujące kod kodów `ldftn` i `calli` .</span><span class="sxs-lookup"><span data-stu-id="2c41c-157">Functional pointers: Language constructs that expose intermediate language (IL) the following opcodes `ldftn` and `calli`.</span></span>

<span data-ttu-id="2c41c-158">Aby uzyskać więcej informacji na temat dostępnych funkcji języka C# 9, zobacz [co nowego w języku c# 9](csharp/whats-new/csharp-9.md).</span><span class="sxs-lookup"><span data-stu-id="2c41c-158">For more information on the available C# 9 features, see [What's new in C# 9](csharp/whats-new/csharp-9.md).</span></span>

#### <a name="source-generators"></a><span data-ttu-id="2c41c-159">Generatory źródeł</span><span class="sxs-lookup"><span data-stu-id="2c41c-159">Source generators</span></span>

<span data-ttu-id="2c41c-160">Oprócz niektórych wyróżnionych nowych funkcji języka C#, generatory źródeł są gotowe do projektów deweloperskich.</span><span class="sxs-lookup"><span data-stu-id="2c41c-160">In addition to some of the highlighted new C# features, source generators are making their way into developer projects.</span></span> <span data-ttu-id="2c41c-161">Generatory źródła umożliwiają kod, który jest uruchamiany podczas kompilacji w celu sprawdzenia programu i tworzenia dodatkowych plików, które są kompilowane razem z resztą kodu.</span><span class="sxs-lookup"><span data-stu-id="2c41c-161">Source generators allow code that runs during compilation to inspect your program and produce additional files that are compiled together with the rest of your code.</span></span>

<span data-ttu-id="2c41c-162">Aby uzyskać więcej informacji na temat generatorów źródeł, zobacz [wprowadzenie do źródłowych generatorów języka c#](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) i [próbek generatora źródła c#](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).</span><span class="sxs-lookup"><span data-stu-id="2c41c-162">For more information on source generators, see [Introducing C# source generators](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) and [C# source generator samples](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).</span></span>

### <a name="f-updates"></a><span data-ttu-id="2c41c-163">Aktualizacje języka F #</span><span class="sxs-lookup"><span data-stu-id="2c41c-163">F# updates</span></span>

<span data-ttu-id="2c41c-164">F # to język programowania funkcjonalny .NET, a w przypadku platformy .NET 5 deweloperzy mają dostęp do programu F # 5.</span><span class="sxs-lookup"><span data-stu-id="2c41c-164">F# is the .NET functional programming language, and with .NET 5, developers have access to F# 5.</span></span> <span data-ttu-id="2c41c-165">Oto kilka nowych funkcji języka F # 5:</span><span class="sxs-lookup"><span data-stu-id="2c41c-165">Here are several new features of F# 5:</span></span>

#### <a name="interpolated-strings"></a><span data-ttu-id="2c41c-166">Ciągi interpolowane</span><span class="sxs-lookup"><span data-stu-id="2c41c-166">Interpolated strings</span></span>

<span data-ttu-id="2c41c-167">Podobnie jak ciąg interpolowany w języku C#, a nawet JavaScript-F # obsługuje interpolację ciągów podstawowych.</span><span class="sxs-lookup"><span data-stu-id="2c41c-167">Similar to interpolated string in C#, and even JavaScript - F# supports basic string interpolation.</span></span>

```fsharp
let name = "David"
let age = 36
let message = $"{name} is {age} years old."
```

<span data-ttu-id="2c41c-168">Oprócz podstawowej interpolacji ciągów jest wpisana Interpolacja.</span><span class="sxs-lookup"><span data-stu-id="2c41c-168">In addition to basic string interpolation, there is typed interpolation.</span></span> <span data-ttu-id="2c41c-169">Po wpisaniu interpolacji, dany typ musi być zgodny ze specyfikatorem formatu.</span><span class="sxs-lookup"><span data-stu-id="2c41c-169">With typed interpolation, a given type must match the format specifier.</span></span>

```fsharp
let name = "David"
let age = 36
let message = $"%s{name} is %d{age} years old."
```

<span data-ttu-id="2c41c-170">Jest to podobne do [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) funkcji, która formatuje ciąg w oparciu o dane wejściowe bezpieczne dla typów.</span><span class="sxs-lookup"><span data-stu-id="2c41c-170">This is similar to the [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) function that formats a string based on type-safe inputs.</span></span> <span data-ttu-id="2c41c-171">Aby uzyskać więcej informacji, zobacz [co nowego w języku F # 5](fsharp/whats-new/fsharp-50.md)</span><span class="sxs-lookup"><span data-stu-id="2c41c-171">For more information, see [What's new in F# 5](fsharp/whats-new/fsharp-50.md)</span></span>

### <a name="visual-basic-updates"></a><span data-ttu-id="2c41c-172">Aktualizacje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c41c-172">Visual Basic updates</span></span>

<span data-ttu-id="2c41c-173">Nie ma nowych funkcji języka dla Visual Basic w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="2c41c-173">There are no new language features for Visual Basic in .NET 5.</span></span> <span data-ttu-id="2c41c-174">Jednak w przypadku platformy .NET 5 obsługa Visual Basic została rozszerzona o następujące:</span><span class="sxs-lookup"><span data-stu-id="2c41c-174">However, with .NET 5, Visual Basic support is extended to:</span></span>

| <span data-ttu-id="2c41c-175">Opis</span><span class="sxs-lookup"><span data-stu-id="2c41c-175">Description</span></span>                            | <span data-ttu-id="2c41c-176">`dotnet new` konstruktora</span><span class="sxs-lookup"><span data-stu-id="2c41c-176">`dotnet new` parameter</span></span> |
|----------------------------------------|------------------------|
| <span data-ttu-id="2c41c-177">Aplikacja konsoli</span><span class="sxs-lookup"><span data-stu-id="2c41c-177">Console Application</span></span>                    | `console`              |
| <span data-ttu-id="2c41c-178">Biblioteka klas</span><span class="sxs-lookup"><span data-stu-id="2c41c-178">Class library</span></span>                          | `classlib`             |
| <span data-ttu-id="2c41c-179">Aplikacja WPF</span><span class="sxs-lookup"><span data-stu-id="2c41c-179">WPF Application</span></span>                        | `wpf`                  |
| <span data-ttu-id="2c41c-180">Biblioteka klas WPF</span><span class="sxs-lookup"><span data-stu-id="2c41c-180">WPF Class library</span></span>                      | `wpflib`               |
| <span data-ttu-id="2c41c-181">Biblioteka kontrolek niestandardowych WPF</span><span class="sxs-lookup"><span data-stu-id="2c41c-181">WPF Custom Control Library</span></span>             | `wpfcustomcontrollib`  |
| <span data-ttu-id="2c41c-182">Biblioteka kontrolek użytkownika WPF</span><span class="sxs-lookup"><span data-stu-id="2c41c-182">WPF User Control Library</span></span>               | `wpfusercontrollib`    |
| <span data-ttu-id="2c41c-183">Aplikacja Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="2c41c-183">Windows Forms (WinForms) Application</span></span>   | `winforms`             |
| <span data-ttu-id="2c41c-184">Biblioteka klas Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="2c41c-184">Windows Forms (WinForms) Class library</span></span> | `winformslib`          |
| <span data-ttu-id="2c41c-185">Projekt testu jednostkowego</span><span class="sxs-lookup"><span data-stu-id="2c41c-185">Unit Test Project</span></span>                      | `mstest`               |
| <span data-ttu-id="2c41c-186">Projekt testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="2c41c-186">NUnit 3 Test Project</span></span>                   | `nunit`                |
| <span data-ttu-id="2c41c-187">Element testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="2c41c-187">NUnit 3 Test Item</span></span>                      | `nunit-test`           |
| <span data-ttu-id="2c41c-188">Projekt testu xUnit</span><span class="sxs-lookup"><span data-stu-id="2c41c-188">xUnit Test Project</span></span>                     | `xunit`                |

<span data-ttu-id="2c41c-189">Aby uzyskać więcej informacji na temat szablonów projektów z interfejsu wiersza polecenia platformy .NET, zobacz [`dotnet new`](core/tools/dotnet-new.md) .</span><span class="sxs-lookup"><span data-stu-id="2c41c-189">For more information on project templates from the .NET CLI, see [`dotnet new`](core/tools/dotnet-new.md).</span></span>

## <a name="net-maui"></a><span data-ttu-id="2c41c-190">MAUI .NET</span><span class="sxs-lookup"><span data-stu-id="2c41c-190">.NET MAUI</span></span>

<span data-ttu-id="2c41c-191">.NET MAUI to ewolucja coraz większego popularnego zestawu narzędzi Xamarin. Forms i jest typu open source w witrynie GitHub na platformie [dotnet/Maui](https://github.com/dotnet/maui).</span><span class="sxs-lookup"><span data-stu-id="2c41c-191">.NET MAUI is an evolution of the increasingly popular Xamarin.Forms toolkit, and is open-source on GitHub at [dotnet/maui](https://github.com/dotnet/maui).</span></span> <span data-ttu-id="2c41c-192">W przypadku programu .NET MAUI wybór dla deweloperów platformy .NET jest uproszczony, zapewniając pojedynczy stos obsługujący wszystkie nowoczesne obciążenia: Android, iOS, macOS i Windows.</span><span class="sxs-lookup"><span data-stu-id="2c41c-192">With .NET MAUI, the choice for .NET developers is simplified, providing a single stack that supports all modern workloads: Android, iOS, macOS, and Windows.</span></span> <span data-ttu-id="2c41c-193">Za pomocą programu .NET MAUI uzyskasz jeden środowisko dewelopera projektu, które jest przeznaczone dla wielu platform i urządzeń.</span><span class="sxs-lookup"><span data-stu-id="2c41c-193">With .NET MAUI, you get a single project developer experience that targets multiple platforms and devices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c41c-194">Program .NET MAUI jest w wczesnej wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="2c41c-194">.NET MAUI is in early preview.</span></span> <span data-ttu-id="2c41c-195">Przykładowy kod źródłowy można znaleźć na platformie [Xamarin/net6-Samples](https://github.com/xamarin/net6-samples).</span><span class="sxs-lookup"><span data-stu-id="2c41c-195">Sample source code can be found at [xamarin/net6-samples](https://github.com/xamarin/net6-samples).</span></span>

### <a name="model-view-update-pattern"></a><span data-ttu-id="2c41c-196">Model-View-Update — wzorzec</span><span class="sxs-lookup"><span data-stu-id="2c41c-196">Model-View-Update pattern</span></span>

<span data-ttu-id="2c41c-197">Deweloperzy lubią nowoczesne wzorce projektowania.</span><span class="sxs-lookup"><span data-stu-id="2c41c-197">Developers love modern development patterns.</span></span> <span data-ttu-id="2c41c-198">Podejście do tworzenia interfejsu użytkownika, które jest inspirowane "architekturą Elm", jest wzorcem [Model-View-Update](https://elmprogramming.com/model-view-update-part-1.html) lub MVU.</span><span class="sxs-lookup"><span data-stu-id="2c41c-198">A fluent approach to UI development, inspired by "The Elm Architecture" is the [model-view-update](https://elmprogramming.com/model-view-update-part-1.html) or MVU pattern.</span></span> <span data-ttu-id="2c41c-199">MVU promuje jednokierunkową przepływ zarządzania danymi i Stanami, a także środowisko programistyczne, które szybko aktualizuje interfejs użytkownika, stosując tylko te zmiany.</span><span class="sxs-lookup"><span data-stu-id="2c41c-199">MVU promotes a one-way flow of data and state management, as well as a code-first development experience that rapidly updates the UI by applying only the changes necessary.</span></span>

<span data-ttu-id="2c41c-200">Na przykład rozważmy następujący licznik zapisany w programie .NET MAUI przy użyciu wzorca MVU:</span><span class="sxs-lookup"><span data-stu-id="2c41c-200">As an example, consider the following counter written in .NET MAUI using the MVU pattern:</span></span>

```csharp
readonly State<int> _count = 0;

[Body]
View body() => new StackLayout
{
    new Label("Welcome to .NET MAUI!"),
    new Button(
        () => $"You clicked {_count} times.",
        () => ++ _count.Value)
    )
};
```

<span data-ttu-id="2c41c-201">Aby uzyskać więcej informacji, zobacz [plan .NET Maui](https://github.com/dotnet/maui/wiki/Roadmap)i wprowadzenie do artykułu [.NET Maui](https://devblogs.microsoft.com/dotnet/introducing-net-multi-platform-app-ui) .</span><span class="sxs-lookup"><span data-stu-id="2c41c-201">For more information, see the [.NET MAUI roadmap](https://github.com/dotnet/maui/wiki/Roadmap), and [Introducing .NET MAUI](https://devblogs.microsoft.com/dotnet/introducing-net-multi-platform-app-ui) article.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c41c-202">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2c41c-202">See also</span></span>

- [<span data-ttu-id="2c41c-203">Podróż do jednego programu .NET</span><span class="sxs-lookup"><span data-stu-id="2c41c-203">The Journey to one .NET</span></span>](https://channel9.msdn.com/Events/Build/2020/BOD106)
- [<span data-ttu-id="2c41c-204">Ulepszenia wydajności w programie .NET 5</span><span class="sxs-lookup"><span data-stu-id="2c41c-204">Performance improvements in .NET 5</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)
