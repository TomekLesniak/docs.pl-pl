---
title: Co nowego w programie .NET 5
description: Dowiedz się więcej na temat platformy .NET 5 — platformy deweloperskiej obejmującej wiele platform i typu "open source", która jest kolejną ewolucją platformy .NET Core.
ms.date: 09/02/2020
ms.topic: overview
ms.author: dapine
author: IEvangelist
ms.openlocfilehash: 9d4fc514c9de7a668f909286f10d6fe28ada7f90
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955205"
---
# <a name="whats-new-in-net-5"></a><span data-ttu-id="657f2-103">Co nowego w programie .NET 5</span><span class="sxs-lookup"><span data-stu-id="657f2-103">What's new in .NET 5</span></span>

<span data-ttu-id="657f2-104">.NET 5 to ewolucja platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="657f2-104">.NET 5 is the evolution of .NET Core.</span></span> <span data-ttu-id="657f2-105">W tym artykule przedstawiono szczegółowe informacje zawarte w programie .NET 5, który jest następną wersją programu .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="657f2-105">This article details what's included in .NET 5, which is the next release of .NET Core following 3.1.</span></span> <span data-ttu-id="657f2-106">Numer wersji to 5,0, aby uniknąć nieporozumień przy użyciu .NET Framework 4. x.</span><span class="sxs-lookup"><span data-stu-id="657f2-106">The version number is 5.0 to avoid confusion with .NET Framework 4.x.</span></span> <span data-ttu-id="657f2-107">I "rdzeń" został porzucony z nazwy, ponieważ jest to główna implementacja platformy .NET do przodu.</span><span class="sxs-lookup"><span data-stu-id="657f2-107">And "Core" is dropped from the name because it is the main implementation of .NET going forward.</span></span> <span data-ttu-id="657f2-108">ASP.NET Core zachowuje nazwę "rdzeń", aby uniknąć pomyłki z ASP.NET MVC 5.</span><span class="sxs-lookup"><span data-stu-id="657f2-108">ASP.NET Core retains the name "Core" to avoid confusing it with ASP.NET MVC 5.</span></span> <span data-ttu-id="657f2-109">Ponadto Entity Framework Core zachowuje nazwę "rdzeń", aby uniknąć pomyłki z Entity Framework 5 i 6.</span><span class="sxs-lookup"><span data-stu-id="657f2-109">Additionally, Entity Framework Core retains the name "Core" to avoid confusing it with Entity Framework 5 and 6.</span></span> <span data-ttu-id="657f2-110">Platforma .NET 5 obsługuje więcej typów aplikacji i więcej platform niż .NET Core lub .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="657f2-110">.NET 5 supports more types of apps and more platforms than .NET Core or .NET Framework.</span></span>

<span data-ttu-id="657f2-111">Pojawieniu platformy .NET Core rozwinęły ekosystem platformy .NET w atrakcyjny sposób.</span><span class="sxs-lookup"><span data-stu-id="657f2-111">The advent of .NET Core has evolved the .NET ecosystem in compelling ways.</span></span> <span data-ttu-id="657f2-112">Zostało ono dojrzałe jako projekt Open Source w witrynie GitHub, świętujemy wkłady społecznościowe i humbly ulepszenie w miarę upływu czasu.</span><span class="sxs-lookup"><span data-stu-id="657f2-112">It matured as an open-source project on GitHub, celebrating community contributions, and humbly improving over time.</span></span>

<span data-ttu-id="657f2-113">Platforma .NET Core ma kilka podstawowych cech:</span><span class="sxs-lookup"><span data-stu-id="657f2-113">.NET Core has several primary characteristics:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="657f2-114">Wiele platform</span><span class="sxs-lookup"><span data-stu-id="657f2-114">Cross-platform</span></span>
> - <span data-ttu-id="657f2-115">Open source</span><span class="sxs-lookup"><span data-stu-id="657f2-115">Open-source</span></span>
> - <span data-ttu-id="657f2-116">Instalacja równoczesna</span><span class="sxs-lookup"><span data-stu-id="657f2-116">Side-by-side installation</span></span>
> - <span data-ttu-id="657f2-117">Małe pliki projektu (zestaw SDK)</span><span class="sxs-lookup"><span data-stu-id="657f2-117">Small project files (SDK-style)</span></span>
> - <span data-ttu-id="657f2-118">Elastyczne wdrażanie</span><span class="sxs-lookup"><span data-stu-id="657f2-118">Flexible deployment</span></span>

