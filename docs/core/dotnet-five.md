---
title: Ewolucja platformy .NET Core do platformy .NET 5
description: Dowiedz się więcej na temat platformy .NET 5 — platformy deweloperskiej obejmującej wiele platform i typu "open source", która jest kolejną ewolucją platformy .NET Core.
ms.date: 09/02/2020
ms.topic: overview
ms.author: dapine
author: IEvangelist
ms.openlocfilehash: 9318b1afbe22c97f056bd38732306c6a6b60ad00
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598119"
---
# <a name="the-evolution-of-net-core-to-net-5"></a><span data-ttu-id="4890b-103">Ewolucja platformy .NET Core do platformy .NET 5</span><span class="sxs-lookup"><span data-stu-id="4890b-103">The evolution of .NET Core to .NET 5</span></span>

<span data-ttu-id="4890b-104">W tym artykule przedstawiono szczegółowe informacje zawarte w programie .NET 5, który jest następną wersją programu .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="4890b-104">This article details what's included in .NET 5, which is the next release of .NET Core following 3.1.</span></span> <span data-ttu-id="4890b-105">Numer wersji to 5,0, aby uniknąć nieporozumień przy użyciu .NET Framework 4. x.</span><span class="sxs-lookup"><span data-stu-id="4890b-105">The version number is 5.0 to avoid confusion with .NET Framework 4.x.</span></span> <span data-ttu-id="4890b-106">I "rdzeń" został porzucony z nazwy, ponieważ jest to główna implementacja platformy .NET do przodu.</span><span class="sxs-lookup"><span data-stu-id="4890b-106">And "Core" is dropped from the name because it is the main implementation of .NET going forward.</span></span> <span data-ttu-id="4890b-107">ASP.NET Core zachowuje nazwę "rdzeń", aby uniknąć pomyłki z ASP.NET MVC 5.</span><span class="sxs-lookup"><span data-stu-id="4890b-107">ASP.NET Core retains the name "Core" to avoid confusing it with ASP.NET MVC 5.</span></span> <span data-ttu-id="4890b-108">Ponadto Entity Framework Core zachowuje nazwę "rdzeń", aby uniknąć pomyłki z Entity Framework 5 i 6.</span><span class="sxs-lookup"><span data-stu-id="4890b-108">Additionally, Entity Framework Core retains the name "Core" to avoid confusing it with Entity Framework 5 and 6.</span></span> <span data-ttu-id="4890b-109">Platforma .NET 5 obsługuje więcej typów aplikacji i więcej platform niż .NET Core lub .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4890b-109">.NET 5 supports more types of apps and more platforms than .NET Core or .NET Framework.</span></span>

<span data-ttu-id="4890b-110">Pojawieniu platformy .NET Core rozwinęły ekosystem platformy .NET w atrakcyjny sposób.</span><span class="sxs-lookup"><span data-stu-id="4890b-110">The advent of .NET Core has evolved the .NET ecosystem in compelling ways.</span></span> <span data-ttu-id="4890b-111">Zostało ono dojrzałe jako projekt Open Source w witrynie GitHub, świętujemy wkłady społecznościowe i humbly ulepszenie w miarę upływu czasu.</span><span class="sxs-lookup"><span data-stu-id="4890b-111">It matured as an open-source project on GitHub, celebrating community contributions, and humbly improving over time.</span></span>

<span data-ttu-id="4890b-112">Platforma .NET Core ma kilka podstawowych cech:</span><span class="sxs-lookup"><span data-stu-id="4890b-112">.NET Core has several primary characteristics:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="4890b-113">Wiele platform</span><span class="sxs-lookup"><span data-stu-id="4890b-113">Cross-platform</span></span>
> - <span data-ttu-id="4890b-114">Open source</span><span class="sxs-lookup"><span data-stu-id="4890b-114">Open-source</span></span>
> - <span data-ttu-id="4890b-115">Instalacja równoczesna</span><span class="sxs-lookup"><span data-stu-id="4890b-115">Side-by-side installation</span></span>
> - <span data-ttu-id="4890b-116">Małe pliki projektu (zestaw SDK)</span><span class="sxs-lookup"><span data-stu-id="4890b-116">Small project files (SDK-style)</span></span>
> - <span data-ttu-id="4890b-117">Elastyczne wdrażanie</span><span class="sxs-lookup"><span data-stu-id="4890b-117">Flexible deployment</span></span>

