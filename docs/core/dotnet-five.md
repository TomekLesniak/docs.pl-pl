---
title: Co nowego w wersji .NET 5
description: Dowiedz się więcej na temat platformy .NET 5 — platformy deweloperskiej obejmującej wiele platform i typu "open source", która jest kolejną ewolucją platformy .NET Core.
ms.date: 11/16/2020
ms.topic: overview
ms.author: dapine
author: IEvangelist
ms.openlocfilehash: 04f72675744426f7dbc99e5978a9ea4bbb8015b1
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687595"
---
# <a name="whats-new-in-net-5"></a><span data-ttu-id="bf495-103">Co nowego w wersji .NET 5</span><span class="sxs-lookup"><span data-stu-id="bf495-103">What's new in .NET 5</span></span>

<span data-ttu-id="bf495-104">.NET 5,0 to następna wersja główna programu .NET Core, która jest następująca: 3,1.</span><span class="sxs-lookup"><span data-stu-id="bf495-104">.NET 5.0 is the next major release of .NET Core following 3.1.</span></span> <span data-ttu-id="bf495-105">Ta nowa wersja programu .NET 5,0 zamiast programu .NET Core 4,0 została nazywana z dwóch powodów:</span><span class="sxs-lookup"><span data-stu-id="bf495-105">We named this new release .NET 5.0 instead of .NET Core 4.0 for two reasons:</span></span>

- <span data-ttu-id="bf495-106">Pominięto numery wersji 4. x, aby uniknąć pomyłek w .NET Framework 4. x.</span><span class="sxs-lookup"><span data-stu-id="bf495-106">We skipped version numbers 4.x to avoid confusion with .NET Framework 4.x.</span></span>
- <span data-ttu-id="bf495-107">Porzucamy "rdzeń" z nazwy, aby podkreślić, że jest to główna implementacja platformy .NET do przodu.</span><span class="sxs-lookup"><span data-stu-id="bf495-107">We dropped "Core" from the name to emphasize that this is the main implementation of .NET going forward.</span></span> <span data-ttu-id="bf495-108">Platforma .NET 5,0 obsługuje więcej typów aplikacji i więcej platform niż .NET Core lub .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bf495-108">.NET 5.0 supports more types of apps and more platforms than .NET Core or .NET Framework.</span></span>

<span data-ttu-id="bf495-109">ASP.NET Core 5,0 jest oparty na platformie .NET 5,0, ale zachowuje nazwę "rdzeń", aby uniknąć pomyłki z ASP.NET MVC 5.</span><span class="sxs-lookup"><span data-stu-id="bf495-109">ASP.NET Core 5.0 is based on .NET 5.0 but retains the name "Core" to avoid confusing it with ASP.NET MVC 5.</span></span> <span data-ttu-id="bf495-110">Podobnie, Entity Framework Core 5,0 zachowuje nazwę "rdzeń", aby uniknąć pomyłki z Entity Framework 5 i 6.</span><span class="sxs-lookup"><span data-stu-id="bf495-110">Likewise, Entity Framework Core 5.0 retains the name "Core" to avoid confusing it with Entity Framework 5 and 6.</span></span>

<span data-ttu-id="bf495-111">Program .NET 5,0 zawiera następujące ulepszenia i nowe funkcje w porównaniu z programem .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="bf495-111">.NET 5.0 includes the following improvements and new features compared to .NET Core 3.1:</span></span>

