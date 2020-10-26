---
title: polecenie dotnet New
description: Polecenie dotnet New umożliwia tworzenie nowych projektów platformy .NET Core na podstawie określonego szablonu.
no-loc:
- Blazor
- WebAssembly
ms.date: 09/01/2020
ms.openlocfilehash: 4a4c8e2806fee663b5f6aa255a6f24250a072a85
ms.sourcegitcommit: 532b03d5bbab764d63356193b04cd2281bc01239
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2020
ms.locfileid: "92526619"
---
# <a name="dotnet-new"></a><span data-ttu-id="88907-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="88907-103">dotnet new</span></span>

<span data-ttu-id="88907-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,0 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="88907-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="88907-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="88907-105">Name</span></span>

<span data-ttu-id="88907-106">`dotnet new` -Tworzy nowy projekt, plik konfiguracji lub rozwiązanie na podstawie określonego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="88907-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="88907-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="88907-108">Opis</span><span class="sxs-lookup"><span data-stu-id="88907-108">Description</span></span>

<span data-ttu-id="88907-109">`dotnet new`Polecenie tworzy projekt .NET Core lub inne artefakty na podstawie szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="88907-110">Polecenie wywołuje [aparat szablonu](https://github.com/dotnet/templating) , aby utworzyć artefakty na dysku na podstawie określonego szablonu i opcji.</span><span class="sxs-lookup"><span data-stu-id="88907-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="88907-111">Przywracanie niejawne</span><span class="sxs-lookup"><span data-stu-id="88907-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="88907-112">Argumenty</span><span class="sxs-lookup"><span data-stu-id="88907-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="88907-113">Szablon do wystąpienia po wywołaniu polecenia.</span><span class="sxs-lookup"><span data-stu-id="88907-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="88907-114">Każdy szablon może mieć określone opcje, które można przekazać.</span><span class="sxs-lookup"><span data-stu-id="88907-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="88907-115">Aby uzyskać więcej informacji, zobacz [Opcje szablonu](#template-options).</span><span class="sxs-lookup"><span data-stu-id="88907-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="88907-116">Można uruchomić `dotnet new --list` lub `dotnet new -l` wyświetlić listę wszystkich zainstalowanych szablonów.</span><span class="sxs-lookup"><span data-stu-id="88907-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="88907-117">Jeśli `TEMPLATE` wartość nie jest dokładnym dopasowaniem do tekstu w kolumnie **Szablony** lub **krótka nazwa** z zwróconej tabeli, do tych dwóch kolumn jest wykonywane dopasowanie podciągu.</span><span class="sxs-lookup"><span data-stu-id="88907-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="88907-118">Począwszy od zestawu SDK platformy .NET Core 3,0, interfejs wiersza polecenia wyszukuje szablony w NuGet.org, gdy wywoła `dotnet new` polecenie w następujących warunkach:</span><span class="sxs-lookup"><span data-stu-id="88907-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="88907-119">Jeśli interfejs wiersza polecenia nie może znaleźć dopasowania szablonu podczas wywoływania `dotnet new` , nie nawet częściowej.</span><span class="sxs-lookup"><span data-stu-id="88907-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="88907-120">Jeśli jest dostępna nowsza wersja szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="88907-121">W takim przypadku projekt lub artefakt jest tworzony, ale interfejs wiersza polecenia ostrzega użytkownika o zaktualizowanej wersji szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="88907-122">W poniższej tabeli przedstawiono szablony, które są wstępnie zainstalowane wraz z zestaw .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="88907-123">Język domyślny dla szablonu jest pokazywany w nawiasach.</span><span class="sxs-lookup"><span data-stu-id="88907-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="88907-124">Kliknij link krótkiej nazwy, aby wyświetlić opcje konkretnego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="88907-125">Szablony</span><span class="sxs-lookup"><span data-stu-id="88907-125">Templates</span></span>                                    | <span data-ttu-id="88907-126">Krótka nazwa</span><span class="sxs-lookup"><span data-stu-id="88907-126">Short name</span></span>                      | <span data-ttu-id="88907-127">Język</span><span class="sxs-lookup"><span data-stu-id="88907-127">Language</span></span>     | <span data-ttu-id="88907-128">Tagi</span><span class="sxs-lookup"><span data-stu-id="88907-128">Tags</span></span>                                  | <span data-ttu-id="88907-129">Wprowadzono</span><span class="sxs-lookup"><span data-stu-id="88907-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="88907-130">Aplikacja konsoli</span><span class="sxs-lookup"><span data-stu-id="88907-130">Console Application</span></span>                          | [<span data-ttu-id="88907-131">konsoli</span><span class="sxs-lookup"><span data-stu-id="88907-131">console</span></span>](#console)             | <span data-ttu-id="88907-132">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="88907-132">[C#], F#, VB</span></span> | <span data-ttu-id="88907-133">Wspólna/konsola</span><span class="sxs-lookup"><span data-stu-id="88907-133">Common/Console</span></span>                        | <span data-ttu-id="88907-134">1.0</span><span class="sxs-lookup"><span data-stu-id="88907-134">1.0</span></span>        |
| <span data-ttu-id="88907-135">Biblioteka klas</span><span class="sxs-lookup"><span data-stu-id="88907-135">Class library</span></span>                                | [<span data-ttu-id="88907-136">określono</span><span class="sxs-lookup"><span data-stu-id="88907-136">classlib</span></span>](#classlib)           | <span data-ttu-id="88907-137">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="88907-137">[C#], F#, VB</span></span> | <span data-ttu-id="88907-138">Wspólna/Biblioteka</span><span class="sxs-lookup"><span data-stu-id="88907-138">Common/Library</span></span>                        | <span data-ttu-id="88907-139">1.0</span><span class="sxs-lookup"><span data-stu-id="88907-139">1.0</span></span>        |
| <span data-ttu-id="88907-140">Aplikacja WPF</span><span class="sxs-lookup"><span data-stu-id="88907-140">WPF Application</span></span>                              | [<span data-ttu-id="88907-141">kodow</span><span class="sxs-lookup"><span data-stu-id="88907-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="88907-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="88907-142">[C#], VB</span></span>     | <span data-ttu-id="88907-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="88907-143">Common/WPF</span></span>                            | <span data-ttu-id="88907-144">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="88907-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="88907-145">Biblioteka klas WPF</span><span class="sxs-lookup"><span data-stu-id="88907-145">WPF Class library</span></span>                            | [<span data-ttu-id="88907-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="88907-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="88907-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="88907-147">[C#], VB</span></span>     | <span data-ttu-id="88907-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="88907-148">Common/WPF</span></span>                            | <span data-ttu-id="88907-149">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="88907-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="88907-150">Biblioteka kontrolek niestandardowych WPF</span><span class="sxs-lookup"><span data-stu-id="88907-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="88907-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="88907-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="88907-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="88907-152">[C#], VB</span></span>     | <span data-ttu-id="88907-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="88907-153">Common/WPF</span></span>                            | <span data-ttu-id="88907-154">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="88907-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="88907-155">Biblioteka kontrolek użytkownika WPF</span><span class="sxs-lookup"><span data-stu-id="88907-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="88907-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="88907-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="88907-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="88907-157">[C#], VB</span></span>     | <span data-ttu-id="88907-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="88907-158">Common/WPF</span></span>                            | <span data-ttu-id="88907-159">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="88907-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="88907-160">Aplikacja Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="88907-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="88907-161">WinForms</span><span class="sxs-lookup"><span data-stu-id="88907-161">winforms</span></span>](#winforms)           | <span data-ttu-id="88907-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="88907-162">[C#], VB</span></span>     | <span data-ttu-id="88907-163">Typowe/WinForms</span><span class="sxs-lookup"><span data-stu-id="88907-163">Common/WinForms</span></span>                       | <span data-ttu-id="88907-164">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="88907-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="88907-165">Biblioteka klas Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="88907-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="88907-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="88907-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="88907-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="88907-167">[C#], VB</span></span>     | <span data-ttu-id="88907-168">Typowe/WinForms</span><span class="sxs-lookup"><span data-stu-id="88907-168">Common/WinForms</span></span>                       | <span data-ttu-id="88907-169">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="88907-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="88907-170">Usługa procesu roboczego</span><span class="sxs-lookup"><span data-stu-id="88907-170">Worker Service</span></span>                               | [<span data-ttu-id="88907-171">odpowiedzialn</span><span class="sxs-lookup"><span data-stu-id="88907-171">worker</span></span>](#web-others)           | <span data-ttu-id="88907-172">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-172">[C#]</span></span>         | <span data-ttu-id="88907-173">Common/Worker/sieć Web</span><span class="sxs-lookup"><span data-stu-id="88907-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="88907-174">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-174">3.0</span></span>        |
| <span data-ttu-id="88907-175">Projekt testu jednostkowego</span><span class="sxs-lookup"><span data-stu-id="88907-175">Unit Test Project</span></span>                            | [<span data-ttu-id="88907-176">MSTest</span><span class="sxs-lookup"><span data-stu-id="88907-176">mstest</span></span>](#test)                 | <span data-ttu-id="88907-177">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="88907-177">[C#], F#, VB</span></span> | <span data-ttu-id="88907-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="88907-178">Test/MSTest</span></span>                           | <span data-ttu-id="88907-179">1.0</span><span class="sxs-lookup"><span data-stu-id="88907-179">1.0</span></span>        |
| <span data-ttu-id="88907-180">Projekt testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="88907-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="88907-181">NUnit</span><span class="sxs-lookup"><span data-stu-id="88907-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="88907-182">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="88907-182">[C#], F#, VB</span></span> | <span data-ttu-id="88907-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="88907-183">Test/NUnit</span></span>                            | <span data-ttu-id="88907-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="88907-184">2.1.400</span></span>    |
| <span data-ttu-id="88907-185">Element testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="88907-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="88907-186">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="88907-186">[C#], F#, VB</span></span> | <span data-ttu-id="88907-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="88907-187">Test/NUnit</span></span>                            | <span data-ttu-id="88907-188">2.2</span><span class="sxs-lookup"><span data-stu-id="88907-188">2.2</span></span>        |
| <span data-ttu-id="88907-189">Projekt testu xUnit</span><span class="sxs-lookup"><span data-stu-id="88907-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="88907-190">xUnit</span><span class="sxs-lookup"><span data-stu-id="88907-190">xunit</span></span>](#test)                  | <span data-ttu-id="88907-191">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="88907-191">[C#], F#, VB</span></span> | <span data-ttu-id="88907-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="88907-192">Test/xUnit</span></span>                            | <span data-ttu-id="88907-193">1.0</span><span class="sxs-lookup"><span data-stu-id="88907-193">1.0</span></span>        |
| <span data-ttu-id="88907-194">Składnik Razor</span><span class="sxs-lookup"><span data-stu-id="88907-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="88907-195">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-195">[C#]</span></span>         | <span data-ttu-id="88907-196">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="88907-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="88907-197">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-197">3.0</span></span>        |
| <span data-ttu-id="88907-198">Strona Razor</span><span class="sxs-lookup"><span data-stu-id="88907-198">Razor Page</span></span>                                   | [<span data-ttu-id="88907-199">stronic</span><span class="sxs-lookup"><span data-stu-id="88907-199">page</span></span>](#page)                   | <span data-ttu-id="88907-200">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-200">[C#]</span></span>         | <span data-ttu-id="88907-201">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="88907-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="88907-202">2,0</span><span class="sxs-lookup"><span data-stu-id="88907-202">2.0</span></span>        |
| <span data-ttu-id="88907-203">ViewImports MVC</span><span class="sxs-lookup"><span data-stu-id="88907-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="88907-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="88907-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="88907-205">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-205">[C#]</span></span>         | <span data-ttu-id="88907-206">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="88907-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="88907-207">2,0</span><span class="sxs-lookup"><span data-stu-id="88907-207">2.0</span></span>        |
| <span data-ttu-id="88907-208">ViewStart MVC</span><span class="sxs-lookup"><span data-stu-id="88907-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="88907-209">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-209">[C#]</span></span>         | <span data-ttu-id="88907-210">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="88907-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="88907-211">2,0</span><span class="sxs-lookup"><span data-stu-id="88907-211">2.0</span></span>        |
| <span data-ttu-id="88907-212">Blazor Aplikacja serwera</span><span class="sxs-lookup"><span data-stu-id="88907-212">Blazor Server App</span></span>                            | [<span data-ttu-id="88907-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="88907-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="88907-214">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-214">[C#]</span></span>         | <span data-ttu-id="88907-215">WitrynęBlazor</span><span class="sxs-lookup"><span data-stu-id="88907-215">Web/Blazor</span></span>                            | <span data-ttu-id="88907-216">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-216">3.0</span></span>        |
| <span data-ttu-id="88907-217">BlazorWebAssemblyAplikacja</span><span class="sxs-lookup"><span data-stu-id="88907-217">Blazor WebAssembly App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="88907-218">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-218">[C#]</span></span>         | <span data-ttu-id="88907-219">WitrynęBlazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="88907-219">Web/Blazor/WebAssembly</span></span>                | <span data-ttu-id="88907-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="88907-220">3.1.300</span></span>    |
| <span data-ttu-id="88907-221">ASP.NET Core puste</span><span class="sxs-lookup"><span data-stu-id="88907-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="88907-222">witrynę</span><span class="sxs-lookup"><span data-stu-id="88907-222">web</span></span>](#web)                     | <span data-ttu-id="88907-223">[C#], F #</span><span class="sxs-lookup"><span data-stu-id="88907-223">[C#], F#</span></span>     | <span data-ttu-id="88907-224">Sieć Web/pusta</span><span class="sxs-lookup"><span data-stu-id="88907-224">Web/Empty</span></span>                             | <span data-ttu-id="88907-225">1.0</span><span class="sxs-lookup"><span data-stu-id="88907-225">1.0</span></span>        |
| <span data-ttu-id="88907-226">Aplikacja sieci Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="88907-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="88907-227">Standard</span><span class="sxs-lookup"><span data-stu-id="88907-227">mvc</span></span>](#web-options)             | <span data-ttu-id="88907-228">[C#], F #</span><span class="sxs-lookup"><span data-stu-id="88907-228">[C#], F#</span></span>     | <span data-ttu-id="88907-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="88907-229">Web/MVC</span></span>                               | <span data-ttu-id="88907-230">1.0</span><span class="sxs-lookup"><span data-stu-id="88907-230">1.0</span></span>        |
| <span data-ttu-id="88907-231">Aplikacja sieci Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="88907-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="88907-232">webapp, Razor</span><span class="sxs-lookup"><span data-stu-id="88907-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="88907-233">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-233">[C#]</span></span>         | <span data-ttu-id="88907-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="88907-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="88907-235">2,2, 2,0</span><span class="sxs-lookup"><span data-stu-id="88907-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="88907-236">ASP.NET Core ze Skośnością</span><span class="sxs-lookup"><span data-stu-id="88907-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="88907-237">kątow</span><span class="sxs-lookup"><span data-stu-id="88907-237">angular</span></span>](#spa)                 | <span data-ttu-id="88907-238">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-238">[C#]</span></span>         | <span data-ttu-id="88907-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="88907-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="88907-240">2,0</span><span class="sxs-lookup"><span data-stu-id="88907-240">2.0</span></span>        |
| <span data-ttu-id="88907-241">ASP.NET Core z React.js</span><span class="sxs-lookup"><span data-stu-id="88907-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="88907-242">biern</span><span class="sxs-lookup"><span data-stu-id="88907-242">react</span></span>](#spa)                   | <span data-ttu-id="88907-243">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-243">[C#]</span></span>         | <span data-ttu-id="88907-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="88907-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="88907-245">2,0</span><span class="sxs-lookup"><span data-stu-id="88907-245">2.0</span></span>        |
| <span data-ttu-id="88907-246">ASP.NET Core z React.js i Redux</span><span class="sxs-lookup"><span data-stu-id="88907-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="88907-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="88907-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="88907-248">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-248">[C#]</span></span>         | <span data-ttu-id="88907-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="88907-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="88907-250">2,0</span><span class="sxs-lookup"><span data-stu-id="88907-250">2.0</span></span>        |
| <span data-ttu-id="88907-251">Biblioteka klas Razor</span><span class="sxs-lookup"><span data-stu-id="88907-251">Razor Class Library</span></span>                          | [<span data-ttu-id="88907-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="88907-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="88907-253">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-253">[C#]</span></span>         | <span data-ttu-id="88907-254">Biblioteka klas sieci Web/Razor/Biblioteka/Razor</span><span class="sxs-lookup"><span data-stu-id="88907-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="88907-255">2.1</span><span class="sxs-lookup"><span data-stu-id="88907-255">2.1</span></span>        |
| <span data-ttu-id="88907-256">Internetowy interfejs API platformy ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="88907-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="88907-257">WebApi</span><span class="sxs-lookup"><span data-stu-id="88907-257">webapi</span></span>](#webapi)               | <span data-ttu-id="88907-258">[C#], F #</span><span class="sxs-lookup"><span data-stu-id="88907-258">[C#], F#</span></span>     | <span data-ttu-id="88907-259">Sieć Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="88907-259">Web/WebAPI</span></span>                            | <span data-ttu-id="88907-260">1.0</span><span class="sxs-lookup"><span data-stu-id="88907-260">1.0</span></span>        |
| <span data-ttu-id="88907-261">ASP.NET Core usługi gRPC</span><span class="sxs-lookup"><span data-stu-id="88907-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="88907-262">grpc</span><span class="sxs-lookup"><span data-stu-id="88907-262">grpc</span></span>](#web-others)             | <span data-ttu-id="88907-263">Znajd</span><span class="sxs-lookup"><span data-stu-id="88907-263">[C#]</span></span>         | <span data-ttu-id="88907-264">Sieć Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="88907-264">Web/gRPC</span></span>                              | <span data-ttu-id="88907-265">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-265">3.0</span></span>        |
| <span data-ttu-id="88907-266">plik GITIGNORE dotnet</span><span class="sxs-lookup"><span data-stu-id="88907-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="88907-267">Config</span><span class="sxs-lookup"><span data-stu-id="88907-267">Config</span></span>                                | <span data-ttu-id="88907-268">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-268">3.0</span></span>        |
| <span data-ttu-id="88907-269">global.jspliku</span><span class="sxs-lookup"><span data-stu-id="88907-269">global.json file</span></span>                             | [<span data-ttu-id="88907-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="88907-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="88907-271">Config</span><span class="sxs-lookup"><span data-stu-id="88907-271">Config</span></span>                                | <span data-ttu-id="88907-272">2,0</span><span class="sxs-lookup"><span data-stu-id="88907-272">2.0</span></span>        |
| <span data-ttu-id="88907-273">Konfiguracja narzędzia NuGet</span><span class="sxs-lookup"><span data-stu-id="88907-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="88907-274">Config</span><span class="sxs-lookup"><span data-stu-id="88907-274">Config</span></span>                                | <span data-ttu-id="88907-275">1.0</span><span class="sxs-lookup"><span data-stu-id="88907-275">1.0</span></span>        |
| <span data-ttu-id="88907-276">Plik manifestu narzędzia lokalnego dotnet</span><span class="sxs-lookup"><span data-stu-id="88907-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="88907-277">Config</span><span class="sxs-lookup"><span data-stu-id="88907-277">Config</span></span>                                | <span data-ttu-id="88907-278">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-278">3.0</span></span>        |
| <span data-ttu-id="88907-279">Konfiguracja sieci Web</span><span class="sxs-lookup"><span data-stu-id="88907-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="88907-280">Config</span><span class="sxs-lookup"><span data-stu-id="88907-280">Config</span></span>                                | <span data-ttu-id="88907-281">1.0</span><span class="sxs-lookup"><span data-stu-id="88907-281">1.0</span></span>        |
| <span data-ttu-id="88907-282">Plik rozwiązania</span><span class="sxs-lookup"><span data-stu-id="88907-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="88907-283">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="88907-283">Solution</span></span>                              | <span data-ttu-id="88907-284">1.0</span><span class="sxs-lookup"><span data-stu-id="88907-284">1.0</span></span>        |
| <span data-ttu-id="88907-285">Plik buforu protokołu</span><span class="sxs-lookup"><span data-stu-id="88907-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="88907-286">proto</span><span class="sxs-lookup"><span data-stu-id="88907-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="88907-287">Sieć Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="88907-287">Web/gRPC</span></span>                              | <span data-ttu-id="88907-288">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="88907-289">Opcje</span><span class="sxs-lookup"><span data-stu-id="88907-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="88907-290">Wyświetla podsumowanie tego, co się stanie w przypadku uruchomienia danego polecenia, jeśli mogłoby to spowodować utworzenie szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="88907-291">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="88907-292">Wymusza wygenerowanie zawartości nawet w przypadku zmiany istniejących plików.</span><span class="sxs-lookup"><span data-stu-id="88907-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="88907-293">Jest to wymagane, gdy wybrany szablon spowoduje zastąpienie istniejących plików w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="88907-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="88907-294">Drukuje pomoc dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="88907-294">Prints out help for the command.</span></span> <span data-ttu-id="88907-295">Może być wywoływana dla `dotnet new` samego polecenia lub dla dowolnego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="88907-296">Na przykład `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="88907-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="88907-297">Instaluje pakiet szablonów z `PATH` lub `NUGET_ID` dostarczone.</span><span class="sxs-lookup"><span data-stu-id="88907-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="88907-298">Jeśli chcesz zainstalować wersję wstępną pakietu szablonu, musisz określić wersję w formacie `<package-name>::<package-version>` .</span><span class="sxs-lookup"><span data-stu-id="88907-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="88907-299">Domyślnie program `dotnet new` przekazuje \* wersję, która reprezentuje najnowszą stabilną wersję pakietu.</span><span class="sxs-lookup"><span data-stu-id="88907-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="88907-300">Zobacz przykład w sekcji [przykładów](#examples) .</span><span class="sxs-lookup"><span data-stu-id="88907-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="88907-301">Jeśli wersja szablonu została już zainstalowana po uruchomieniu tego polecenia, szablon zostanie zaktualizowany do określonej wersji lub do najnowszej wersji stabilnej, jeśli nie określono żadnej wersji.</span><span class="sxs-lookup"><span data-stu-id="88907-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="88907-302">Aby uzyskać informacje na temat tworzenia szablonów niestandardowych, zobacz [Szablony niestandardowe dla usługi dotnet New](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="88907-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="88907-303">Wyświetla listę szablonów zawierających określoną nazwę.</span><span class="sxs-lookup"><span data-stu-id="88907-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="88907-304">Jeśli nazwa nie zostanie określona, program wyświetli listę wszystkich szablonów.</span><span class="sxs-lookup"><span data-stu-id="88907-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="88907-305">Język szablonu do utworzenia.</span><span class="sxs-lookup"><span data-stu-id="88907-305">The language of the template to create.</span></span> <span data-ttu-id="88907-306">Zaakceptowany język zależy od szablonu (zobacz wartości domyślne w sekcji [argumenty](#arguments) ).</span><span class="sxs-lookup"><span data-stu-id="88907-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="88907-307">Nieprawidłowy dla niektórych szablonów.</span><span class="sxs-lookup"><span data-stu-id="88907-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="88907-308">Niektóre powłoki interpretują `#` jako znak specjalny.</span><span class="sxs-lookup"><span data-stu-id="88907-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="88907-309">W takich przypadkach należy ująć wartość parametru Language w cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="88907-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="88907-310">Na przykład `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="88907-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="88907-311">Nazwa dla utworzonych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="88907-311">The name for the created output.</span></span> <span data-ttu-id="88907-312">Jeśli nazwa nie zostanie określona, zostanie użyta nazwa bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="88907-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="88907-313">Określa źródło NuGet do użycia podczas instalacji.</span><span class="sxs-lookup"><span data-stu-id="88907-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="88907-314">Dostępne od wersji .NET Core 2,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="88907-315">Lokalizacja, w której mają zostać umieszczone wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="88907-315">Location to place the generated output.</span></span> <span data-ttu-id="88907-316">Ustawieniem domyślnym jest bieżący katalog.</span><span class="sxs-lookup"><span data-stu-id="88907-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="88907-317">Filtruje szablony w oparciu o dostępne typy.</span><span class="sxs-lookup"><span data-stu-id="88907-317">Filters templates based on available types.</span></span> <span data-ttu-id="88907-318">Wstępnie zdefiniowane wartości to `project` i `item` .</span><span class="sxs-lookup"><span data-stu-id="88907-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="88907-319">Odinstalowuje pakiet szablonów w `PATH` lub `NUGET_ID` udostępniony.</span><span class="sxs-lookup"><span data-stu-id="88907-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="88907-320">Gdy `<PATH|NUGET_ID>` wartość nie jest określona, wyświetlane są wszystkie aktualnie zainstalowane pakiety szablonów i skojarzone z nimi szablony.</span><span class="sxs-lookup"><span data-stu-id="88907-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="88907-321">Podczas określania `NUGET_ID` nie należy umieszczać numeru wersji.</span><span class="sxs-lookup"><span data-stu-id="88907-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="88907-322">Jeśli nie określisz parametru do tej opcji, polecenie wyświetli listę zainstalowanych szablonów i szczegółowe informacje o nich.</span><span class="sxs-lookup"><span data-stu-id="88907-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="88907-323">Aby odinstalować szablon przy użyciu programu `PATH` , należy w pełni zakwalifikować ścieżkę.</span><span class="sxs-lookup"><span data-stu-id="88907-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="88907-324">Na przykład *C:/Users/ \<USER> /Documents/templates/GarciaSoftware.ConsoleTemplate.CSharp* będzie działał, ale *./GarciaSoftware.ConsoleTemplate.CSharp* z folderu zawierającego nie będzie.</span><span class="sxs-lookup"><span data-stu-id="88907-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="88907-325">Nie dołączaj ostatecznego ukośnika katalogu w ścieżce szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="88907-326">Sprawdza, czy są dostępne aktualizacje pakietów szablonów, które są obecnie zainstalowane i instaluje je.</span><span class="sxs-lookup"><span data-stu-id="88907-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="88907-327">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="88907-328">Sprawdza, czy są dostępne aktualizacje pakietów szablonów, które są obecnie zainstalowane.</span><span class="sxs-lookup"><span data-stu-id="88907-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="88907-329">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="88907-330">Opcje szablonu</span><span class="sxs-lookup"><span data-stu-id="88907-330">Template options</span></span>

<span data-ttu-id="88907-331">Każdy szablon projektu może mieć dodatkowe opcje dostępne.</span><span class="sxs-lookup"><span data-stu-id="88907-331">Each project template may have additional options available.</span></span> <span data-ttu-id="88907-332">Szablony podstawowe mają następujące dodatkowe opcje:</span><span class="sxs-lookup"><span data-stu-id="88907-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="88907-333">console</span><span class="sxs-lookup"><span data-stu-id="88907-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="88907-334">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="88907-335">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="88907-336">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="88907-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="88907-337">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="88907-337">SDK version</span></span> | <span data-ttu-id="88907-338">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="88907-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="88907-339">3,1</span><span class="sxs-lookup"><span data-stu-id="88907-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="88907-340">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="88907-341">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="88907-342">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="88907-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="88907-343">Nieobsługiwane dla języka F #.</span><span class="sxs-lookup"><span data-stu-id="88907-343">Not supported for F#.</span></span> <span data-ttu-id="88907-344">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="88907-345">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="88907-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="88907-346">Jeśli określony, nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="88907-347">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-347">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="88907-348">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-348">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="88907-349">określono</span><span class="sxs-lookup"><span data-stu-id="88907-349">classlib</span></span>

- <span data-ttu-id="88907-350">_*`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-350">_*`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="88907-351">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-351">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="88907-352">Wartości: `netcoreapp<version>` Aby utworzyć bibliotekę klas platformy .NET Core lub `netstandard<version>` utworzyć bibliotekę klas .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="88907-352">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="88907-353">Wartość domyślna to `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="88907-353">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="88907-354">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-354">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="88907-355">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="88907-355">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="88907-356">Nieobsługiwane dla języka F #.</span><span class="sxs-lookup"><span data-stu-id="88907-356">Not supported for F#.</span></span> <span data-ttu-id="88907-357">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-357">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="88907-358">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="88907-358">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="88907-359">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-359">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="88907-360">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-360">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="88907-361">WPF, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="88907-361">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="88907-362">_*`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-362">_*`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="88907-363">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-363">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="88907-364">Wartość domyślna to `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="88907-364">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="88907-365">Dostępne od wersji .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-365">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="88907-366">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-366">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="88907-367">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="88907-367">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="88907-368">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="88907-368">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="88907-369">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-369">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="88907-370">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-370">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="88907-371">WinForms, winformslib</span><span class="sxs-lookup"><span data-stu-id="88907-371">winforms, winformslib</span></span>

- <span data-ttu-id="88907-372">_*`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-372">_*`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="88907-373">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-373">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="88907-374">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="88907-374">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="88907-375">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="88907-375">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="88907-376">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-376">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="88907-377">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-377">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="88907-378">proces roboczy, GRPC</span><span class="sxs-lookup"><span data-stu-id="88907-378">worker, grpc</span></span>

- <span data-ttu-id="88907-379">_*`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-379">_*`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="88907-380">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-380">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="88907-381">Wartość domyślna to `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="88907-381">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="88907-382">Dostępne od wersji .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-382">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="88907-383">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-383">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="88907-384">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-384">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="88907-385">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-385">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="88907-386">MSTest, xUnit</span><span class="sxs-lookup"><span data-stu-id="88907-386">mstest, xunit</span></span>

- <span data-ttu-id="88907-387">_*`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-387">_*`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="88907-388">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="88907-389">Opcja dostępna od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-389">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="88907-390">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="88907-390">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="88907-391">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="88907-391">SDK version</span></span> | <span data-ttu-id="88907-392">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="88907-392">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="88907-393">3,1</span><span class="sxs-lookup"><span data-stu-id="88907-393">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="88907-394">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-394">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="88907-395">Włącza pakowanie dla projektu przy użyciu [pakietu dotnet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="88907-395">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="88907-396">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-396">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="88907-397">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-397">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="88907-398">NUnit</span><span class="sxs-lookup"><span data-stu-id="88907-398">nunit</span></span>

- <span data-ttu-id="88907-399">_*`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-399">_*`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="88907-400">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-400">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="88907-401">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="88907-401">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="88907-402">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="88907-402">SDK version</span></span> | <span data-ttu-id="88907-403">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="88907-403">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="88907-404">3,1</span><span class="sxs-lookup"><span data-stu-id="88907-404">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="88907-405">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-405">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="88907-406">2.2</span><span class="sxs-lookup"><span data-stu-id="88907-406">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="88907-407">2.1</span><span class="sxs-lookup"><span data-stu-id="88907-407">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="88907-408">Włącza pakowanie dla projektu przy użyciu [pakietu dotnet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="88907-408">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="88907-409">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-409">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="88907-410">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-410">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="88907-411">stronic</span><span class="sxs-lookup"><span data-stu-id="88907-411">page</span></span>

- <span data-ttu-id="88907-412">_*`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-412">_*`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="88907-413">Przestrzeń nazw dla wygenerowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="88907-413">Namespace for the generated code.</span></span> <span data-ttu-id="88907-414">Wartość domyślna to `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="88907-414">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="88907-415">Tworzy stronę bez PageModel.</span><span class="sxs-lookup"><span data-stu-id="88907-415">Creates the page without a PageModel.</span></span>

<span data-ttu-id="88907-416">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-416">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="88907-417">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="88907-417">viewimports, proto</span></span>

- <span data-ttu-id="88907-418">_*`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-418">_*`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="88907-419">Przestrzeń nazw dla wygenerowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="88907-419">Namespace for the generated code.</span></span> <span data-ttu-id="88907-420">Wartość domyślna to `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="88907-420">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="88907-421">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-421">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="88907-422">blazorserver</span><span class="sxs-lookup"><span data-stu-id="88907-422">blazorserver</span></span>

- <span data-ttu-id="88907-423">_*`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-423">_*`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="88907-424">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="88907-424">The type of authentication to use.</span></span> <span data-ttu-id="88907-425">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="88907-425">The possible values are:</span></span>

  - <span data-ttu-id="88907-426">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="88907-426">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="88907-427">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="88907-427">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="88907-428">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="88907-428">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="88907-429">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="88907-429">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="88907-430">`MultiOrg` -Organizacja uwierzytelnianie dla wielu dzierżawców.</span><span class="sxs-lookup"><span data-stu-id="88907-430">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="88907-431">`Windows` — Uwierzytelnianie systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="88907-431">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="88907-432">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="88907-432">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="88907-433">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-433">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="88907-434">Wartość domyślna to `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="88907-434">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="88907-435">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-435">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="88907-436">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-436">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="88907-437">Identyfikator zasad resetowania hasła dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-437">The reset password policy ID for this project.</span></span> <span data-ttu-id="88907-438">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-438">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="88907-439">Edytuj identyfikator zasad profilu dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-439">The edit profile policy ID for this project.</span></span> <span data-ttu-id="88907-440">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-440">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="88907-441">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="88907-441">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="88907-442">Używanie z usługą `SingleOrg` lub `MultiOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-442">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="88907-443">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="88907-443">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="88907-444">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-444">The Client ID for this project.</span></span> <span data-ttu-id="88907-445">Użyj z `IndividualB2C` , `SingleOrg` lub `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="88907-445">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="88907-446">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="88907-446">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="88907-447">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="88907-447">The domain for the directory tenant.</span></span> <span data-ttu-id="88907-448">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-448">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="88907-449">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="88907-449">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="88907-450">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="88907-450">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="88907-451">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-451">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="88907-452">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="88907-452">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="88907-453">Ścieżka żądania w ścieżce podstawowej identyfikatora URI przekierowania.</span><span class="sxs-lookup"><span data-stu-id="88907-453">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="88907-454">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-454">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="88907-455">Wartość domyślna to `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="88907-455">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="88907-456">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="88907-456">Allows this application read-access to the directory.</span></span> <span data-ttu-id="88907-457">Dotyczy tylko `SingleOrg` `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="88907-457">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="88907-458">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-458">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="88907-459">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88907-459">Turns off HTTPS.</span></span> <span data-ttu-id="88907-460">Ta opcja ma zastosowanie tylko wtedy, gdy,, `Individual` `IndividualB2C` `SingleOrg` lub `MultiOrg` nie są używane w programie `--auth` .</span><span class="sxs-lookup"><span data-stu-id="88907-460">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="88907-461">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="88907-461">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="88907-462">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="88907-462">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="88907-463">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-463">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="88907-464">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-464">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="88907-465">web</span><span class="sxs-lookup"><span data-stu-id="88907-465">web</span></span>

- <span data-ttu-id="88907-466">_*`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-466">_*`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="88907-467">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-467">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="88907-468">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-468">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="88907-469">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="88907-469">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="88907-470">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="88907-470">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="88907-471">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="88907-471">SDK version</span></span> | <span data-ttu-id="88907-472">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="88907-472">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="88907-473">3,1</span><span class="sxs-lookup"><span data-stu-id="88907-473">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="88907-474">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-474">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="88907-475">2.1</span><span class="sxs-lookup"><span data-stu-id="88907-475">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="88907-476">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="88907-477">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88907-477">Turns off HTTPS.</span></span>

<span data-ttu-id="88907-478">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-478">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="88907-479">MVC, webapp</span><span class="sxs-lookup"><span data-stu-id="88907-479">mvc, webapp</span></span>

- <span data-ttu-id="88907-480">_*`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-480">_*`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="88907-481">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="88907-481">The type of authentication to use.</span></span> <span data-ttu-id="88907-482">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="88907-482">The possible values are:</span></span>

  - <span data-ttu-id="88907-483">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="88907-483">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="88907-484">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="88907-484">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="88907-485">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="88907-485">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="88907-486">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="88907-486">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="88907-487">`MultiOrg` -Organizacja uwierzytelnianie dla wielu dzierżawców.</span><span class="sxs-lookup"><span data-stu-id="88907-487">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="88907-488">`Windows` — Uwierzytelnianie systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="88907-488">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="88907-489">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="88907-489">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="88907-490">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-490">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="88907-491">Wartość domyślna to `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="88907-491">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="88907-492">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-492">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="88907-493">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-493">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="88907-494">Identyfikator zasad resetowania hasła dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-494">The reset password policy ID for this project.</span></span> <span data-ttu-id="88907-495">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-495">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="88907-496">Edytuj identyfikator zasad profilu dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-496">The edit profile policy ID for this project.</span></span> <span data-ttu-id="88907-497">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-497">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="88907-498">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="88907-498">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="88907-499">Używanie z usługą `SingleOrg` lub `MultiOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-499">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="88907-500">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="88907-500">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="88907-501">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-501">The Client ID for this project.</span></span> <span data-ttu-id="88907-502">Użyj z `IndividualB2C` , `SingleOrg` lub `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="88907-502">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="88907-503">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="88907-503">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="88907-504">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="88907-504">The domain for the directory tenant.</span></span> <span data-ttu-id="88907-505">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="88907-506">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="88907-506">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="88907-507">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="88907-507">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="88907-508">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-508">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="88907-509">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="88907-509">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="88907-510">Ścieżka żądania w ścieżce podstawowej identyfikatora URI przekierowania.</span><span class="sxs-lookup"><span data-stu-id="88907-510">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="88907-511">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-511">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="88907-512">Wartość domyślna to `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="88907-512">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="88907-513">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="88907-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="88907-514">Dotyczy tylko `SingleOrg` `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="88907-514">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="88907-515">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="88907-516">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88907-516">Turns off HTTPS.</span></span> <span data-ttu-id="88907-517">Ta opcja ma zastosowanie tylko wtedy, gdy,, `Individual` `IndividualB2C` `SingleOrg` lub `MultiOrg` nie jest używany.</span><span class="sxs-lookup"><span data-stu-id="88907-517">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="88907-518">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="88907-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="88907-519">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="88907-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="88907-520">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-520">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="88907-521">Opcja dostępna od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-521">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="88907-522">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="88907-522">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="88907-523">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="88907-523">SDK version</span></span> | <span data-ttu-id="88907-524">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="88907-524">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="88907-525">3,1</span><span class="sxs-lookup"><span data-stu-id="88907-525">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="88907-526">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-526">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="88907-527">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-527">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="88907-528">Zawiera BrowserLink w projekcie.</span><span class="sxs-lookup"><span data-stu-id="88907-528">Includes BrowserLink in the project.</span></span> <span data-ttu-id="88907-529">Opcja nie jest dostępna w programie .NET Core 2,2 i 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-529">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="88907-530">Określa, czy projekt jest skonfigurowany do używania [kompilacji środowiska uruchomieniowego Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) w kompilacjach debugowania.</span><span class="sxs-lookup"><span data-stu-id="88907-530">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="88907-531">Opcja dostępna od wersji .NET Core 3.1.201 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-531">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="88907-532">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-532">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="88907-533">kątowy, reagowanie</span><span class="sxs-lookup"><span data-stu-id="88907-533">angular, react</span></span>

- <span data-ttu-id="88907-534">_*`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-534">_*`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="88907-535">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="88907-535">The type of authentication to use.</span></span> <span data-ttu-id="88907-536">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-536">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="88907-537">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="88907-537">The possible values are:</span></span>

  - <span data-ttu-id="88907-538">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="88907-538">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="88907-539">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="88907-539">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="88907-540">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-540">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="88907-541">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="88907-542">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88907-542">Turns off HTTPS.</span></span> <span data-ttu-id="88907-543">Ta opcja ma zastosowanie tylko wtedy, gdy uwierzytelnianie jest `None` .</span><span class="sxs-lookup"><span data-stu-id="88907-543">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="88907-544">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="88907-544">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="88907-545">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="88907-545">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="88907-546">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-546">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="88907-547">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-547">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="88907-548">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="88907-548">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="88907-549">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="88907-549">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="88907-550">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="88907-550">SDK version</span></span> | <span data-ttu-id="88907-551">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="88907-551">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="88907-552">3,1</span><span class="sxs-lookup"><span data-stu-id="88907-552">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="88907-553">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-553">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="88907-554">2.1</span><span class="sxs-lookup"><span data-stu-id="88907-554">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="88907-555">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-555">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="88907-556">reactredux</span><span class="sxs-lookup"><span data-stu-id="88907-556">reactredux</span></span>

- <span data-ttu-id="88907-557">_*`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-557">_*`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="88907-558">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-558">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="88907-559">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-559">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="88907-560">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="88907-560">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="88907-561">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="88907-561">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="88907-562">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="88907-562">SDK version</span></span> | <span data-ttu-id="88907-563">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="88907-563">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="88907-564">3,1</span><span class="sxs-lookup"><span data-stu-id="88907-564">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="88907-565">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-565">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="88907-566">2.1</span><span class="sxs-lookup"><span data-stu-id="88907-566">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="88907-567">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-567">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="88907-568">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88907-568">Turns off HTTPS.</span></span>

<span data-ttu-id="88907-569">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-569">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="88907-570">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="88907-570">razorclasslib</span></span>

- <span data-ttu-id="88907-571">_*`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-571">_*`--no-restore`*\*</span></span>

  <span data-ttu-id="88907-572">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-572">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="88907-573">Obsługuje dodawanie tradycyjnych stron Razor i widoków oprócz składników do tej biblioteki.</span><span class="sxs-lookup"><span data-stu-id="88907-573">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="88907-574">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="88907-574">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="88907-575">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-575">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="88907-576">WebApi</span><span class="sxs-lookup"><span data-stu-id="88907-576">webapi</span></span>

- <span data-ttu-id="88907-577">_*`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-577">_*`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="88907-578">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="88907-578">The type of authentication to use.</span></span> <span data-ttu-id="88907-579">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="88907-579">The possible values are:</span></span>

  - <span data-ttu-id="88907-580">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="88907-580">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="88907-581">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="88907-581">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="88907-582">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="88907-582">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="88907-583">`Windows` — Uwierzytelnianie systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="88907-583">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="88907-584">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="88907-584">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="88907-585">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-585">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="88907-586">Wartość domyślna to `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="88907-586">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="88907-587">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-587">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="88907-588">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-588">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="88907-589">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="88907-589">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="88907-590">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-590">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="88907-591">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="88907-591">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="88907-592">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-592">The Client ID for this project.</span></span> <span data-ttu-id="88907-593">Używanie z usługą `IndividualB2C` lub `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-593">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="88907-594">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="88907-594">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="88907-595">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="88907-595">The domain for the directory tenant.</span></span> <span data-ttu-id="88907-596">Używanie z usługą `IndividualB2C` lub `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-596">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="88907-597">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="88907-597">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="88907-598">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="88907-598">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="88907-599">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="88907-599">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="88907-600">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="88907-600">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="88907-601">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="88907-601">Allows this application read-access to the directory.</span></span> <span data-ttu-id="88907-602">Dotyczy tylko `SingleOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="88907-602">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="88907-603">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88907-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="88907-604">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88907-604">Turns off HTTPS.</span></span> <span data-ttu-id="88907-605">`app.UseHsts` i `app.UseHttpsRedirection` nie są dodawane do `Startup.Configure` .</span><span class="sxs-lookup"><span data-stu-id="88907-605">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="88907-606">Ta opcja ma zastosowanie tylko wtedy `IndividualB2C` , gdy lub `SingleOrg` nie są używane do uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="88907-606">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="88907-607">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="88907-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="88907-608">Dotyczy tylko `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="88907-608">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="88907-609">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="88907-609">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="88907-610">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="88907-610">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="88907-611">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="88907-611">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="88907-612">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="88907-612">SDK version</span></span> | <span data-ttu-id="88907-613">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="88907-613">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="88907-614">3,1</span><span class="sxs-lookup"><span data-stu-id="88907-614">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="88907-615">3.0</span><span class="sxs-lookup"><span data-stu-id="88907-615">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="88907-616">2.1</span><span class="sxs-lookup"><span data-stu-id="88907-616">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="88907-617">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="88907-617">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="88907-618">\*\*_</span><span class="sxs-lookup"><span data-stu-id="88907-618">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="88907-619">globaljson</span><span class="sxs-lookup"><span data-stu-id="88907-619">globaljson</span></span>

- <span data-ttu-id="88907-620">_*`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="88907-620">_*`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="88907-621">Określa wersję zestaw .NET Core SDK, która ma być używana w *global.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="88907-621">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="88907-622">Przykłady</span><span class="sxs-lookup"><span data-stu-id="88907-622">Examples</span></span>

- <span data-ttu-id="88907-623">Utwórz projekt aplikacji konsolowej w języku C#, określając nazwę szablonu:</span><span class="sxs-lookup"><span data-stu-id="88907-623">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="88907-624">Utwórz projekt aplikacji konsolowej F # w bieżącym katalogu:</span><span class="sxs-lookup"><span data-stu-id="88907-624">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="88907-625">Utwórz projekt biblioteki klas .NET Standard w określonym katalogu:</span><span class="sxs-lookup"><span data-stu-id="88907-625">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="88907-626">Utwórz nowy projekt ASP.NET Core C# MVC w bieżącym katalogu bez uwierzytelniania:</span><span class="sxs-lookup"><span data-stu-id="88907-626">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="88907-627">Utwórz nowy projekt xUnit:</span><span class="sxs-lookup"><span data-stu-id="88907-627">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="88907-628">Wyświetl listę wszystkich szablonów dostępnych dla szablonów aplikacji jednostronicowych (SPA):</span><span class="sxs-lookup"><span data-stu-id="88907-628">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="88907-629">Wyświetl listę wszystkich szablonów pasujących *do* podciągu.</span><span class="sxs-lookup"><span data-stu-id="88907-629">List all templates matching the *we* substring.</span></span> <span data-ttu-id="88907-630">Nie znaleziono dokładnego dopasowania, więc Dopasowywanie podciągów działa w odniesieniu do kolumn krótkich nazw i nazw.</span><span class="sxs-lookup"><span data-stu-id="88907-630">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="88907-631">Podjęto próbę wywołania szablonu zgodnego z parametrem *ng*.</span><span class="sxs-lookup"><span data-stu-id="88907-631">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="88907-632">Jeśli nie można ustalić pojedynczego dopasowania, należy wyświetlić listę szablonów, które są dopasowań częściowych.</span><span class="sxs-lookup"><span data-stu-id="88907-632">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="88907-633">Zainstaluj wersję 2,0 szablonów SPA dla ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="88907-633">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="88907-634">Wyświetl listę zainstalowanych szablonów i szczegółowe informacje o nich, w tym sposoby ich odinstalowywania:</span><span class="sxs-lookup"><span data-stu-id="88907-634">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="88907-635">Utwórz *global.js* w bieżącym katalogu, ustawiając wersję zestawu SDK na 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="88907-635">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="88907-636">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="88907-636">See also</span></span>

- [<span data-ttu-id="88907-637">Szablony niestandardowe dla nowego dotnet</span><span class="sxs-lookup"><span data-stu-id="88907-637">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="88907-638">Tworzenie szablonu niestandardowego dla polecenia dotnet new</span><span class="sxs-lookup"><span data-stu-id="88907-638">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="88907-639">dotnet/dotnet-Template-przykłady repozytorium GitHub</span><span class="sxs-lookup"><span data-stu-id="88907-639">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="88907-640">Dostępne szablony dla nowego dotnet</span><span class="sxs-lookup"><span data-stu-id="88907-640">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