<span data-ttu-id="657f2-119">Platforma .NET 5 rozszerza te charakterystyki, wprowadzając przyrostowe ulepszenia:</span><span class="sxs-lookup"><span data-stu-id="657f2-119">.NET 5 extends these characteristics, making incremental improvements:</span></span>

- <span data-ttu-id="657f2-120">Aplikacje pojedynczego pliku</span><span class="sxs-lookup"><span data-stu-id="657f2-120">Single file apps</span></span>
- <span data-ttu-id="657f2-121">Funkcje wewnętrzne ARM64 i ARM64 systemu Windows</span><span class="sxs-lookup"><span data-stu-id="657f2-121">Windows ARM64 and ARM64 intrinsics</span></span>
- <span data-ttu-id="657f2-122">Udoskonalenia wydajności w celu:</span><span class="sxs-lookup"><span data-stu-id="657f2-122">Sweeping performance improvements to:</span></span>
  - [<span data-ttu-id="657f2-123">Odzyskiwanie pamięci (GC)</span><span class="sxs-lookup"><span data-stu-id="657f2-123">Garbage Collection (GC)</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#gc)
  - [<span data-ttu-id="657f2-124">System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="657f2-124">System.Text.Json</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#json)
  - [<span data-ttu-id="657f2-125">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="657f2-125">System.Text.RegularExpressions</span></span>](https://devblogs.microsoft.com/dotnet/regex-performance-improvements-in-net-5)
  - [<span data-ttu-id="657f2-126">Asynchroniczne buforowanie ValueTask</span><span class="sxs-lookup"><span data-stu-id="657f2-126">Async ValueTask pooling</span></span>](https://devblogs.microsoft.com/dotnet/async-valuetask-pooling-in-net-5)
  - [<span data-ttu-id="657f2-127">Wiele więcej obszarów</span><span class="sxs-lookup"><span data-stu-id="657f2-127">Many more areas</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)
- <span data-ttu-id="657f2-128">Optymalizacje rozmiaru kontenera</span><span class="sxs-lookup"><span data-stu-id="657f2-128">Container size optimizations</span></span>
- [<span data-ttu-id="657f2-129">Przycinanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="657f2-129">App trimming</span></span>](https://devblogs.microsoft.com/dotnet/app-trimming-in-net-5)
- [<span data-ttu-id="657f2-130">Udoskonalenia kompilatora języka C#</span><span class="sxs-lookup"><span data-stu-id="657f2-130">C# compiler enhancements</span></span>](https://devblogs.microsoft.com/dotnet/automatically-find-latent-bugs-in-your-code-with-net-5)
- <span data-ttu-id="657f2-131">Narzędzia obsługujące debugowanie zrzutów</span><span class="sxs-lookup"><span data-stu-id="657f2-131">Tooling support for dump debugging</span></span>
- <span data-ttu-id="657f2-132">Platforma to 80% adnotacji dla [typów referencyjnych dopuszczających wartości null](../csharp/nullable-references.md)</span><span class="sxs-lookup"><span data-stu-id="657f2-132">Platform is 80% annotated for [nullable reference types](../csharp/nullable-references.md)</span></span>

### <a name="what-net-5-is-not"></a><span data-ttu-id="657f2-133">Co to jest platforma .NET 5</span><span class="sxs-lookup"><span data-stu-id="657f2-133">What .NET 5 is not</span></span>

<span data-ttu-id="657f2-134">Platforma .NET 5 nie jest kompletną wymianą dla .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="657f2-134">.NET 5 is not a complete replacement for .NET Framework.</span></span> <span data-ttu-id="657f2-135">Nie istnieją plany dotyczące portów następujących technologii z .NET Framework do platformy .NET 5, ale istnieją obsługiwane alternatywy:</span><span class="sxs-lookup"><span data-stu-id="657f2-135">There are no plans to port the following technologies from .NET Framework to .NET 5, but there are supported alternatives:</span></span>

| <span data-ttu-id="657f2-136">Technologia</span><span class="sxs-lookup"><span data-stu-id="657f2-136">Technology</span></span>                             | <span data-ttu-id="657f2-137">Zalecana alternatywa</span><span class="sxs-lookup"><span data-stu-id="657f2-137">Recommended alternative</span></span>                                                                         |
|----------------------------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="657f2-138">Formularze sieci Web</span><span class="sxs-lookup"><span data-stu-id="657f2-138">Web Forms</span></span>                              | <span data-ttu-id="657f2-139">ASP.NET Core [Blazor](/aspnet/core/blazor) lub [Razor Pages](/aspnet/core/tutorials/razor-pages)</span><span class="sxs-lookup"><span data-stu-id="657f2-139">ASP.NET Core [Blazor](/aspnet/core/blazor) or [Razor Pages](/aspnet/core/tutorials/razor-pages)</span></span> |
| <span data-ttu-id="657f2-140">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="657f2-140">Windows Communication Foundation (WCF)</span></span> | [<span data-ttu-id="657f2-141">gRPC</span><span class="sxs-lookup"><span data-stu-id="657f2-141">gRPC</span></span>](/aspnet/core/grpc)                                                                       |
| <span data-ttu-id="657f2-142">Windows Workflow (WF)</span><span class="sxs-lookup"><span data-stu-id="657f2-142">Windows Workflow (WF)</span></span>                  | [<span data-ttu-id="657f2-143">CoreWF "open source"</span><span class="sxs-lookup"><span data-stu-id="657f2-143">Open-source CoreWF</span></span>](https://github.com/UiPath-Open/corewf)                                     |

## <a name="net-standard"></a><span data-ttu-id="657f2-144">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="657f2-144">.NET Standard</span></span>

<span data-ttu-id="657f2-145">Nowe opracowywanie aplikacji może określać `net5.0` moniker platformy docelowej (TFM) dla wszystkich typów projektów, w tym biblioteki klas.</span><span class="sxs-lookup"><span data-stu-id="657f2-145">New application development can specify the `net5.0` target framework moniker (TFM) for all project types, including class libraries.</span></span> <span data-ttu-id="657f2-146">Udostępnianie kodu między obciążeniami programu .NET 5 jest uproszczone w tym, że wszystko, co jest potrzebne, to `net5.0` TFM.</span><span class="sxs-lookup"><span data-stu-id="657f2-146">Sharing code between .NET 5 workloads is simplified in that all you need is the `net5.0` TFM.</span></span>

<span data-ttu-id="657f2-147">`net5.0`TFM łączy i zastępuje `netcoreapp` `netstandard` nazwy i.</span><span class="sxs-lookup"><span data-stu-id="657f2-147">The `net5.0` TFM combines and replaces the `netcoreapp` and `netstandard` names.</span></span> <span data-ttu-id="657f2-148">Ta TFM zazwyczaj obejmuje tylko technologie, które działają na wielu platformach, takich jak .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="657f2-148">This TFM will generally only include technologies that work cross-platform, like was done with .NET Standard.</span></span> <span data-ttu-id="657f2-149">Jeśli jednak planujesz udostępnianie kodu między obciążeniami .NET Framework, .NET Core i .NET 5, możesz to zrobić, określając `netstandard2.0` jako TFM.</span><span class="sxs-lookup"><span data-stu-id="657f2-149">However, if you plan to share code between .NET Framework, .NET Core, and .NET 5 workloads, you can do so by specifying `netstandard2.0` as your TFM.</span></span> <span data-ttu-id="657f2-150">Aby uzyskać więcej informacji, zobacz [jak określić Platformy docelowe](../standard/frameworks.md#how-to-specify-a-target-framework).</span><span class="sxs-lookup"><span data-stu-id="657f2-150">For more information, see [How to specify target frameworks](../standard/frameworks.md#how-to-specify-a-target-framework).</span></span>

## <a name="language-updates"></a><span data-ttu-id="657f2-151">Aktualizacje języka</span><span class="sxs-lookup"><span data-stu-id="657f2-151">Language updates</span></span>

<span data-ttu-id="657f2-152">W przypadku platformy .NET 5 Języki programowania .NET są kontynuowane.</span><span class="sxs-lookup"><span data-stu-id="657f2-152">With .NET 5, the .NET programming languages are continuing to improve.</span></span>

### <a name="c-updates"></a><span data-ttu-id="657f2-153">Aktualizacje w języku C#</span><span class="sxs-lookup"><span data-stu-id="657f2-153">C# updates</span></span>

<span data-ttu-id="657f2-154">Deweloperzy piszący aplikacje .NET 5 będą mieli dostęp do najnowszej wersji i funkcji języka C#.</span><span class="sxs-lookup"><span data-stu-id="657f2-154">Developers writing .NET 5 apps will have access to the latest C# version and features.</span></span> <span data-ttu-id="657f2-155">Program .NET 5 jest sparowany z językiem C# 9, który oferuje wiele nowych funkcji w języku.</span><span class="sxs-lookup"><span data-stu-id="657f2-155">.NET 5 is paired with C# 9, which brings many new features to the language.</span></span> <span data-ttu-id="657f2-156">Oto kilka świateł:</span><span class="sxs-lookup"><span data-stu-id="657f2-156">Here are a few highlights:</span></span>

- <span data-ttu-id="657f2-157">Rekordy: niezmienne typy odwołań, które zachowują się jak typy wartości, i wprowadzają nowe `with` słowo kluczowe do języka.</span><span class="sxs-lookup"><span data-stu-id="657f2-157">Records: Immutable reference types that behave like value types, and introduce the new `with` keyword into the language.</span></span>
- <span data-ttu-id="657f2-158">Dopasowywanie do wzorca relacyjnego: rozszerza możliwości dopasowania wzorców do operatorów relacyjnych dla obliczeń porównawczych i wyrażeń, w tym wzorców logicznych — nowe słowa kluczowe `and` , `or` i `not` .</span><span class="sxs-lookup"><span data-stu-id="657f2-158">Relational pattern matching: Extends pattern matching capabilities to relational operators for comparative evaluations and expressions, including logical patterns - new keywords `and`, `or`, and `not`.</span></span>
- <span data-ttu-id="657f2-159">Instrukcje najwyższego poziomu: jako metody przyspieszania wdrażania i uczenia się języka C#, `Main` Metoda może zostać pominięta, a aplikacja jako prosta jest prawidłowa:</span><span class="sxs-lookup"><span data-stu-id="657f2-159">Top-level statements: As a means for accelerating adoption and learning of C#, the `Main` method can be omitted and application as simple as the following is valid:</span></span>

   ```csharp
   System.Console.Write("Hello world!");
   ```

- <span data-ttu-id="657f2-160">Wskaźniki funkcji: konstrukcje języka, które uwidaczniają następujące kod w języku pośrednim (IL): `ldftn` i `calli` .</span><span class="sxs-lookup"><span data-stu-id="657f2-160">Function pointers: Language constructs that expose the following intermediate language (IL) opcodes: `ldftn` and `calli`.</span></span>

<span data-ttu-id="657f2-161">Aby uzyskać więcej informacji na temat dostępnych funkcji języka C# 9, zobacz [co nowego w języku c# 9](../csharp/whats-new/csharp-9.md).</span><span class="sxs-lookup"><span data-stu-id="657f2-161">For more information on the available C# 9 features, see [What's new in C# 9](../csharp/whats-new/csharp-9.md).</span></span>

#### <a name="source-generators"></a><span data-ttu-id="657f2-162">Generatory źródeł</span><span class="sxs-lookup"><span data-stu-id="657f2-162">Source generators</span></span>

<span data-ttu-id="657f2-163">Oprócz niektórych wyróżnionych nowych funkcji języka C#, generatory źródeł są gotowe do projektów deweloperskich.</span><span class="sxs-lookup"><span data-stu-id="657f2-163">In addition to some of the highlighted new C# features, source generators are making their way into developer projects.</span></span> <span data-ttu-id="657f2-164">Generatory źródła umożliwiają kod, który jest uruchamiany podczas kompilacji w celu sprawdzenia programu i tworzenia dodatkowych plików, które są kompilowane razem z resztą kodu.</span><span class="sxs-lookup"><span data-stu-id="657f2-164">Source generators allow code that runs during compilation to inspect your program and produce additional files that are compiled together with the rest of your code.</span></span>

<span data-ttu-id="657f2-165">Aby uzyskać więcej informacji na temat generatorów źródeł, zobacz [wprowadzenie do źródłowych generatorów języka c#](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) i [próbek generatora źródła c#](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).</span><span class="sxs-lookup"><span data-stu-id="657f2-165">For more information on source generators, see [Introducing C# source generators](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) and [C# source generator samples](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).</span></span>

### <a name="f-updates"></a><span data-ttu-id="657f2-166">Aktualizacje języka F #</span><span class="sxs-lookup"><span data-stu-id="657f2-166">F# updates</span></span>

<span data-ttu-id="657f2-167">F # to język programowania funkcjonalny .NET, a w przypadku platformy .NET 5 deweloperzy mają dostęp do programu F # 5.</span><span class="sxs-lookup"><span data-stu-id="657f2-167">F# is the .NET functional programming language, and with .NET 5, developers have access to F# 5.</span></span> <span data-ttu-id="657f2-168">Oto kilka nowych funkcji języka F # 5:</span><span class="sxs-lookup"><span data-stu-id="657f2-168">Here are several new features of F# 5:</span></span>

#### <a name="interpolated-strings"></a><span data-ttu-id="657f2-169">Ciągi interpolowane</span><span class="sxs-lookup"><span data-stu-id="657f2-169">Interpolated strings</span></span>

<span data-ttu-id="657f2-170">Podobnie jak ciąg interpolowany w języku C#, a nawet JavaScript, język F # obsługuje interpolację ciągów podstawowych.</span><span class="sxs-lookup"><span data-stu-id="657f2-170">Similar to interpolated string in C#, and even JavaScript, F# supports basic string interpolation.</span></span>

```fsharp
let name = "David"
let age = 36
let message = $"{name} is {age} years old."
```

<span data-ttu-id="657f2-171">Oprócz podstawowej interpolacji ciągów jest wpisana Interpolacja.</span><span class="sxs-lookup"><span data-stu-id="657f2-171">In addition to basic string interpolation, there is typed interpolation.</span></span> <span data-ttu-id="657f2-172">Po wpisaniu interpolacji, dany typ musi być zgodny ze specyfikatorem formatu.</span><span class="sxs-lookup"><span data-stu-id="657f2-172">With typed interpolation, a given type must match the format specifier.</span></span>

```fsharp
let name = "David"
let age = 36
let message = $"%s{name} is %d{age} years old."
```

<span data-ttu-id="657f2-173">Jest to podobne do [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) funkcji, która formatuje ciąg w oparciu o dane wejściowe bezpieczne dla typów.</span><span class="sxs-lookup"><span data-stu-id="657f2-173">This is similar to the [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) function that formats a string based on type-safe inputs.</span></span> <!-- For more information, see [What's new in F# 5](fsharp/whats-new/fsharp-50.md). -->

### <a name="visual-basic-updates"></a><span data-ttu-id="657f2-174">Aktualizacje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="657f2-174">Visual Basic updates</span></span>

<span data-ttu-id="657f2-175">Nie ma nowych funkcji języka dla Visual Basic w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="657f2-175">There are no new language features for Visual Basic in .NET 5.</span></span> <span data-ttu-id="657f2-176">Jednak w przypadku platformy .NET 5 obsługa Visual Basic została rozszerzona o następujące:</span><span class="sxs-lookup"><span data-stu-id="657f2-176">However, with .NET 5, Visual Basic support is extended to:</span></span>

| <span data-ttu-id="657f2-177">Opis</span><span class="sxs-lookup"><span data-stu-id="657f2-177">Description</span></span>                            | <span data-ttu-id="657f2-178">`dotnet new` konstruktora</span><span class="sxs-lookup"><span data-stu-id="657f2-178">`dotnet new` parameter</span></span> |
|----------------------------------------|------------------------|
| <span data-ttu-id="657f2-179">Aplikacja konsoli</span><span class="sxs-lookup"><span data-stu-id="657f2-179">Console Application</span></span>                    | `console`              |
| <span data-ttu-id="657f2-180">Biblioteka klas</span><span class="sxs-lookup"><span data-stu-id="657f2-180">Class library</span></span>                          | `classlib`             |
| <span data-ttu-id="657f2-181">Aplikacja WPF</span><span class="sxs-lookup"><span data-stu-id="657f2-181">WPF Application</span></span>                        | `wpf`                  |
| <span data-ttu-id="657f2-182">Biblioteka klas WPF</span><span class="sxs-lookup"><span data-stu-id="657f2-182">WPF Class library</span></span>                      | `wpflib`               |
| <span data-ttu-id="657f2-183">Biblioteka kontrolek niestandardowych WPF</span><span class="sxs-lookup"><span data-stu-id="657f2-183">WPF Custom Control Library</span></span>             | `wpfcustomcontrollib`  |
| <span data-ttu-id="657f2-184">Biblioteka kontrolek użytkownika WPF</span><span class="sxs-lookup"><span data-stu-id="657f2-184">WPF User Control Library</span></span>               | `wpfusercontrollib`    |
| <span data-ttu-id="657f2-185">Aplikacja Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="657f2-185">Windows Forms (WinForms) Application</span></span>   | `winforms`             |
| <span data-ttu-id="657f2-186">Biblioteka klas Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="657f2-186">Windows Forms (WinForms) Class library</span></span> | `winformslib`          |
| <span data-ttu-id="657f2-187">Projekt testu jednostkowego</span><span class="sxs-lookup"><span data-stu-id="657f2-187">Unit Test Project</span></span>                      | `mstest`               |
| <span data-ttu-id="657f2-188">Projekt testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="657f2-188">NUnit 3 Test Project</span></span>                   | `nunit`                |
| <span data-ttu-id="657f2-189">Element testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="657f2-189">NUnit 3 Test Item</span></span>                      | `nunit-test`           |
| <span data-ttu-id="657f2-190">Projekt testu xUnit</span><span class="sxs-lookup"><span data-stu-id="657f2-190">xUnit Test Project</span></span>                     | `xunit`                |

<span data-ttu-id="657f2-191">Aby uzyskać więcej informacji na temat szablonów projektów z interfejsu wiersza polecenia platformy .NET, zobacz [`dotnet new`](tools/dotnet-new.md) .</span><span class="sxs-lookup"><span data-stu-id="657f2-191">For more information on project templates from the .NET CLI, see [`dotnet new`](tools/dotnet-new.md).</span></span>

## <a name="net-maui"></a><span data-ttu-id="657f2-192">MAUI .NET</span><span class="sxs-lookup"><span data-stu-id="657f2-192">.NET MAUI</span></span>

<span data-ttu-id="657f2-193">.NET MAUI to ewolucja coraz większego popularnego zestawu narzędzi Xamarin. Forms i jest typu open source w witrynie GitHub na platformie [dotnet/Maui](https://github.com/dotnet/maui).</span><span class="sxs-lookup"><span data-stu-id="657f2-193">.NET MAUI is an evolution of the increasingly popular Xamarin.Forms toolkit, and is open-source on GitHub at [dotnet/maui](https://github.com/dotnet/maui).</span></span> <span data-ttu-id="657f2-194">W przypadku programu .NET MAUI wybór dla deweloperów platformy .NET jest uproszczony, zapewniając pojedynczy stos obsługujący wszystkie nowoczesne obciążenia: Android, iOS, macOS i Windows.</span><span class="sxs-lookup"><span data-stu-id="657f2-194">With .NET MAUI, the choice for .NET developers is simplified, providing a single stack that supports all modern workloads: Android, iOS, macOS, and Windows.</span></span> <span data-ttu-id="657f2-195">Za pomocą programu .NET MAUI uzyskasz jeden środowisko dewelopera projektu, które jest przeznaczone dla wielu platform i urządzeń.</span><span class="sxs-lookup"><span data-stu-id="657f2-195">With .NET MAUI, you get a single project developer experience that targets multiple platforms and devices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="657f2-196">Program .NET MAUI jest w wczesnej wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="657f2-196">.NET MAUI is in early preview.</span></span> <span data-ttu-id="657f2-197">Przykładowy kod źródłowy można znaleźć na platformie [Xamarin/net6-Samples](https://github.com/xamarin/net6-samples).</span><span class="sxs-lookup"><span data-stu-id="657f2-197">Sample source code can be found at [xamarin/net6-samples](https://github.com/xamarin/net6-samples).</span></span>

### <a name="model-view-update-pattern"></a><span data-ttu-id="657f2-198">Model-View-Update — wzorzec</span><span class="sxs-lookup"><span data-stu-id="657f2-198">Model-View-Update pattern</span></span>

<span data-ttu-id="657f2-199">Deweloperzy lubią nowoczesne wzorce projektowania.</span><span class="sxs-lookup"><span data-stu-id="657f2-199">Developers love modern development patterns.</span></span> <span data-ttu-id="657f2-200">Podejście do tworzenia interfejsu użytkownika, które jest inspirowane "architekturą Elm", jest wzorcem [Model-View-Update](https://elmprogramming.com/model-view-update-part-1.html) lub MVU.</span><span class="sxs-lookup"><span data-stu-id="657f2-200">A fluent approach to UI development, inspired by "The Elm Architecture" is the [model-view-update](https://elmprogramming.com/model-view-update-part-1.html) or MVU pattern.</span></span> <span data-ttu-id="657f2-201">MVU promuje jednokierunkową przepływ zarządzania danymi i Stanami, a także środowisko programistyczne, które szybko aktualizuje interfejs użytkownika, stosując tylko te zmiany.</span><span class="sxs-lookup"><span data-stu-id="657f2-201">MVU promotes a one-way flow of data and state management, as well as a code-first development experience that rapidly updates the UI by applying only the changes necessary.</span></span>

<span data-ttu-id="657f2-202">Na przykład rozważmy następujący licznik zapisany w programie .NET MAUI przy użyciu wzorca MVU:</span><span class="sxs-lookup"><span data-stu-id="657f2-202">As an example, consider the following counter written in .NET MAUI using the MVU pattern:</span></span>

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

<span data-ttu-id="657f2-203">Aby uzyskać więcej informacji, zobacz [plan .NET Maui](https://github.com/dotnet/maui/wiki/Roadmap)i wprowadzenie do artykułu [.NET Maui](https://devblogs.microsoft.com/dotnet/introducing-net-multi-platform-app-ui) .</span><span class="sxs-lookup"><span data-stu-id="657f2-203">For more information, see the [.NET MAUI roadmap](https://github.com/dotnet/maui/wiki/Roadmap), and [Introducing .NET MAUI](https://devblogs.microsoft.com/dotnet/introducing-net-multi-platform-app-ui) article.</span></span>

## <a name="see-also"></a><span data-ttu-id="657f2-204">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="657f2-204">See also</span></span>

- [<span data-ttu-id="657f2-205">Podróż do jednego programu .NET</span><span class="sxs-lookup"><span data-stu-id="657f2-205">The Journey to one .NET</span></span>](https://channel9.msdn.com/Events/Build/2020/BOD106)
- [<span data-ttu-id="657f2-206">Ulepszenia wydajności w programie .NET 5</span><span class="sxs-lookup"><span data-stu-id="657f2-206">Performance improvements in .NET 5</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)