<span data-ttu-id="4890b-118">Platforma .NET 5 rozszerza te charakterystyki, wprowadzając przyrostowe ulepszenia:</span><span class="sxs-lookup"><span data-stu-id="4890b-118">.NET 5 extends these characteristics, making incremental improvements:</span></span>

- <span data-ttu-id="4890b-119">Aplikacje pojedynczego pliku</span><span class="sxs-lookup"><span data-stu-id="4890b-119">Single file apps</span></span>
- <span data-ttu-id="4890b-120">Funkcje wewnętrzne ARM64 i ARM64 systemu Windows</span><span class="sxs-lookup"><span data-stu-id="4890b-120">Windows ARM64 and ARM64 intrinsics</span></span>
- <span data-ttu-id="4890b-121">Udoskonalenia wydajności w celu:</span><span class="sxs-lookup"><span data-stu-id="4890b-121">Sweeping performance improvements to:</span></span>
  - [<span data-ttu-id="4890b-122">Odzyskiwanie pamięci (GC)</span><span class="sxs-lookup"><span data-stu-id="4890b-122">Garbage Collection (GC)</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#gc)
  - [<span data-ttu-id="4890b-123">System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="4890b-123">System.Text.Json</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#json)
  - [<span data-ttu-id="4890b-124">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="4890b-124">System.Text.RegularExpressions</span></span>](https://devblogs.microsoft.com/dotnet/regex-performance-improvements-in-net-5)
  - [<span data-ttu-id="4890b-125">Asynchroniczne buforowanie ValueTask</span><span class="sxs-lookup"><span data-stu-id="4890b-125">Async ValueTask pooling</span></span>](https://devblogs.microsoft.com/dotnet/async-valuetask-pooling-in-net-5)
  - [<span data-ttu-id="4890b-126">Wiele więcej obszarów</span><span class="sxs-lookup"><span data-stu-id="4890b-126">Many more areas</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)
- <span data-ttu-id="4890b-127">Optymalizacje rozmiaru kontenera</span><span class="sxs-lookup"><span data-stu-id="4890b-127">Container size optimizations</span></span>
- [<span data-ttu-id="4890b-128">Przycinanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="4890b-128">App trimming</span></span>](https://devblogs.microsoft.com/dotnet/app-trimming-in-net-5)
- [<span data-ttu-id="4890b-129">Udoskonalenia kompilatora języka C#</span><span class="sxs-lookup"><span data-stu-id="4890b-129">C# compiler enhancements</span></span>](https://devblogs.microsoft.com/dotnet/automatically-find-latent-bugs-in-your-code-with-net-5)
- <span data-ttu-id="4890b-130">Narzędzia obsługujące debugowanie zrzutów</span><span class="sxs-lookup"><span data-stu-id="4890b-130">Tooling support for dump debugging</span></span>
- <span data-ttu-id="4890b-131">Platforma to 80% adnotacji dla [typów referencyjnych dopuszczających wartości null](../csharp/nullable-references.md)</span><span class="sxs-lookup"><span data-stu-id="4890b-131">Platform is 80% annotated for [nullable reference types](../csharp/nullable-references.md)</span></span>

### <a name="what-net-5-is-not"></a><span data-ttu-id="4890b-132">Co to jest platforma .NET 5</span><span class="sxs-lookup"><span data-stu-id="4890b-132">What .NET 5 is not</span></span>

<span data-ttu-id="4890b-133">Platforma .NET 5 nie zastępuje .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4890b-133">.NET 5 is not a replacement for .NET Framework.</span></span> <span data-ttu-id="4890b-134">Nie istnieją plany dotyczące portów następujących technologii z .NET Framework do platformy .NET 5, ale istnieją obsługiwane alternatywy zawarte w programie .NET 5:</span><span class="sxs-lookup"><span data-stu-id="4890b-134">There are no plans to port the following technologies from .NET Framework to .NET 5, but there are supported alternatives included in .NET 5:</span></span>

| <span data-ttu-id="4890b-135">Technologia</span><span class="sxs-lookup"><span data-stu-id="4890b-135">Technology</span></span>                             | <span data-ttu-id="4890b-136">Zalecenie</span><span class="sxs-lookup"><span data-stu-id="4890b-136">Recommendation</span></span>                                              |
|----------------------------------------|-------------------------------------------------------------|
| <span data-ttu-id="4890b-137">Formularze sieci Web</span><span class="sxs-lookup"><span data-stu-id="4890b-137">Web Forms</span></span>                              | [<span data-ttu-id="4890b-138">ASP.NET Core Blazor</span><span class="sxs-lookup"><span data-stu-id="4890b-138">ASP.NET Core Blazor</span></span>](/aspnet/core/blazor)                  |
| <span data-ttu-id="4890b-139">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="4890b-139">Windows Communication Foundation (WCF)</span></span> | [<span data-ttu-id="4890b-140">gRPC</span><span class="sxs-lookup"><span data-stu-id="4890b-140">gRPC</span></span>](/aspnet/core/grpc)                                   |
| <span data-ttu-id="4890b-141">Windows Workflow (WF)</span><span class="sxs-lookup"><span data-stu-id="4890b-141">Windows Workflow (WF)</span></span>                  | [<span data-ttu-id="4890b-142">CoreWF "open source"</span><span class="sxs-lookup"><span data-stu-id="4890b-142">Open-source CoreWF</span></span>](https://github.com/UiPath-Open/corewf) |

## <a name="net-standard"></a><span data-ttu-id="4890b-143">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="4890b-143">.NET Standard</span></span>

<span data-ttu-id="4890b-144">Nowe opracowywanie aplikacji może określać `net5.0` moniker platformy docelowej (TFM) dla wszystkich typów projektów, w tym biblioteki klas.</span><span class="sxs-lookup"><span data-stu-id="4890b-144">New application development can specify the `net5.0` target framework moniker (TFM) for all project types, including class libraries.</span></span> <span data-ttu-id="4890b-145">Udostępnianie kodu między obciążeniami programu .NET 5 jest uproszczone w tym, że wszystko, co jest potrzebne, to `net5.0` TFM.</span><span class="sxs-lookup"><span data-stu-id="4890b-145">Sharing code between .NET 5 workloads is simplified in that all you need is the `net5.0` TFM.</span></span>

<span data-ttu-id="4890b-146">`net5.0`TFM łączy i zastępuje `netcoreapp` `netstandard` nazwy i.</span><span class="sxs-lookup"><span data-stu-id="4890b-146">The `net5.0` TFM combines and replaces the `netcoreapp` and `netstandard` names.</span></span> <span data-ttu-id="4890b-147">Ta TFM zazwyczaj obejmuje tylko technologie, które działają na wielu platformach, takich jak .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4890b-147">This TFM will generally only include technologies that work cross-platform, like was done with .NET Standard.</span></span> <span data-ttu-id="4890b-148">Jeśli jednak planujesz udostępnianie kodu między obciążeniami .NET Framework, .NET Core i .NET 5, możesz to zrobić, określając `netstandard2.0` jako TFM.</span><span class="sxs-lookup"><span data-stu-id="4890b-148">However, if you plan to share code between .NET Framework, .NET Core, and .NET 5 workloads, you can do so by specifying `netstandard2.0` as your TFM.</span></span> <span data-ttu-id="4890b-149">Aby uzyskać więcej informacji, zobacz [jak określić Platformy docelowe](../standard/frameworks.md#how-to-specify-a-target-framework).</span><span class="sxs-lookup"><span data-stu-id="4890b-149">For more information, see [How to specify target frameworks](../standard/frameworks.md#how-to-specify-a-target-framework).</span></span>

## <a name="language-updates"></a><span data-ttu-id="4890b-150">Aktualizacje języka</span><span class="sxs-lookup"><span data-stu-id="4890b-150">Language updates</span></span>

<span data-ttu-id="4890b-151">W przypadku platformy .NET 5 Języki programowania .NET są kontynuowane.</span><span class="sxs-lookup"><span data-stu-id="4890b-151">With .NET 5, the .NET programming languages are continuing to improve.</span></span>

### <a name="c-updates"></a><span data-ttu-id="4890b-152">Aktualizacje w języku C#</span><span class="sxs-lookup"><span data-stu-id="4890b-152">C# updates</span></span>

<span data-ttu-id="4890b-153">Deweloperzy piszący aplikacje .NET 5 będą mieli dostęp do najnowszej wersji i funkcji języka C#.</span><span class="sxs-lookup"><span data-stu-id="4890b-153">Developers writing .NET 5 apps will have access to the latest C# version and features.</span></span> <span data-ttu-id="4890b-154">Program .NET 5 jest sparowany z językiem C# 9, który oferuje wiele nowych funkcji w języku.</span><span class="sxs-lookup"><span data-stu-id="4890b-154">.NET 5 is paired with C# 9, which brings many new features to the language.</span></span> <span data-ttu-id="4890b-155">Oto kilka świateł:</span><span class="sxs-lookup"><span data-stu-id="4890b-155">Here are a few highlights:</span></span>

- <span data-ttu-id="4890b-156">Rekordy: niezmienne typy odwołań, które zachowują się jak typy wartości, i wprowadzają nowe `with` słowo kluczowe do języka.</span><span class="sxs-lookup"><span data-stu-id="4890b-156">Records: Immutable reference types that behave like value types, and introduce the new `with` keyword into the language.</span></span>
- <span data-ttu-id="4890b-157">Dopasowywanie do wzorca relacyjnego: rozszerza możliwości dopasowania wzorców do operatorów relacyjnych dla obliczeń porównawczych i wyrażeń, w tym wzorców logicznych — nowe słowa kluczowe `and` , `or` i `not` .</span><span class="sxs-lookup"><span data-stu-id="4890b-157">Relational pattern matching: Extends pattern matching capabilities to relational operators for comparative evaluations and expressions, including logical patterns - new keywords `and`, `or`, and `not`.</span></span>
- <span data-ttu-id="4890b-158">Instrukcje najwyższego poziomu: jako metody przyspieszania wdrażania i uczenia się języka C#, `Main` Metoda może zostać pominięta, a aplikacja jako prosta jest prawidłowa:</span><span class="sxs-lookup"><span data-stu-id="4890b-158">Top-level statements: As a means for accelerating adoption and learning of C#, the `Main` method can be omitted and application as simple as the following is valid:</span></span>

   ```csharp
   System.Console.Write("Hello world!");
   ```

- <span data-ttu-id="4890b-159">Wskaźniki funkcji: konstrukcje języka, które uwidaczniają następujące kod w języku pośrednim (IL): `ldftn` i `calli` .</span><span class="sxs-lookup"><span data-stu-id="4890b-159">Function pointers: Language constructs that expose the following intermediate language (IL) opcodes: `ldftn` and `calli`.</span></span>

<span data-ttu-id="4890b-160">Aby uzyskać więcej informacji na temat dostępnych funkcji języka C# 9, zobacz [co nowego w języku c# 9](../csharp/whats-new/csharp-9.md).</span><span class="sxs-lookup"><span data-stu-id="4890b-160">For more information on the available C# 9 features, see [What's new in C# 9](../csharp/whats-new/csharp-9.md).</span></span>

#### <a name="source-generators"></a><span data-ttu-id="4890b-161">Generatory źródeł</span><span class="sxs-lookup"><span data-stu-id="4890b-161">Source generators</span></span>

<span data-ttu-id="4890b-162">Oprócz niektórych wyróżnionych nowych funkcji języka C#, generatory źródeł są gotowe do projektów deweloperskich.</span><span class="sxs-lookup"><span data-stu-id="4890b-162">In addition to some of the highlighted new C# features, source generators are making their way into developer projects.</span></span> <span data-ttu-id="4890b-163">Generatory źródła umożliwiają kod, który jest uruchamiany podczas kompilacji w celu sprawdzenia programu i tworzenia dodatkowych plików, które są kompilowane razem z resztą kodu.</span><span class="sxs-lookup"><span data-stu-id="4890b-163">Source generators allow code that runs during compilation to inspect your program and produce additional files that are compiled together with the rest of your code.</span></span>

<span data-ttu-id="4890b-164">Aby uzyskać więcej informacji na temat generatorów źródeł, zobacz [wprowadzenie do źródłowych generatorów języka c#](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) i [próbek generatora źródła c#](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).</span><span class="sxs-lookup"><span data-stu-id="4890b-164">For more information on source generators, see [Introducing C# source generators](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) and [C# source generator samples](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).</span></span>

### <a name="f-updates"></a><span data-ttu-id="4890b-165">Aktualizacje języka F #</span><span class="sxs-lookup"><span data-stu-id="4890b-165">F# updates</span></span>

<span data-ttu-id="4890b-166">F # to język programowania funkcjonalny .NET, a w przypadku platformy .NET 5 deweloperzy mają dostęp do programu F # 5.</span><span class="sxs-lookup"><span data-stu-id="4890b-166">F# is the .NET functional programming language, and with .NET 5, developers have access to F# 5.</span></span> <span data-ttu-id="4890b-167">Oto kilka nowych funkcji języka F # 5:</span><span class="sxs-lookup"><span data-stu-id="4890b-167">Here are several new features of F# 5:</span></span>

#### <a name="interpolated-strings"></a><span data-ttu-id="4890b-168">Ciągi interpolowane</span><span class="sxs-lookup"><span data-stu-id="4890b-168">Interpolated strings</span></span>

<span data-ttu-id="4890b-169">Podobnie jak ciąg interpolowany w języku C#, a nawet JavaScript, język F # obsługuje interpolację ciągów podstawowych.</span><span class="sxs-lookup"><span data-stu-id="4890b-169">Similar to interpolated string in C#, and even JavaScript, F# supports basic string interpolation.</span></span>

```fsharp
let name = "David"
let age = 36
let message = $"{name} is {age} years old."
```

<span data-ttu-id="4890b-170">Oprócz podstawowej interpolacji ciągów jest wpisana Interpolacja.</span><span class="sxs-lookup"><span data-stu-id="4890b-170">In addition to basic string interpolation, there is typed interpolation.</span></span> <span data-ttu-id="4890b-171">Po wpisaniu interpolacji, dany typ musi być zgodny ze specyfikatorem formatu.</span><span class="sxs-lookup"><span data-stu-id="4890b-171">With typed interpolation, a given type must match the format specifier.</span></span>

```fsharp
let name = "David"
let age = 36
let message = $"%s{name} is %d{age} years old."
```

<span data-ttu-id="4890b-172">Jest to podobne do [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) funkcji, która formatuje ciąg w oparciu o dane wejściowe bezpieczne dla typów.</span><span class="sxs-lookup"><span data-stu-id="4890b-172">This is similar to the [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) function that formats a string based on type-safe inputs.</span></span> <!-- For more information, see [What's new in F# 5](fsharp/whats-new/fsharp-50.md). -->

### <a name="visual-basic-updates"></a><span data-ttu-id="4890b-173">Aktualizacje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4890b-173">Visual Basic updates</span></span>

<span data-ttu-id="4890b-174">Nie ma nowych funkcji języka dla Visual Basic w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="4890b-174">There are no new language features for Visual Basic in .NET 5.</span></span> <span data-ttu-id="4890b-175">Jednak w przypadku platformy .NET 5 obsługa Visual Basic została rozszerzona o następujące:</span><span class="sxs-lookup"><span data-stu-id="4890b-175">However, with .NET 5, Visual Basic support is extended to:</span></span>

| <span data-ttu-id="4890b-176">Opis</span><span class="sxs-lookup"><span data-stu-id="4890b-176">Description</span></span>                            | <span data-ttu-id="4890b-177">`dotnet new` konstruktora</span><span class="sxs-lookup"><span data-stu-id="4890b-177">`dotnet new` parameter</span></span> |
|----------------------------------------|------------------------|
| <span data-ttu-id="4890b-178">Aplikacja konsoli</span><span class="sxs-lookup"><span data-stu-id="4890b-178">Console Application</span></span>                    | `console`              |
| <span data-ttu-id="4890b-179">Biblioteka klas</span><span class="sxs-lookup"><span data-stu-id="4890b-179">Class library</span></span>                          | `classlib`             |
| <span data-ttu-id="4890b-180">Aplikacja WPF</span><span class="sxs-lookup"><span data-stu-id="4890b-180">WPF Application</span></span>                        | `wpf`                  |
| <span data-ttu-id="4890b-181">Biblioteka klas WPF</span><span class="sxs-lookup"><span data-stu-id="4890b-181">WPF Class library</span></span>                      | `wpflib`               |
| <span data-ttu-id="4890b-182">Biblioteka kontrolek niestandardowych WPF</span><span class="sxs-lookup"><span data-stu-id="4890b-182">WPF Custom Control Library</span></span>             | `wpfcustomcontrollib`  |
| <span data-ttu-id="4890b-183">Biblioteka kontrolek użytkownika WPF</span><span class="sxs-lookup"><span data-stu-id="4890b-183">WPF User Control Library</span></span>               | `wpfusercontrollib`    |
| <span data-ttu-id="4890b-184">Aplikacja Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="4890b-184">Windows Forms (WinForms) Application</span></span>   | `winforms`             |
| <span data-ttu-id="4890b-185">Biblioteka klas Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="4890b-185">Windows Forms (WinForms) Class library</span></span> | `winformslib`          |
| <span data-ttu-id="4890b-186">Projekt testu jednostkowego</span><span class="sxs-lookup"><span data-stu-id="4890b-186">Unit Test Project</span></span>                      | `mstest`               |
| <span data-ttu-id="4890b-187">Projekt testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="4890b-187">NUnit 3 Test Project</span></span>                   | `nunit`                |
| <span data-ttu-id="4890b-188">Element testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="4890b-188">NUnit 3 Test Item</span></span>                      | `nunit-test`           |
| <span data-ttu-id="4890b-189">Projekt testu xUnit</span><span class="sxs-lookup"><span data-stu-id="4890b-189">xUnit Test Project</span></span>                     | `xunit`                |

<span data-ttu-id="4890b-190">Aby uzyskać więcej informacji na temat szablonów projektów z interfejsu wiersza polecenia platformy .NET, zobacz [`dotnet new`](tools/dotnet-new.md) .</span><span class="sxs-lookup"><span data-stu-id="4890b-190">For more information on project templates from the .NET CLI, see [`dotnet new`](tools/dotnet-new.md).</span></span>

## <a name="net-maui"></a><span data-ttu-id="4890b-191">MAUI .NET</span><span class="sxs-lookup"><span data-stu-id="4890b-191">.NET MAUI</span></span>

<span data-ttu-id="4890b-192">.NET MAUI to ewolucja coraz większego popularnego zestawu narzędzi Xamarin. Forms i jest typu open source w witrynie GitHub na platformie [dotnet/Maui](https://github.com/dotnet/maui).</span><span class="sxs-lookup"><span data-stu-id="4890b-192">.NET MAUI is an evolution of the increasingly popular Xamarin.Forms toolkit, and is open-source on GitHub at [dotnet/maui](https://github.com/dotnet/maui).</span></span> <span data-ttu-id="4890b-193">W przypadku programu .NET MAUI wybór dla deweloperów platformy .NET jest uproszczony, zapewniając pojedynczy stos obsługujący wszystkie nowoczesne obciążenia: Android, iOS, macOS i Windows.</span><span class="sxs-lookup"><span data-stu-id="4890b-193">With .NET MAUI, the choice for .NET developers is simplified, providing a single stack that supports all modern workloads: Android, iOS, macOS, and Windows.</span></span> <span data-ttu-id="4890b-194">Za pomocą programu .NET MAUI uzyskasz jeden środowisko dewelopera projektu, które jest przeznaczone dla wielu platform i urządzeń.</span><span class="sxs-lookup"><span data-stu-id="4890b-194">With .NET MAUI, you get a single project developer experience that targets multiple platforms and devices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4890b-195">Program .NET MAUI jest w wczesnej wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="4890b-195">.NET MAUI is in early preview.</span></span> <span data-ttu-id="4890b-196">Przykładowy kod źródłowy można znaleźć na platformie [Xamarin/net6-Samples](https://github.com/xamarin/net6-samples).</span><span class="sxs-lookup"><span data-stu-id="4890b-196">Sample source code can be found at [xamarin/net6-samples](https://github.com/xamarin/net6-samples).</span></span>

### <a name="model-view-update-pattern"></a><span data-ttu-id="4890b-197">Model-View-Update — wzorzec</span><span class="sxs-lookup"><span data-stu-id="4890b-197">Model-View-Update pattern</span></span>

<span data-ttu-id="4890b-198">Deweloperzy lubią nowoczesne wzorce projektowania.</span><span class="sxs-lookup"><span data-stu-id="4890b-198">Developers love modern development patterns.</span></span> <span data-ttu-id="4890b-199">Podejście do tworzenia interfejsu użytkownika, które jest inspirowane "architekturą Elm", jest wzorcem [Model-View-Update](https://elmprogramming.com/model-view-update-part-1.html) lub MVU.</span><span class="sxs-lookup"><span data-stu-id="4890b-199">A fluent approach to UI development, inspired by "The Elm Architecture" is the [model-view-update](https://elmprogramming.com/model-view-update-part-1.html) or MVU pattern.</span></span> <span data-ttu-id="4890b-200">MVU promuje jednokierunkową przepływ zarządzania danymi i Stanami, a także środowisko programistyczne, które szybko aktualizuje interfejs użytkownika, stosując tylko te zmiany.</span><span class="sxs-lookup"><span data-stu-id="4890b-200">MVU promotes a one-way flow of data and state management, as well as a code-first development experience that rapidly updates the UI by applying only the changes necessary.</span></span>

<span data-ttu-id="4890b-201">Na przykład rozważmy następujący licznik zapisany w programie .NET MAUI przy użyciu wzorca MVU:</span><span class="sxs-lookup"><span data-stu-id="4890b-201">As an example, consider the following counter written in .NET MAUI using the MVU pattern:</span></span>

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

<span data-ttu-id="4890b-202">Aby uzyskać więcej informacji, zobacz [plan .NET Maui](https://github.com/dotnet/maui/wiki/Roadmap)i wprowadzenie do artykułu [.NET Maui](https://devblogs.microsoft.com/dotnet/introducing-net-multi-platform-app-ui) .</span><span class="sxs-lookup"><span data-stu-id="4890b-202">For more information, see the [.NET MAUI roadmap](https://github.com/dotnet/maui/wiki/Roadmap), and [Introducing .NET MAUI](https://devblogs.microsoft.com/dotnet/introducing-net-multi-platform-app-ui) article.</span></span>

## <a name="see-also"></a><span data-ttu-id="4890b-203">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4890b-203">See also</span></span>

- [<span data-ttu-id="4890b-204">Podróż do jednego programu .NET</span><span class="sxs-lookup"><span data-stu-id="4890b-204">The Journey to one .NET</span></span>](https://channel9.msdn.com/Events/Build/2020/BOD106)
- [<span data-ttu-id="4890b-205">Ulepszenia wydajności w programie .NET 5</span><span class="sxs-lookup"><span data-stu-id="4890b-205">Performance improvements in .NET 5</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)