- [<span data-ttu-id="bf495-112">Aktualizacje w języku C#</span><span class="sxs-lookup"><span data-stu-id="bf495-112">C# updates</span></span>](#c-updates)
- [<span data-ttu-id="bf495-113">Aktualizacje języka F #</span><span class="sxs-lookup"><span data-stu-id="bf495-113">F# updates</span></span>](#f-updates)
- [<span data-ttu-id="bf495-114">Aktualizacje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf495-114">Visual Basic updates</span></span>](#visual-basic-updates)
- [<span data-ttu-id="bf495-115">System.Text.Jsnowych funkcji</span><span class="sxs-lookup"><span data-stu-id="bf495-115">System.Text.Json new features</span></span>](#systemtextjson-new-features)
- [<span data-ttu-id="bf495-116">Aplikacje pojedynczego pliku</span><span class="sxs-lookup"><span data-stu-id="bf495-116">Single file apps</span></span>](deploying/single-file.md)
- [<span data-ttu-id="bf495-117">Przycinanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="bf495-117">App trimming</span></span>](https://devblogs.microsoft.com/dotnet/app-trimming-in-net-5)
- <span data-ttu-id="bf495-118">Funkcje wewnętrzne ARM64 i ARM64 systemu Windows</span><span class="sxs-lookup"><span data-stu-id="bf495-118">Windows ARM64 and ARM64 intrinsics</span></span>
- <span data-ttu-id="bf495-119">Narzędzia obsługujące debugowanie zrzutów</span><span class="sxs-lookup"><span data-stu-id="bf495-119">Tooling support for dump debugging</span></span>
- <span data-ttu-id="bf495-120">Biblioteki środowiska uruchomieniowego są 80% adnotacją dla [typów odwołań dopuszczających wartości null](../csharp/nullable-references.md)</span><span class="sxs-lookup"><span data-stu-id="bf495-120">The runtime libraries are 80% annotated for [nullable reference types](../csharp/nullable-references.md)</span></span>
- <span data-ttu-id="bf495-121">Ulepszenia wydajności:</span><span class="sxs-lookup"><span data-stu-id="bf495-121">Performance improvements:</span></span>
  - [<span data-ttu-id="bf495-122">Odzyskiwanie pamięci (GC)</span><span class="sxs-lookup"><span data-stu-id="bf495-122">Garbage Collection (GC)</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#gc)
  - [<span data-ttu-id="bf495-123">System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="bf495-123">System.Text.Json</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#json)
  - [<span data-ttu-id="bf495-124">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="bf495-124">System.Text.RegularExpressions</span></span>](https://devblogs.microsoft.com/dotnet/regex-performance-improvements-in-net-5)
  - [<span data-ttu-id="bf495-125">Asynchroniczne buforowanie ValueTask</span><span class="sxs-lookup"><span data-stu-id="bf495-125">Async ValueTask pooling</span></span>](https://devblogs.microsoft.com/dotnet/async-valuetask-pooling-in-net-5)
  - [<span data-ttu-id="bf495-126">Optymalizacje rozmiaru kontenera</span><span class="sxs-lookup"><span data-stu-id="bf495-126">Container size optimizations</span></span>](https://github.com/dotnet/dotnet-docker/issues/1814#issuecomment-625294750)
  - [<span data-ttu-id="bf495-127">Wiele więcej obszarów</span><span class="sxs-lookup"><span data-stu-id="bf495-127">Many more areas</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)

## <a name="net-50-doesnt-replace-net-framework"></a><span data-ttu-id="bf495-128">.NET 5,0 nie zastępuje .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bf495-128">.NET 5.0 doesn't replace .NET Framework</span></span>

<span data-ttu-id="bf495-129">.NET 5,0 to główna implementacja platformy .NET do przodu i .NET Framework 4. x jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="bf495-129">.NET 5.0 is the main implementation of .NET going forward and .NET Framework 4.x is still supported.</span></span>

<span data-ttu-id="bf495-130">Nie ma żadnych planów dotyczących portów z .NET Framework do .NET 5,0, ale istnieją alternatywy w programie .NET 5,0:</span><span class="sxs-lookup"><span data-stu-id="bf495-130">There are no plans to port the following technologies from .NET Framework to .NET 5.0, but there are alternatives in .NET 5.0:</span></span>

| <span data-ttu-id="bf495-131">Technologia</span><span class="sxs-lookup"><span data-stu-id="bf495-131">Technology</span></span>                             | <span data-ttu-id="bf495-132">Zalecana alternatywa</span><span class="sxs-lookup"><span data-stu-id="bf495-132">Recommended alternative</span></span>                                                                         |
|----------------------------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="bf495-133">Formularze sieci Web</span><span class="sxs-lookup"><span data-stu-id="bf495-133">Web Forms</span></span>                              | <span data-ttu-id="bf495-134">ASP.NET Core [Blazor](/aspnet/core/blazor) lub [Razor Pages](/aspnet/core/tutorials/razor-pages)</span><span class="sxs-lookup"><span data-stu-id="bf495-134">ASP.NET Core [Blazor](/aspnet/core/blazor) or [Razor Pages](/aspnet/core/tutorials/razor-pages)</span></span> |
| <span data-ttu-id="bf495-135">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="bf495-135">Windows Communication Foundation (WCF)</span></span> | [<span data-ttu-id="bf495-136">gRPC</span><span class="sxs-lookup"><span data-stu-id="bf495-136">gRPC</span></span>](/aspnet/core/grpc)                                                                       |
| <span data-ttu-id="bf495-137">Windows Workflow (WF)</span><span class="sxs-lookup"><span data-stu-id="bf495-137">Windows Workflow (WF)</span></span>                  | [<span data-ttu-id="bf495-138">CoreWF "open source"</span><span class="sxs-lookup"><span data-stu-id="bf495-138">Open-source CoreWF</span></span>](https://github.com/UiPath-Open/corewf)                                     |

## <a name="net-50-doesnt-replace-net-standard"></a><span data-ttu-id="bf495-139">.NET 5,0 nie zastępuje .NET Standard</span><span class="sxs-lookup"><span data-stu-id="bf495-139">.NET 5.0 doesn't replace .NET Standard</span></span>

<span data-ttu-id="bf495-140">Nowe opracowywanie aplikacji może określać `net5.0` moniker platformy docelowej (TFM) dla wszystkich typów projektów, w tym biblioteki klas.</span><span class="sxs-lookup"><span data-stu-id="bf495-140">New application development can specify the `net5.0` target framework moniker (TFM) for all project types, including class libraries.</span></span> <span data-ttu-id="bf495-141">Udostępnianie kodu między obciążeniami programu .NET 5 jest uproszczone w tym, że wszystko, co jest potrzebne, to `net5.0` TFM.</span><span class="sxs-lookup"><span data-stu-id="bf495-141">Sharing code between .NET 5 workloads is simplified in that all you need is the `net5.0` TFM.</span></span>

<span data-ttu-id="bf495-142">W przypadku aplikacji i bibliotek programu .NET 5,0, `net5.0` moniker struktury docelowej (TFM) łączy i zastępuje `netcoreapp` `netstandard` TFMs.</span><span class="sxs-lookup"><span data-stu-id="bf495-142">For .NET 5.0 apps and libraries, the `net5.0` Target Framework Moniker (TFM) combines and replaces the `netcoreapp` and `netstandard` TFMs.</span></span> <span data-ttu-id="bf495-143">Jeśli jednak planujesz udostępnianie kodu między obciążeniami .NET Framework, .NET Core i .NET 5, możesz to zrobić, określając `netstandard2.0` jako TFM.</span><span class="sxs-lookup"><span data-stu-id="bf495-143">However, if you plan to share code between .NET Framework, .NET Core, and .NET 5 workloads, you can do so by specifying `netstandard2.0` as your TFM.</span></span> <span data-ttu-id="bf495-144">Aby uzyskać więcej informacji, zobacz [.NET Standard](../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="bf495-144">For more information, see [.NET Standard](../standard/net-standard.md).</span></span>

## <a name="c-updates"></a><span data-ttu-id="bf495-145">Aktualizacje w języku C#</span><span class="sxs-lookup"><span data-stu-id="bf495-145">C# updates</span></span>

<span data-ttu-id="bf495-146">Deweloperzy piszący aplikacje .NET 5 będą mieli dostęp do najnowszej wersji i funkcji języka C#.</span><span class="sxs-lookup"><span data-stu-id="bf495-146">Developers writing .NET 5 apps will have access to the latest C# version and features.</span></span> <span data-ttu-id="bf495-147">Program .NET 5 jest sparowany z językiem C# 9, który oferuje wiele nowych funkcji w języku.</span><span class="sxs-lookup"><span data-stu-id="bf495-147">.NET 5 is paired with C# 9, which brings many new features to the language.</span></span> <span data-ttu-id="bf495-148">Oto kilka świateł:</span><span class="sxs-lookup"><span data-stu-id="bf495-148">Here are a few highlights:</span></span>

- <span data-ttu-id="bf495-149">Rekordy: typy referencyjne z semantyką równości opartej na wartościach i mutacją nieniszczącą obsługiwaną przez nowe `with` wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="bf495-149">Records: reference types with value-based equality semantics and non-destructive mutation supported by a new `with` expression.</span></span>
- <span data-ttu-id="bf495-150">Dopasowywanie do wzorca relacyjnego: rozszerza możliwości dopasowania wzorców do operatorów relacyjnych dla obliczeń porównawczych i wyrażeń, w tym wzorców logicznych — nowe słowa kluczowe `and` , `or` i `not` .</span><span class="sxs-lookup"><span data-stu-id="bf495-150">Relational pattern matching: Extends pattern matching capabilities to relational operators for comparative evaluations and expressions, including logical patterns - new keywords `and`, `or`, and `not`.</span></span>
- <span data-ttu-id="bf495-151">Instrukcje najwyższego poziomu: jako metody przyspieszania wdrażania i uczenia się języka C#, `Main` Metoda może zostać pominięta, a aplikacja jako prosta jest prawidłowa:</span><span class="sxs-lookup"><span data-stu-id="bf495-151">Top-level statements: As a means for accelerating adoption and learning of C#, the `Main` method can be omitted and application as simple as the following is valid:</span></span>

   ```csharp
   System.Console.Write("Hello world!");
   ```

- <span data-ttu-id="bf495-152">Wskaźniki funkcji: konstrukcje języka, które uwidaczniają następujące kod w języku pośrednim (IL): `ldftn` i `calli` .</span><span class="sxs-lookup"><span data-stu-id="bf495-152">Function pointers: Language constructs that expose the following intermediate language (IL) opcodes: `ldftn` and `calli`.</span></span>

<span data-ttu-id="bf495-153">Aby uzyskać więcej informacji na temat dostępnych funkcji języka C# 9, zobacz [co nowego w języku c# 9](../csharp/whats-new/csharp-9.md).</span><span class="sxs-lookup"><span data-stu-id="bf495-153">For more information on the available C# 9 features, see [What's new in C# 9](../csharp/whats-new/csharp-9.md).</span></span>

### <a name="source-generators"></a><span data-ttu-id="bf495-154">Generatory źródeł</span><span class="sxs-lookup"><span data-stu-id="bf495-154">Source generators</span></span>

<span data-ttu-id="bf495-155">Oprócz niektórych wyróżnionych nowych funkcji języka C#, generatory źródeł są gotowe do projektów deweloperskich.</span><span class="sxs-lookup"><span data-stu-id="bf495-155">In addition to some of the highlighted new C# features, source generators are making their way into developer projects.</span></span> <span data-ttu-id="bf495-156">Generatory źródła umożliwiają kod, który jest uruchamiany podczas kompilacji w celu sprawdzenia programu i tworzenia dodatkowych plików, które są kompilowane razem z resztą kodu.</span><span class="sxs-lookup"><span data-stu-id="bf495-156">Source generators allow code that runs during compilation to inspect your program and produce additional files that are compiled together with the rest of your code.</span></span>

<span data-ttu-id="bf495-157">Aby uzyskać więcej informacji na temat generatorów źródeł, zobacz [wprowadzenie do źródłowych generatorów języka c#](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) i [próbek generatora źródła c#](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).</span><span class="sxs-lookup"><span data-stu-id="bf495-157">For more information on source generators, see [Introducing C# source generators](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) and [C# source generator samples](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).</span></span>

## <a name="f-updates"></a><span data-ttu-id="bf495-158">Aktualizacje języka F #</span><span class="sxs-lookup"><span data-stu-id="bf495-158">F# updates</span></span>

<span data-ttu-id="bf495-159">F # to język programowania funkcjonalny .NET, a w przypadku platformy .NET 5 deweloperzy mają dostęp do programu F # 5.</span><span class="sxs-lookup"><span data-stu-id="bf495-159">F# is the .NET functional programming language, and with .NET 5, developers have access to F# 5.</span></span> <span data-ttu-id="bf495-160">Oto kilka nowych funkcji języka F # 5:</span><span class="sxs-lookup"><span data-stu-id="bf495-160">Here are several new features of F# 5:</span></span>

### <a name="interpolated-strings"></a><span data-ttu-id="bf495-161">Ciągi interpolowane</span><span class="sxs-lookup"><span data-stu-id="bf495-161">Interpolated strings</span></span>

<span data-ttu-id="bf495-162">Podobnie jak ciąg interpolowany w języku C#, a nawet JavaScript, język F # obsługuje interpolację ciągów podstawowych.</span><span class="sxs-lookup"><span data-stu-id="bf495-162">Similar to interpolated string in C#, and even JavaScript, F# supports basic string interpolation.</span></span>

```fsharp
let name = "David"
let age = 36
let message = $"{name} is {age} years old."
```

<span data-ttu-id="bf495-163">Oprócz podstawowej interpolacji ciągów jest wpisana Interpolacja.</span><span class="sxs-lookup"><span data-stu-id="bf495-163">In addition to basic string interpolation, there is typed interpolation.</span></span> <span data-ttu-id="bf495-164">Po wpisaniu interpolacji, dany typ musi być zgodny ze specyfikatorem formatu.</span><span class="sxs-lookup"><span data-stu-id="bf495-164">With typed interpolation, a given type must match the format specifier.</span></span>

```fsharp
let name = "David"
let age = 36
let message = $"%s{name} is %d{age} years old."
```

<span data-ttu-id="bf495-165">Jest to podobne do [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) funkcji, która formatuje ciąg w oparciu o dane wejściowe bezpieczne dla typów.</span><span class="sxs-lookup"><span data-stu-id="bf495-165">This is similar to the [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) function that formats a string based on type-safe inputs.</span></span> <!-- For more information, see [What's new in F# 5](fsharp/whats-new/fsharp-50.md). -->

## <a name="visual-basic-updates"></a><span data-ttu-id="bf495-166">Aktualizacje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf495-166">Visual Basic updates</span></span>

<span data-ttu-id="bf495-167">Nie ma nowych funkcji języka dla Visual Basic w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="bf495-167">There are no new language features for Visual Basic in .NET 5.</span></span> <span data-ttu-id="bf495-168">Jednak w przypadku platformy .NET 5 obsługa Visual Basic została rozszerzona o następujące:</span><span class="sxs-lookup"><span data-stu-id="bf495-168">However, with .NET 5, Visual Basic support is extended to:</span></span>

| <span data-ttu-id="bf495-169">Opis</span><span class="sxs-lookup"><span data-stu-id="bf495-169">Description</span></span>                            | <span data-ttu-id="bf495-170">`dotnet new` konstruktora</span><span class="sxs-lookup"><span data-stu-id="bf495-170">`dotnet new` parameter</span></span> |
|----------------------------------------|------------------------|
| <span data-ttu-id="bf495-171">Aplikacja konsoli</span><span class="sxs-lookup"><span data-stu-id="bf495-171">Console Application</span></span>                    | `console`              |
| <span data-ttu-id="bf495-172">Biblioteka klas</span><span class="sxs-lookup"><span data-stu-id="bf495-172">Class library</span></span>                          | `classlib`             |
| <span data-ttu-id="bf495-173">Aplikacja WPF</span><span class="sxs-lookup"><span data-stu-id="bf495-173">WPF Application</span></span>                        | `wpf`                  |
| <span data-ttu-id="bf495-174">Biblioteka klas WPF</span><span class="sxs-lookup"><span data-stu-id="bf495-174">WPF Class library</span></span>                      | `wpflib`               |
| <span data-ttu-id="bf495-175">Biblioteka kontrolek niestandardowych WPF</span><span class="sxs-lookup"><span data-stu-id="bf495-175">WPF Custom Control Library</span></span>             | `wpfcustomcontrollib`  |
| <span data-ttu-id="bf495-176">Biblioteka kontrolek użytkownika WPF</span><span class="sxs-lookup"><span data-stu-id="bf495-176">WPF User Control Library</span></span>               | `wpfusercontrollib`    |
| <span data-ttu-id="bf495-177">Aplikacja Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="bf495-177">Windows Forms (WinForms) Application</span></span>   | `winforms`             |
| <span data-ttu-id="bf495-178">Biblioteka klas Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="bf495-178">Windows Forms (WinForms) Class library</span></span> | `winformslib`          |
| <span data-ttu-id="bf495-179">Projekt testu jednostkowego</span><span class="sxs-lookup"><span data-stu-id="bf495-179">Unit Test Project</span></span>                      | `mstest`               |
| <span data-ttu-id="bf495-180">Projekt testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="bf495-180">NUnit 3 Test Project</span></span>                   | `nunit`                |
| <span data-ttu-id="bf495-181">Element testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="bf495-181">NUnit 3 Test Item</span></span>                      | `nunit-test`           |
| <span data-ttu-id="bf495-182">Projekt testu xUnit</span><span class="sxs-lookup"><span data-stu-id="bf495-182">xUnit Test Project</span></span>                     | `xunit`                |

<span data-ttu-id="bf495-183">Aby uzyskać więcej informacji na temat szablonów projektów z interfejsu wiersza polecenia platformy .NET, zobacz [`dotnet new`](tools/dotnet-new.md) .</span><span class="sxs-lookup"><span data-stu-id="bf495-183">For more information on project templates from the .NET CLI, see [`dotnet new`](tools/dotnet-new.md).</span></span>

## <a name="systemtextjson-new-features"></a><span data-ttu-id="bf495-184">System.Text.Jsnowych funkcji</span><span class="sxs-lookup"><span data-stu-id="bf495-184">System.Text.Json new features</span></span>

<span data-ttu-id="bf495-185">W [ systemach iSystem.Text.Js](../standard/serialization/system-text-json-overview.md)są dostępne nowe funkcje:</span><span class="sxs-lookup"><span data-stu-id="bf495-185">There are new features in and for [System.Text.Json](../standard/serialization/system-text-json-overview.md):</span></span>

- [<span data-ttu-id="bf495-186">Zachowaj odwołania i dojścia cykliczne odwołania</span><span class="sxs-lookup"><span data-stu-id="bf495-186">Preserve references and handle circular references</span></span>](../standard/serialization/system-text-json-how-to.md#preserve-references-and-handle-circular-references)
- [<span data-ttu-id="bf495-187">Metody rozszerzenia HttpClient i HttpContent</span><span class="sxs-lookup"><span data-stu-id="bf495-187">HttpClient and HttpContent extension methods</span></span>](../standard/serialization/system-text-json-how-to.md#httpclient-and-httpcontent-extension-methods)
- [<span data-ttu-id="bf495-188">Zezwalaj lub zapisuj liczby w cudzysłowach</span><span class="sxs-lookup"><span data-stu-id="bf495-188">Allow or write numbers in quotes</span></span>](../standard/serialization/system-text-json-how-to.md#allow-or-write-numbers-in-quotes)
- [<span data-ttu-id="bf495-189">Obsługa niemodyfikowalnych typów i rekordów C# 9</span><span class="sxs-lookup"><span data-stu-id="bf495-189">Support immutable types and C# 9 Records</span></span>](../standard/serialization/system-text-json-how-to.md#immutable-types-and-records)
- [<span data-ttu-id="bf495-190">Obsługa metod dostępu do właściwości niepublicznych</span><span class="sxs-lookup"><span data-stu-id="bf495-190">Support non-public property accessors</span></span>](../standard/serialization/system-text-json-how-to.md#non-public-property-accessors)
- [<span data-ttu-id="bf495-191">pola pomocy technicznej</span><span class="sxs-lookup"><span data-stu-id="bf495-191">support fields</span></span>](../standard/serialization/system-text-json-how-to.md#include-fields)
- [<span data-ttu-id="bf495-192">Ignoruj warunkowo właściwości</span><span class="sxs-lookup"><span data-stu-id="bf495-192">Conditionally ignore properties</span></span>](../standard/serialization/system-text-json-how-to.md#ignore-properties)
- [<span data-ttu-id="bf495-193">Obsługa słowników z kluczami niebędącymi ciągami</span><span class="sxs-lookup"><span data-stu-id="bf495-193">Support non-string-key dictionaries</span></span>](../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md#dictionary-with-non-string-key)
- [<span data-ttu-id="bf495-194">Zezwalaj na obsługę niestandardowych konwerterów o wartości null</span><span class="sxs-lookup"><span data-stu-id="bf495-194">Allow custom converters to handle null</span></span>](../standard/serialization/system-text-json-converters-how-to.md#handle-null-values)
- [<span data-ttu-id="bf495-195">Kopiuj JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="bf495-195">Copy JsonSerializerOptions</span></span>](../standard/serialization/system-text-json-how-to.md#copy-jsonserializeroptions)
- [<span data-ttu-id="bf495-196">Tworzenie JsonSerializerOptions przy użyciu ustawień domyślnych sieci Web</span><span class="sxs-lookup"><span data-stu-id="bf495-196">Create JsonSerializerOptions with web defaults</span></span>](../standard/serialization/system-text-json-how-to.md#web-defaults-for-jsonserializeroptions)

## <a name="see-also"></a><span data-ttu-id="bf495-197">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="bf495-197">See also</span></span>

- [<span data-ttu-id="bf495-198">Podróż do jednego programu .NET</span><span class="sxs-lookup"><span data-stu-id="bf495-198">The Journey to one .NET</span></span>](https://channel9.msdn.com/Events/Build/2020/BOD106)
- [<span data-ttu-id="bf495-199">Ulepszenia wydajności w programie .NET 5</span><span class="sxs-lookup"><span data-stu-id="bf495-199">Performance improvements in .NET 5</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)
- [<span data-ttu-id="bf495-200">Pobierz zestaw .NET SDK</span><span class="sxs-lookup"><span data-stu-id="bf495-200">Download the .NET SDK</span></span>](https://dotnet.microsoft.com/download)
