---
title: polecenie dotnet New
description: Polecenie dotnet New umożliwia tworzenie nowych projektów platformy .NET na podstawie określonego szablonu.
no-loc:
- 'Blazor'
- 'WebAssembly'
ms.date: 09/04/2020
ms.openlocfilehash: 3ee644f05ea5929ffc7b11054ef1d974b811f418
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634458"
---
# <a name="dotnet-new"></a><span data-ttu-id="73d5e-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="73d5e-103">dotnet new</span></span>

<span data-ttu-id="73d5e-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,0 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="73d5e-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="73d5e-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="73d5e-105">Name</span></span>

<span data-ttu-id="73d5e-106">`dotnet new` -Tworzy nowy projekt, plik konfiguracji lub rozwiązanie na podstawie określonego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="73d5e-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="73d5e-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="73d5e-108">Opis</span><span class="sxs-lookup"><span data-stu-id="73d5e-108">Description</span></span>

<span data-ttu-id="73d5e-109">`dotnet new`Polecenie tworzy projekt .NET lub inne artefakty na podstawie szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-109">The `dotnet new` command creates a .NET project or other artifacts based on a template.</span></span>

<span data-ttu-id="73d5e-110">Polecenie wywołuje [aparat szablonu](https://github.com/dotnet/templating) , aby utworzyć artefakty na dysku na podstawie określonego szablonu i opcji.</span><span class="sxs-lookup"><span data-stu-id="73d5e-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="73d5e-111">Przywracanie niejawne</span><span class="sxs-lookup"><span data-stu-id="73d5e-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="73d5e-112">Argumenty</span><span class="sxs-lookup"><span data-stu-id="73d5e-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="73d5e-113">Szablon do wystąpienia po wywołaniu polecenia.</span><span class="sxs-lookup"><span data-stu-id="73d5e-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="73d5e-114">Każdy szablon może mieć określone opcje, które można przekazać.</span><span class="sxs-lookup"><span data-stu-id="73d5e-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="73d5e-115">Aby uzyskać więcej informacji, zobacz [Opcje szablonu](#template-options).</span><span class="sxs-lookup"><span data-stu-id="73d5e-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="73d5e-116">Można uruchomić `dotnet new --list` lub `dotnet new -l` wyświetlić listę wszystkich zainstalowanych szablonów.</span><span class="sxs-lookup"><span data-stu-id="73d5e-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="73d5e-117">Jeśli `TEMPLATE` wartość nie jest dokładnym dopasowaniem do tekstu w kolumnie **Szablony** lub **krótka nazwa** z zwróconej tabeli, do tych dwóch kolumn jest wykonywane dopasowanie podciągu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="73d5e-118">Począwszy od zestawu SDK platformy .NET Core 3,0, interfejs wiersza polecenia wyszukuje szablony w NuGet.org, gdy wywoła `dotnet new` polecenie w następujących warunkach:</span><span class="sxs-lookup"><span data-stu-id="73d5e-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="73d5e-119">Jeśli interfejs wiersza polecenia nie może znaleźć dopasowania szablonu podczas wywoływania `dotnet new` , nie nawet częściowej.</span><span class="sxs-lookup"><span data-stu-id="73d5e-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="73d5e-120">Jeśli jest dostępna nowsza wersja szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="73d5e-121">W takim przypadku projekt lub artefakt jest tworzony, ale interfejs wiersza polecenia ostrzega użytkownika o zaktualizowanej wersji szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="73d5e-122">W poniższej tabeli przedstawiono szablony, które są wstępnie zainstalowane przy użyciu zestawu .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-122">The following table shows the templates that come pre-installed with the .NET SDK.</span></span> <span data-ttu-id="73d5e-123">Język domyślny dla szablonu jest pokazywany w nawiasach.</span><span class="sxs-lookup"><span data-stu-id="73d5e-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="73d5e-124">Kliknij link krótkiej nazwy, aby wyświetlić opcje konkretnego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="73d5e-125">Szablony</span><span class="sxs-lookup"><span data-stu-id="73d5e-125">Templates</span></span>                                    | <span data-ttu-id="73d5e-126">Krótka nazwa</span><span class="sxs-lookup"><span data-stu-id="73d5e-126">Short name</span></span>                      | <span data-ttu-id="73d5e-127">Język</span><span class="sxs-lookup"><span data-stu-id="73d5e-127">Language</span></span>     | <span data-ttu-id="73d5e-128">Tagi</span><span class="sxs-lookup"><span data-stu-id="73d5e-128">Tags</span></span>                                  | <span data-ttu-id="73d5e-129">Wprowadzono</span><span class="sxs-lookup"><span data-stu-id="73d5e-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="73d5e-130">Aplikacja konsoli</span><span class="sxs-lookup"><span data-stu-id="73d5e-130">Console Application</span></span>                          | [<span data-ttu-id="73d5e-131">konsoli</span><span class="sxs-lookup"><span data-stu-id="73d5e-131">console</span></span>](#console)             | <span data-ttu-id="73d5e-132">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-132">[C#], F#, VB</span></span> | <span data-ttu-id="73d5e-133">Wspólna/konsola</span><span class="sxs-lookup"><span data-stu-id="73d5e-133">Common/Console</span></span>                        | <span data-ttu-id="73d5e-134">1,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-134">1.0</span></span>        |
| <span data-ttu-id="73d5e-135">Biblioteka klas</span><span class="sxs-lookup"><span data-stu-id="73d5e-135">Class library</span></span>                                | [<span data-ttu-id="73d5e-136">określono</span><span class="sxs-lookup"><span data-stu-id="73d5e-136">classlib</span></span>](#classlib)           | <span data-ttu-id="73d5e-137">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-137">[C#], F#, VB</span></span> | <span data-ttu-id="73d5e-138">Wspólna/Biblioteka</span><span class="sxs-lookup"><span data-stu-id="73d5e-138">Common/Library</span></span>                        | <span data-ttu-id="73d5e-139">1,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-139">1.0</span></span>        |
| <span data-ttu-id="73d5e-140">Aplikacja WPF</span><span class="sxs-lookup"><span data-stu-id="73d5e-140">WPF Application</span></span>                              | [<span data-ttu-id="73d5e-141">kodow</span><span class="sxs-lookup"><span data-stu-id="73d5e-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="73d5e-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-142">[C#], VB</span></span>     | <span data-ttu-id="73d5e-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="73d5e-143">Common/WPF</span></span>                            | <span data-ttu-id="73d5e-144">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="73d5e-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="73d5e-145">Biblioteka klas WPF</span><span class="sxs-lookup"><span data-stu-id="73d5e-145">WPF Class library</span></span>                            | [<span data-ttu-id="73d5e-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="73d5e-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="73d5e-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-147">[C#], VB</span></span>     | <span data-ttu-id="73d5e-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="73d5e-148">Common/WPF</span></span>                            | <span data-ttu-id="73d5e-149">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="73d5e-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="73d5e-150">Biblioteka kontrolek niestandardowych WPF</span><span class="sxs-lookup"><span data-stu-id="73d5e-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="73d5e-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="73d5e-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="73d5e-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-152">[C#], VB</span></span>     | <span data-ttu-id="73d5e-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="73d5e-153">Common/WPF</span></span>                            | <span data-ttu-id="73d5e-154">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="73d5e-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="73d5e-155">Biblioteka kontrolek użytkownika WPF</span><span class="sxs-lookup"><span data-stu-id="73d5e-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="73d5e-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="73d5e-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="73d5e-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-157">[C#], VB</span></span>     | <span data-ttu-id="73d5e-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="73d5e-158">Common/WPF</span></span>                            | <span data-ttu-id="73d5e-159">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="73d5e-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="73d5e-160">Aplikacja Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="73d5e-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="73d5e-161">WinForms</span><span class="sxs-lookup"><span data-stu-id="73d5e-161">winforms</span></span>](#winforms)           | <span data-ttu-id="73d5e-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-162">[C#], VB</span></span>     | <span data-ttu-id="73d5e-163">Typowe/WinForms</span><span class="sxs-lookup"><span data-stu-id="73d5e-163">Common/WinForms</span></span>                       | <span data-ttu-id="73d5e-164">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="73d5e-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="73d5e-165">Biblioteka klas Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="73d5e-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="73d5e-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="73d5e-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="73d5e-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-167">[C#], VB</span></span>     | <span data-ttu-id="73d5e-168">Typowe/WinForms</span><span class="sxs-lookup"><span data-stu-id="73d5e-168">Common/WinForms</span></span>                       | <span data-ttu-id="73d5e-169">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="73d5e-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="73d5e-170">Usługa procesu roboczego</span><span class="sxs-lookup"><span data-stu-id="73d5e-170">Worker Service</span></span>                               | [<span data-ttu-id="73d5e-171">odpowiedzialn</span><span class="sxs-lookup"><span data-stu-id="73d5e-171">worker</span></span>](#web-others)           | <span data-ttu-id="73d5e-172">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-172">[C#]</span></span>         | <span data-ttu-id="73d5e-173">Common/Worker/sieć Web</span><span class="sxs-lookup"><span data-stu-id="73d5e-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="73d5e-174">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-174">3.0</span></span>        |
| <span data-ttu-id="73d5e-175">Projekt testu jednostkowego</span><span class="sxs-lookup"><span data-stu-id="73d5e-175">Unit Test Project</span></span>                            | [<span data-ttu-id="73d5e-176">MSTest</span><span class="sxs-lookup"><span data-stu-id="73d5e-176">mstest</span></span>](#test)                 | <span data-ttu-id="73d5e-177">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-177">[C#], F#, VB</span></span> | <span data-ttu-id="73d5e-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="73d5e-178">Test/MSTest</span></span>                           | <span data-ttu-id="73d5e-179">1,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-179">1.0</span></span>        |
| <span data-ttu-id="73d5e-180">Projekt testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="73d5e-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="73d5e-181">NUnit</span><span class="sxs-lookup"><span data-stu-id="73d5e-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="73d5e-182">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-182">[C#], F#, VB</span></span> | <span data-ttu-id="73d5e-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="73d5e-183">Test/NUnit</span></span>                            | <span data-ttu-id="73d5e-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="73d5e-184">2.1.400</span></span>    |
| <span data-ttu-id="73d5e-185">Element testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="73d5e-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="73d5e-186">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-186">[C#], F#, VB</span></span> | <span data-ttu-id="73d5e-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="73d5e-187">Test/NUnit</span></span>                            | <span data-ttu-id="73d5e-188">2.2</span><span class="sxs-lookup"><span data-stu-id="73d5e-188">2.2</span></span>        |
| <span data-ttu-id="73d5e-189">Projekt testu xUnit</span><span class="sxs-lookup"><span data-stu-id="73d5e-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="73d5e-190">xUnit</span><span class="sxs-lookup"><span data-stu-id="73d5e-190">xunit</span></span>](#test)                  | <span data-ttu-id="73d5e-191">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="73d5e-191">[C#], F#, VB</span></span> | <span data-ttu-id="73d5e-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="73d5e-192">Test/xUnit</span></span>                            | <span data-ttu-id="73d5e-193">1,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-193">1.0</span></span>        |
| <span data-ttu-id="73d5e-194">Składnik Razor</span><span class="sxs-lookup"><span data-stu-id="73d5e-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="73d5e-195">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-195">[C#]</span></span>         | <span data-ttu-id="73d5e-196">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="73d5e-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="73d5e-197">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-197">3.0</span></span>        |
| <span data-ttu-id="73d5e-198">Strona Razor</span><span class="sxs-lookup"><span data-stu-id="73d5e-198">Razor Page</span></span>                                   | [<span data-ttu-id="73d5e-199">strona</span><span class="sxs-lookup"><span data-stu-id="73d5e-199">page</span></span>](#page)                   | <span data-ttu-id="73d5e-200">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-200">[C#]</span></span>         | <span data-ttu-id="73d5e-201">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="73d5e-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="73d5e-202">2,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-202">2.0</span></span>        |
| <span data-ttu-id="73d5e-203">ViewImports MVC</span><span class="sxs-lookup"><span data-stu-id="73d5e-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="73d5e-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="73d5e-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="73d5e-205">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-205">[C#]</span></span>         | <span data-ttu-id="73d5e-206">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="73d5e-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="73d5e-207">2,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-207">2.0</span></span>        |
| <span data-ttu-id="73d5e-208">ViewStart MVC</span><span class="sxs-lookup"><span data-stu-id="73d5e-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="73d5e-209">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-209">[C#]</span></span>         | <span data-ttu-id="73d5e-210">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="73d5e-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="73d5e-211">2,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-211">2.0</span></span>        |
| <span data-ttu-id="73d5e-212">Blazor Aplikacja serwera</span><span class="sxs-lookup"><span data-stu-id="73d5e-212">Blazor Server App</span></span>                            | [<span data-ttu-id="73d5e-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="73d5e-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="73d5e-214">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-214">[C#]</span></span>         | <span data-ttu-id="73d5e-215">WitrynęBlazor</span><span class="sxs-lookup"><span data-stu-id="73d5e-215">Web/Blazor</span></span>                            | <span data-ttu-id="73d5e-216">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-216">3.0</span></span>        |
| <span data-ttu-id="73d5e-217">BlazorWebAssemblyAplikacja</span><span class="sxs-lookup"><span data-stu-id="73d5e-217">Blazor WebAssembly App</span></span>                       | [<span data-ttu-id="73d5e-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="73d5e-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="73d5e-219">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-219">[C#]</span></span>         | <span data-ttu-id="73d5e-220">WitrynęBlazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="73d5e-220">Web/Blazor/WebAssembly</span></span>                | <span data-ttu-id="73d5e-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="73d5e-221">3.1.300</span></span>    |
| <span data-ttu-id="73d5e-222">ASP.NET Core puste</span><span class="sxs-lookup"><span data-stu-id="73d5e-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="73d5e-223">witrynę</span><span class="sxs-lookup"><span data-stu-id="73d5e-223">web</span></span>](#web)                     | <span data-ttu-id="73d5e-224">[C#], F #</span><span class="sxs-lookup"><span data-stu-id="73d5e-224">[C#], F#</span></span>     | <span data-ttu-id="73d5e-225">Sieć Web/pusta</span><span class="sxs-lookup"><span data-stu-id="73d5e-225">Web/Empty</span></span>                             | <span data-ttu-id="73d5e-226">1,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-226">1.0</span></span>        |
| <span data-ttu-id="73d5e-227">Aplikacja sieci Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="73d5e-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="73d5e-228">Standard</span><span class="sxs-lookup"><span data-stu-id="73d5e-228">mvc</span></span>](#web-options)             | <span data-ttu-id="73d5e-229">[C#], F #</span><span class="sxs-lookup"><span data-stu-id="73d5e-229">[C#], F#</span></span>     | <span data-ttu-id="73d5e-230">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="73d5e-230">Web/MVC</span></span>                               | <span data-ttu-id="73d5e-231">1,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-231">1.0</span></span>        |
| <span data-ttu-id="73d5e-232">Aplikacja sieci Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="73d5e-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="73d5e-233">webapp, Razor</span><span class="sxs-lookup"><span data-stu-id="73d5e-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="73d5e-234">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-234">[C#]</span></span>         | <span data-ttu-id="73d5e-235">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="73d5e-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="73d5e-236">2,2, 2,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="73d5e-237">ASP.NET Core ze Skośnością</span><span class="sxs-lookup"><span data-stu-id="73d5e-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="73d5e-238">kątow</span><span class="sxs-lookup"><span data-stu-id="73d5e-238">angular</span></span>](#spa)                 | <span data-ttu-id="73d5e-239">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-239">[C#]</span></span>         | <span data-ttu-id="73d5e-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="73d5e-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="73d5e-241">2,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-241">2.0</span></span>        |
| <span data-ttu-id="73d5e-242">ASP.NET Core z React.js</span><span class="sxs-lookup"><span data-stu-id="73d5e-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="73d5e-243">biern</span><span class="sxs-lookup"><span data-stu-id="73d5e-243">react</span></span>](#spa)                   | <span data-ttu-id="73d5e-244">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-244">[C#]</span></span>         | <span data-ttu-id="73d5e-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="73d5e-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="73d5e-246">2,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-246">2.0</span></span>        |
| <span data-ttu-id="73d5e-247">ASP.NET Core z React.js i Redux</span><span class="sxs-lookup"><span data-stu-id="73d5e-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="73d5e-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="73d5e-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="73d5e-249">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-249">[C#]</span></span>         | <span data-ttu-id="73d5e-250">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="73d5e-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="73d5e-251">2,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-251">2.0</span></span>        |
| <span data-ttu-id="73d5e-252">Biblioteka klas Razor</span><span class="sxs-lookup"><span data-stu-id="73d5e-252">Razor Class Library</span></span>                          | [<span data-ttu-id="73d5e-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="73d5e-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="73d5e-254">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-254">[C#]</span></span>         | <span data-ttu-id="73d5e-255">Biblioteka klas sieci Web/Razor/Biblioteka/Razor</span><span class="sxs-lookup"><span data-stu-id="73d5e-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="73d5e-256">2.1</span><span class="sxs-lookup"><span data-stu-id="73d5e-256">2.1</span></span>        |
| <span data-ttu-id="73d5e-257">Internetowy interfejs API platformy ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="73d5e-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="73d5e-258">WebApi</span><span class="sxs-lookup"><span data-stu-id="73d5e-258">webapi</span></span>](#webapi)               | <span data-ttu-id="73d5e-259">[C#], F #</span><span class="sxs-lookup"><span data-stu-id="73d5e-259">[C#], F#</span></span>     | <span data-ttu-id="73d5e-260">Sieć Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="73d5e-260">Web/WebAPI</span></span>                            | <span data-ttu-id="73d5e-261">1,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-261">1.0</span></span>        |
| <span data-ttu-id="73d5e-262">ASP.NET Core usługi gRPC</span><span class="sxs-lookup"><span data-stu-id="73d5e-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="73d5e-263">grpc</span><span class="sxs-lookup"><span data-stu-id="73d5e-263">grpc</span></span>](#web-others)             | <span data-ttu-id="73d5e-264">Znajd</span><span class="sxs-lookup"><span data-stu-id="73d5e-264">[C#]</span></span>         | <span data-ttu-id="73d5e-265">Sieć Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="73d5e-265">Web/gRPC</span></span>                              | <span data-ttu-id="73d5e-266">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-266">3.0</span></span>        |
| <span data-ttu-id="73d5e-267">plik GITIGNORE dotnet</span><span class="sxs-lookup"><span data-stu-id="73d5e-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="73d5e-268">Config</span><span class="sxs-lookup"><span data-stu-id="73d5e-268">Config</span></span>                                | <span data-ttu-id="73d5e-269">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-269">3.0</span></span>        |
| <span data-ttu-id="73d5e-270">global.jspliku</span><span class="sxs-lookup"><span data-stu-id="73d5e-270">global.json file</span></span>                             | [<span data-ttu-id="73d5e-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="73d5e-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="73d5e-272">Config</span><span class="sxs-lookup"><span data-stu-id="73d5e-272">Config</span></span>                                | <span data-ttu-id="73d5e-273">2,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-273">2.0</span></span>        |
| <span data-ttu-id="73d5e-274">Konfiguracja narzędzia NuGet</span><span class="sxs-lookup"><span data-stu-id="73d5e-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="73d5e-275">Config</span><span class="sxs-lookup"><span data-stu-id="73d5e-275">Config</span></span>                                | <span data-ttu-id="73d5e-276">1,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-276">1.0</span></span>        |
| <span data-ttu-id="73d5e-277">Plik manifestu narzędzia lokalnego dotnet</span><span class="sxs-lookup"><span data-stu-id="73d5e-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="73d5e-278">Config</span><span class="sxs-lookup"><span data-stu-id="73d5e-278">Config</span></span>                                | <span data-ttu-id="73d5e-279">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-279">3.0</span></span>        |
| <span data-ttu-id="73d5e-280">Konfiguracja sieci Web</span><span class="sxs-lookup"><span data-stu-id="73d5e-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="73d5e-281">Config</span><span class="sxs-lookup"><span data-stu-id="73d5e-281">Config</span></span>                                | <span data-ttu-id="73d5e-282">1,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-282">1.0</span></span>        |
| <span data-ttu-id="73d5e-283">Plik rozwiązania</span><span class="sxs-lookup"><span data-stu-id="73d5e-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="73d5e-284">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="73d5e-284">Solution</span></span>                              | <span data-ttu-id="73d5e-285">1,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-285">1.0</span></span>        |
| <span data-ttu-id="73d5e-286">Plik buforu protokołu</span><span class="sxs-lookup"><span data-stu-id="73d5e-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="73d5e-287">proto</span><span class="sxs-lookup"><span data-stu-id="73d5e-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="73d5e-288">Sieć Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="73d5e-288">Web/gRPC</span></span>                              | <span data-ttu-id="73d5e-289">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="73d5e-290">Opcje</span><span class="sxs-lookup"><span data-stu-id="73d5e-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="73d5e-291">Wyświetla podsumowanie tego, co się stanie w przypadku uruchomienia danego polecenia, jeśli mogłoby to spowodować utworzenie szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="73d5e-292">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="73d5e-293">Wymusza wygenerowanie zawartości nawet w przypadku zmiany istniejących plików.</span><span class="sxs-lookup"><span data-stu-id="73d5e-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="73d5e-294">Jest to wymagane, gdy wybrany szablon spowoduje zastąpienie istniejących plików w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="73d5e-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="73d5e-295">Drukuje pomoc dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="73d5e-295">Prints out help for the command.</span></span> <span data-ttu-id="73d5e-296">Może być wywoływana dla `dotnet new` samego polecenia lub dla dowolnego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="73d5e-297">Na przykład `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="73d5e-298">Instaluje pakiet szablonów z `PATH` lub `NUGET_ID` dostarczone.</span><span class="sxs-lookup"><span data-stu-id="73d5e-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="73d5e-299">Jeśli chcesz zainstalować wersję wstępną pakietu szablonu, musisz określić wersję w formacie `<package-name>::<package-version>` .</span><span class="sxs-lookup"><span data-stu-id="73d5e-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="73d5e-300">Domyślnie program `dotnet new` przekazuje \* wersję, która reprezentuje najnowszą stabilną wersję pakietu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="73d5e-301">Zobacz przykład w sekcji [przykładów](#examples) .</span><span class="sxs-lookup"><span data-stu-id="73d5e-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="73d5e-302">Jeśli wersja szablonu została już zainstalowana po uruchomieniu tego polecenia, szablon zostanie zaktualizowany do określonej wersji lub do najnowszej wersji stabilnej, jeśli nie określono żadnej wersji.</span><span class="sxs-lookup"><span data-stu-id="73d5e-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="73d5e-303">Aby uzyskać informacje na temat tworzenia szablonów niestandardowych, zobacz [Szablony niestandardowe dla usługi dotnet New](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="73d5e-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="73d5e-304">Wyświetla listę szablonów zawierających określoną nazwę.</span><span class="sxs-lookup"><span data-stu-id="73d5e-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="73d5e-305">Jeśli nazwa nie zostanie określona, program wyświetli listę wszystkich szablonów.</span><span class="sxs-lookup"><span data-stu-id="73d5e-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="73d5e-306">Język szablonu do utworzenia.</span><span class="sxs-lookup"><span data-stu-id="73d5e-306">The language of the template to create.</span></span> <span data-ttu-id="73d5e-307">Zaakceptowany język zależy od szablonu (zobacz wartości domyślne w sekcji [argumenty](#arguments) ).</span><span class="sxs-lookup"><span data-stu-id="73d5e-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="73d5e-308">Nieprawidłowy dla niektórych szablonów.</span><span class="sxs-lookup"><span data-stu-id="73d5e-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="73d5e-309">Niektóre powłoki interpretują `#` jako znak specjalny.</span><span class="sxs-lookup"><span data-stu-id="73d5e-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="73d5e-310">W takich przypadkach należy ująć wartość parametru Language w cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="73d5e-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="73d5e-311">Na przykład `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="73d5e-312">Nazwa dla utworzonych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="73d5e-312">The name for the created output.</span></span> <span data-ttu-id="73d5e-313">Jeśli nazwa nie zostanie określona, zostanie użyta nazwa bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="73d5e-314">Określa źródło NuGet do użycia podczas instalacji.</span><span class="sxs-lookup"><span data-stu-id="73d5e-314">Specifies a NuGet source to use during install.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="73d5e-315">Lokalizacja, w której mają zostać umieszczone wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="73d5e-315">Location to place the generated output.</span></span> <span data-ttu-id="73d5e-316">Ustawieniem domyślnym jest bieżący katalog.</span><span class="sxs-lookup"><span data-stu-id="73d5e-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="73d5e-317">Filtruje szablony w oparciu o dostępne typy.</span><span class="sxs-lookup"><span data-stu-id="73d5e-317">Filters templates based on available types.</span></span> <span data-ttu-id="73d5e-318">Wstępnie zdefiniowane wartości to `project` i `item` .</span><span class="sxs-lookup"><span data-stu-id="73d5e-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="73d5e-319">Odinstalowuje pakiet szablonów w `PATH` lub `NUGET_ID` udostępniony.</span><span class="sxs-lookup"><span data-stu-id="73d5e-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="73d5e-320">Gdy `<PATH|NUGET_ID>` wartość nie jest określona, wyświetlane są wszystkie aktualnie zainstalowane pakiety szablonów i skojarzone z nimi szablony.</span><span class="sxs-lookup"><span data-stu-id="73d5e-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="73d5e-321">Podczas określania `NUGET_ID` nie należy umieszczać numeru wersji.</span><span class="sxs-lookup"><span data-stu-id="73d5e-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="73d5e-322">Jeśli nie określisz parametru do tej opcji, polecenie wyświetli listę zainstalowanych szablonów i szczegółowe informacje o nich.</span><span class="sxs-lookup"><span data-stu-id="73d5e-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="73d5e-323">Aby odinstalować szablon przy użyciu programu `PATH` , należy w pełni zakwalifikować ścieżkę.</span><span class="sxs-lookup"><span data-stu-id="73d5e-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="73d5e-324">Na przykład *C:/Users/ \<USER> /Documents/templates/GarciaSoftware.ConsoleTemplate.CSharp* będzie działał, ale *./GarciaSoftware.ConsoleTemplate.CSharp* z folderu zawierającego nie będzie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="73d5e-325">Nie dołączaj ostatecznego ukośnika katalogu w ścieżce szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="73d5e-326">Sprawdza, czy są dostępne aktualizacje pakietów szablonów, które są obecnie zainstalowane i instaluje je.</span><span class="sxs-lookup"><span data-stu-id="73d5e-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="73d5e-327">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="73d5e-328">Sprawdza, czy są dostępne aktualizacje pakietów szablonów, które są obecnie zainstalowane.</span><span class="sxs-lookup"><span data-stu-id="73d5e-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="73d5e-329">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="73d5e-330">Opcje szablonu</span><span class="sxs-lookup"><span data-stu-id="73d5e-330">Template options</span></span>

<span data-ttu-id="73d5e-331">Każdy szablon projektu może mieć dodatkowe opcje dostępne.</span><span class="sxs-lookup"><span data-stu-id="73d5e-331">Each project template may have additional options available.</span></span> <span data-ttu-id="73d5e-332">Szablony podstawowe mają następujące dodatkowe opcje:</span><span class="sxs-lookup"><span data-stu-id="73d5e-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="73d5e-333">console</span><span class="sxs-lookup"><span data-stu-id="73d5e-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="73d5e-334">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="73d5e-335">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="73d5e-336">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="73d5e-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="73d5e-337">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="73d5e-337">SDK version</span></span> | <span data-ttu-id="73d5e-338">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="73d5e-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="73d5e-339">5,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-339">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="73d5e-340">3,1</span><span class="sxs-lookup"><span data-stu-id="73d5e-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="73d5e-341">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="73d5e-342">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="73d5e-343">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="73d5e-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="73d5e-344">Nieobsługiwane dla języka F #.</span><span class="sxs-lookup"><span data-stu-id="73d5e-344">Not supported for F#.</span></span> <span data-ttu-id="73d5e-345">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="73d5e-346">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="73d5e-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="73d5e-347">Jeśli określony, nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="73d5e-348">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="73d5e-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="73d5e-350">określono</span><span class="sxs-lookup"><span data-stu-id="73d5e-350">classlib</span></span>

- <span data-ttu-id="73d5e-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="73d5e-352">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="73d5e-353">Wartości: `net5.0` lub `netcoreapp<version>` do tworzenia biblioteki klas .NET lub `netstandard<version>` do tworzenia biblioteki klas .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="73d5e-353">Values: `net5.0` or `netcoreapp<version>` to create a .NET Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="73d5e-354">Wartość domyślna dla zestawu .NET 5,0 SDK to `net5.0` .</span><span class="sxs-lookup"><span data-stu-id="73d5e-354">The default value for .NET 5.0 SDK is `net5.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="73d5e-355">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="73d5e-356">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="73d5e-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="73d5e-357">Nieobsługiwane dla języka F #.</span><span class="sxs-lookup"><span data-stu-id="73d5e-357">Not supported for F#.</span></span> <span data-ttu-id="73d5e-358">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="73d5e-359">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="73d5e-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="73d5e-360">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="73d5e-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="73d5e-362">WPF, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="73d5e-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="73d5e-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="73d5e-364">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="73d5e-365">Wartość domyślna to `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-365">The default value is `net5.0`.</span></span> <span data-ttu-id="73d5e-366">Dostępne od wersji .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="73d5e-367">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="73d5e-368">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="73d5e-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="73d5e-369">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="73d5e-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="73d5e-370">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="73d5e-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="73d5e-372">WinForms, winformslib</span><span class="sxs-lookup"><span data-stu-id="73d5e-372">winforms, winformslib</span></span>

- <span data-ttu-id="73d5e-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="73d5e-374">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="73d5e-375">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="73d5e-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="73d5e-376">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="73d5e-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="73d5e-377">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="73d5e-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="73d5e-379">proces roboczy, GRPC</span><span class="sxs-lookup"><span data-stu-id="73d5e-379">worker, grpc</span></span>

- <span data-ttu-id="73d5e-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="73d5e-381">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="73d5e-382">Wartość domyślna to `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="73d5e-383">Dostępne od wersji .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="73d5e-384">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="73d5e-385">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="73d5e-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="73d5e-387">MSTest, xUnit</span><span class="sxs-lookup"><span data-stu-id="73d5e-387">mstest, xunit</span></span>

- <span data-ttu-id="73d5e-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="73d5e-389">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="73d5e-390">Opcja dostępna od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="73d5e-391">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="73d5e-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="73d5e-392">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="73d5e-392">SDK version</span></span> | <span data-ttu-id="73d5e-393">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="73d5e-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="73d5e-394">5,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-394">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="73d5e-395">3,1</span><span class="sxs-lookup"><span data-stu-id="73d5e-395">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="73d5e-396">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-396">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="73d5e-397">Włącza pakowanie dla projektu przy użyciu [pakietu dotnet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="73d5e-397">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="73d5e-398">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-398">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="73d5e-399">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-399">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="73d5e-400">NUnit</span><span class="sxs-lookup"><span data-stu-id="73d5e-400">nunit</span></span>

- <span data-ttu-id="73d5e-401">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-401">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="73d5e-402">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-402">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="73d5e-403">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="73d5e-403">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="73d5e-404">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="73d5e-404">SDK version</span></span> | <span data-ttu-id="73d5e-405">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="73d5e-405">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="73d5e-406">5,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-406">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="73d5e-407">3,1</span><span class="sxs-lookup"><span data-stu-id="73d5e-407">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="73d5e-408">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-408">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="73d5e-409">2.2</span><span class="sxs-lookup"><span data-stu-id="73d5e-409">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="73d5e-410">2.1</span><span class="sxs-lookup"><span data-stu-id="73d5e-410">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="73d5e-411">Włącza pakowanie dla projektu przy użyciu [pakietu dotnet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="73d5e-411">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="73d5e-412">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-412">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="73d5e-413">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-413">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="73d5e-414">strona</span><span class="sxs-lookup"><span data-stu-id="73d5e-414">page</span></span>

- <span data-ttu-id="73d5e-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="73d5e-416">Przestrzeń nazw dla wygenerowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-416">Namespace for the generated code.</span></span> <span data-ttu-id="73d5e-417">Wartość domyślna to `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-417">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="73d5e-418">Tworzy stronę bez PageModel.</span><span class="sxs-lookup"><span data-stu-id="73d5e-418">Creates the page without a PageModel.</span></span>

<span data-ttu-id="73d5e-419">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-419">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="73d5e-420">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="73d5e-420">viewimports, proto</span></span>

- <span data-ttu-id="73d5e-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="73d5e-422">Przestrzeń nazw dla wygenerowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-422">Namespace for the generated code.</span></span> <span data-ttu-id="73d5e-423">Wartość domyślna to `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-423">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="73d5e-424">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-424">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="73d5e-425">blazorserver</span><span class="sxs-lookup"><span data-stu-id="73d5e-425">blazorserver</span></span>

- <span data-ttu-id="73d5e-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="73d5e-427">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="73d5e-427">The type of authentication to use.</span></span> <span data-ttu-id="73d5e-428">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="73d5e-428">The possible values are:</span></span>

  - <span data-ttu-id="73d5e-429">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="73d5e-429">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="73d5e-430">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="73d5e-430">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="73d5e-431">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="73d5e-431">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="73d5e-432">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="73d5e-432">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="73d5e-433">`MultiOrg` -Organizacja uwierzytelnianie dla wielu dzierżawców.</span><span class="sxs-lookup"><span data-stu-id="73d5e-433">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="73d5e-434">`Windows` — Uwierzytelnianie systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="73d5e-434">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="73d5e-435">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-435">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="73d5e-436">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-436">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-437">Wartość domyślna to `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-437">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="73d5e-438">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-438">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="73d5e-439">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-439">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="73d5e-440">Identyfikator zasad resetowania hasła dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-440">The reset password policy ID for this project.</span></span> <span data-ttu-id="73d5e-441">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-441">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="73d5e-442">Edytuj identyfikator zasad profilu dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-442">The edit profile policy ID for this project.</span></span> <span data-ttu-id="73d5e-443">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-443">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="73d5e-444">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-444">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="73d5e-445">Używanie z usługą `SingleOrg` lub `MultiOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-445">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="73d5e-446">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-446">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="73d5e-447">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-447">The Client ID for this project.</span></span> <span data-ttu-id="73d5e-448">Użyj z `IndividualB2C` , `SingleOrg` lub `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-448">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="73d5e-449">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-449">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="73d5e-450">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-450">The domain for the directory tenant.</span></span> <span data-ttu-id="73d5e-451">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-451">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-452">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-452">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="73d5e-453">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-453">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="73d5e-454">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-454">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="73d5e-455">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-455">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="73d5e-456">Ścieżka żądania w ścieżce podstawowej identyfikatora URI przekierowania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-456">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="73d5e-457">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-457">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-458">Wartość domyślna to `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-458">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="73d5e-459">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-459">Allows this application read-access to the directory.</span></span> <span data-ttu-id="73d5e-460">Dotyczy tylko `SingleOrg` `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-460">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="73d5e-461">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-461">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="73d5e-462">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="73d5e-462">Turns off HTTPS.</span></span> <span data-ttu-id="73d5e-463">Ta opcja ma zastosowanie tylko wtedy, gdy,, `Individual` `IndividualB2C` `SingleOrg` lub `MultiOrg` nie są używane w programie `--auth` .</span><span class="sxs-lookup"><span data-stu-id="73d5e-463">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="73d5e-464">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="73d5e-464">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="73d5e-465">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-465">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="73d5e-466">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-466">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="73d5e-467">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-467">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="73d5e-468">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="73d5e-468">blazorwasm</span></span>

- <span data-ttu-id="73d5e-469">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-469">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="73d5e-470">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-470">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="73d5e-471">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="73d5e-471">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="73d5e-472">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="73d5e-472">SDK version</span></span> | <span data-ttu-id="73d5e-473">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="73d5e-473">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="73d5e-474">5,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-474">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="73d5e-475">3,1</span><span class="sxs-lookup"><span data-stu-id="73d5e-475">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="73d5e-476">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="73d5e-477">Zawiera ASP.NET Core hosta dla Blazor WebAssembly aplikacji.</span><span class="sxs-lookup"><span data-stu-id="73d5e-477">Includes an ASP.NET Core host for the Blazor WebAssembly app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="73d5e-478">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="73d5e-478">The type of authentication to use.</span></span> <span data-ttu-id="73d5e-479">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="73d5e-479">The possible values are:</span></span>

  - <span data-ttu-id="73d5e-480">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="73d5e-480">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="73d5e-481">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="73d5e-481">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="73d5e-482">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="73d5e-482">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="73d5e-483">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="73d5e-483">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="73d5e-484">Urząd dostawcy OIDC.</span><span class="sxs-lookup"><span data-stu-id="73d5e-484">The authority of the OIDC provider.</span></span> <span data-ttu-id="73d5e-485">Użyj z `Individual` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-485">Use with `Individual` authentication.</span></span> <span data-ttu-id="73d5e-486">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-486">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="73d5e-487">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-487">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="73d5e-488">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-488">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-489">Wartość domyślna to `https://aadB2CInstance.b2clogin.com/`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-489">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="73d5e-490">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-490">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="73d5e-491">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-491">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="73d5e-492">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-492">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="73d5e-493">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-493">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="73d5e-494">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-494">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="73d5e-495">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-495">The Client ID for this project.</span></span> <span data-ttu-id="73d5e-496">Używanie z `IndividualB2C` , `SingleOrg` lub `Individual` uwierzytelnianie w scenariuszach autonomicznych.</span><span class="sxs-lookup"><span data-stu-id="73d5e-496">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="73d5e-497">Wartość domyślna to `33333333-3333-3333-33333333333333333`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-497">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="73d5e-498">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-498">The domain for the directory tenant.</span></span> <span data-ttu-id="73d5e-499">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-499">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-500">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-500">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="73d5e-501">Identyfikator URI identyfikatora aplikacji dla interfejsu API serwera, który chcesz wywołać.</span><span class="sxs-lookup"><span data-stu-id="73d5e-501">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="73d5e-502">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-502">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-503">Wartość domyślna to `api.id.uri`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-503">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="73d5e-504">Identyfikator klienta dla interfejsu API, który jest hostem serwera.</span><span class="sxs-lookup"><span data-stu-id="73d5e-504">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="73d5e-505">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-506">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-506">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="73d5e-507">Zakres interfejsu API, do którego klient musi zażądać tokenu dostępu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-507">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="73d5e-508">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-508">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-509">Wartość domyślna to `user_impersonation`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-509">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="73d5e-510">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-510">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="73d5e-511">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-511">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="73d5e-512">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-512">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="73d5e-513">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="73d5e-514">Dotyczy tylko `SingleOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-514">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="73d5e-515">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="73d5e-516">tworzy progresywną aplikację sieci Web (PWA), która obsługuje instalację i użycie w trybie offline.</span><span class="sxs-lookup"><span data-stu-id="73d5e-516">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="73d5e-517">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="73d5e-517">Turns off HTTPS.</span></span> <span data-ttu-id="73d5e-518">Ta opcja ma zastosowanie tylko wtedy `Individual` , gdy `IndividualB2C` lub `SingleOrg` nie są używane dla `--auth` .</span><span class="sxs-lookup"><span data-stu-id="73d5e-518">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="73d5e-519">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="73d5e-519">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="73d5e-520">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-520">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="73d5e-521">Adres URL interfejsu API do wywołania z aplikacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="73d5e-521">URL of the API to call from the web app.</span></span> <span data-ttu-id="73d5e-522">Dotyczy tylko `SingleOrg` `IndividualB2C` uwierzytelniania bez określonego hosta ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="73d5e-522">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="73d5e-523">Wartość domyślna to `https://graph.microsoft.com/v1.0/me`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-523">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="73d5e-524">Określa, czy aplikacja sieci Web wywołuje Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="73d5e-524">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="73d5e-525">Dotyczy tylko `SingleOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-525">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="73d5e-526">Zakresy do żądania wywołania interfejsu API z aplikacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="73d5e-526">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="73d5e-527">Dotyczy tylko `SingleOrg` `IndividualB2C` uwierzytelniania bez określonego hosta ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="73d5e-527">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="73d5e-528">Wartość domyślna to `user.read`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-528">The default is `user.read`.</span></span>

<span data-ttu-id="73d5e-529">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-529">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="73d5e-530">web</span><span class="sxs-lookup"><span data-stu-id="73d5e-530">web</span></span>

- <span data-ttu-id="73d5e-531">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-531">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="73d5e-532">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="73d5e-533">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="73d5e-534">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="73d5e-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="73d5e-535">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="73d5e-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="73d5e-536">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="73d5e-536">SDK version</span></span> | <span data-ttu-id="73d5e-537">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="73d5e-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="73d5e-538">5,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-538">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="73d5e-539">3,1</span><span class="sxs-lookup"><span data-stu-id="73d5e-539">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="73d5e-540">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-540">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="73d5e-541">2.1</span><span class="sxs-lookup"><span data-stu-id="73d5e-541">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="73d5e-542">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="73d5e-543">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="73d5e-543">Turns off HTTPS.</span></span>

<span data-ttu-id="73d5e-544">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-544">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="73d5e-545">MVC, webapp</span><span class="sxs-lookup"><span data-stu-id="73d5e-545">mvc, webapp</span></span>

- <span data-ttu-id="73d5e-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="73d5e-547">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="73d5e-547">The type of authentication to use.</span></span> <span data-ttu-id="73d5e-548">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="73d5e-548">The possible values are:</span></span>

  - <span data-ttu-id="73d5e-549">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="73d5e-549">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="73d5e-550">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="73d5e-550">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="73d5e-551">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="73d5e-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="73d5e-552">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="73d5e-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="73d5e-553">`MultiOrg` -Organizacja uwierzytelnianie dla wielu dzierżawców.</span><span class="sxs-lookup"><span data-stu-id="73d5e-553">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="73d5e-554">`Windows` — Uwierzytelnianie systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="73d5e-554">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="73d5e-555">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-555">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="73d5e-556">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-556">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-557">Wartość domyślna to `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-557">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="73d5e-558">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-558">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="73d5e-559">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-559">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="73d5e-560">Identyfikator zasad resetowania hasła dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-560">The reset password policy ID for this project.</span></span> <span data-ttu-id="73d5e-561">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-561">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="73d5e-562">Edytuj identyfikator zasad profilu dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-562">The edit profile policy ID for this project.</span></span> <span data-ttu-id="73d5e-563">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-563">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="73d5e-564">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-564">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="73d5e-565">Używanie z usługą `SingleOrg` lub `MultiOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-565">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="73d5e-566">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-566">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="73d5e-567">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-567">The Client ID for this project.</span></span> <span data-ttu-id="73d5e-568">Użyj z `IndividualB2C` , `SingleOrg` lub `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-568">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="73d5e-569">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-569">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="73d5e-570">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-570">The domain for the directory tenant.</span></span> <span data-ttu-id="73d5e-571">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-571">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-572">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-572">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="73d5e-573">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-573">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="73d5e-574">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-574">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="73d5e-575">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-575">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="73d5e-576">Ścieżka żądania w ścieżce podstawowej identyfikatora URI przekierowania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-576">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="73d5e-577">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-577">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-578">Wartość domyślna to `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-578">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="73d5e-579">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-579">Allows this application read-access to the directory.</span></span> <span data-ttu-id="73d5e-580">Dotyczy tylko `SingleOrg` `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-580">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="73d5e-581">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-581">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="73d5e-582">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="73d5e-582">Turns off HTTPS.</span></span> <span data-ttu-id="73d5e-583">Ta opcja ma zastosowanie tylko wtedy, gdy,, `Individual` `IndividualB2C` `SingleOrg` lub `MultiOrg` nie jest używany.</span><span class="sxs-lookup"><span data-stu-id="73d5e-583">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="73d5e-584">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="73d5e-584">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="73d5e-585">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-585">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="73d5e-586">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-586">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="73d5e-587">Opcja dostępna od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-587">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="73d5e-588">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="73d5e-588">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="73d5e-589">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="73d5e-589">SDK version</span></span> | <span data-ttu-id="73d5e-590">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="73d5e-590">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="73d5e-591">5,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-591">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="73d5e-592">3,1</span><span class="sxs-lookup"><span data-stu-id="73d5e-592">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="73d5e-593">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-593">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="73d5e-594">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-594">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="73d5e-595">Zawiera BrowserLink w projekcie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-595">Includes BrowserLink in the project.</span></span> <span data-ttu-id="73d5e-596">Opcja nie jest dostępna w programie .NET Core 2,2 i 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-596">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="73d5e-597">Określa, czy projekt jest skonfigurowany do używania [kompilacji środowiska uruchomieniowego Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) w kompilacjach debugowania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-597">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="73d5e-598">Opcja dostępna od wersji .NET Core 3.1.201 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-598">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="73d5e-599">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-599">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="73d5e-600">kątowy, reagowanie</span><span class="sxs-lookup"><span data-stu-id="73d5e-600">angular, react</span></span>

- <span data-ttu-id="73d5e-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="73d5e-602">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="73d5e-602">The type of authentication to use.</span></span> <span data-ttu-id="73d5e-603">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-603">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="73d5e-604">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="73d5e-604">The possible values are:</span></span>

  - <span data-ttu-id="73d5e-605">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="73d5e-605">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="73d5e-606">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="73d5e-606">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="73d5e-607">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-607">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="73d5e-608">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-608">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="73d5e-609">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="73d5e-609">Turns off HTTPS.</span></span> <span data-ttu-id="73d5e-610">Ta opcja ma zastosowanie tylko wtedy, gdy uwierzytelnianie jest `None` .</span><span class="sxs-lookup"><span data-stu-id="73d5e-610">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="73d5e-611">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="73d5e-611">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="73d5e-612">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-612">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-613">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-613">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="73d5e-614">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-614">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="73d5e-615">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="73d5e-615">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="73d5e-616">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="73d5e-616">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="73d5e-617">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="73d5e-617">SDK version</span></span> | <span data-ttu-id="73d5e-618">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="73d5e-618">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="73d5e-619">5,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-619">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="73d5e-620">3,1</span><span class="sxs-lookup"><span data-stu-id="73d5e-620">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="73d5e-621">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-621">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="73d5e-622">2.1</span><span class="sxs-lookup"><span data-stu-id="73d5e-622">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="73d5e-623">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-623">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="73d5e-624">reactredux</span><span class="sxs-lookup"><span data-stu-id="73d5e-624">reactredux</span></span>

- <span data-ttu-id="73d5e-625">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-625">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="73d5e-626">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-626">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="73d5e-627">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-627">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="73d5e-628">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="73d5e-628">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="73d5e-629">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="73d5e-629">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="73d5e-630">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="73d5e-630">SDK version</span></span> | <span data-ttu-id="73d5e-631">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="73d5e-631">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="73d5e-632">5,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-632">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="73d5e-633">3,1</span><span class="sxs-lookup"><span data-stu-id="73d5e-633">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="73d5e-634">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-634">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="73d5e-635">2.1</span><span class="sxs-lookup"><span data-stu-id="73d5e-635">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="73d5e-636">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-636">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="73d5e-637">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="73d5e-637">Turns off HTTPS.</span></span>

<span data-ttu-id="73d5e-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-638">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="73d5e-639">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="73d5e-639">razorclasslib</span></span>

- <span data-ttu-id="73d5e-640">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-640">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="73d5e-641">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-641">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="73d5e-642">Obsługuje dodawanie tradycyjnych stron Razor i widoków oprócz składników do tej biblioteki.</span><span class="sxs-lookup"><span data-stu-id="73d5e-642">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="73d5e-643">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="73d5e-643">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="73d5e-644">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-644">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="73d5e-645">WebApi</span><span class="sxs-lookup"><span data-stu-id="73d5e-645">webapi</span></span>

- <span data-ttu-id="73d5e-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="73d5e-647">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="73d5e-647">The type of authentication to use.</span></span> <span data-ttu-id="73d5e-648">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="73d5e-648">The possible values are:</span></span>

  - <span data-ttu-id="73d5e-649">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="73d5e-649">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="73d5e-650">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="73d5e-650">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="73d5e-651">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="73d5e-651">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="73d5e-652">`Windows` — Uwierzytelnianie systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="73d5e-652">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="73d5e-653">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-653">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="73d5e-654">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-654">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="73d5e-655">Wartość domyślna to `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-655">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="73d5e-656">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-656">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="73d5e-657">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-657">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="73d5e-658">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-658">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="73d5e-659">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-659">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="73d5e-660">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-660">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="73d5e-661">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-661">The Client ID for this project.</span></span> <span data-ttu-id="73d5e-662">Używanie z usługą `IndividualB2C` lub `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-662">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="73d5e-663">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-663">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="73d5e-664">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-664">The domain for the directory tenant.</span></span> <span data-ttu-id="73d5e-665">Używanie z usługą `IndividualB2C` lub `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-665">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="73d5e-666">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-666">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="73d5e-667">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="73d5e-667">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="73d5e-668">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="73d5e-668">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="73d5e-669">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="73d5e-669">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="73d5e-670">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-670">Allows this application read-access to the directory.</span></span> <span data-ttu-id="73d5e-671">Dotyczy tylko `SingleOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-671">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="73d5e-672">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-672">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="73d5e-673">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="73d5e-673">Turns off HTTPS.</span></span> <span data-ttu-id="73d5e-674">`app.UseHsts` i `app.UseHttpsRedirection` nie są dodawane do `Startup.Configure` .</span><span class="sxs-lookup"><span data-stu-id="73d5e-674">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="73d5e-675">Ta opcja ma zastosowanie tylko wtedy `IndividualB2C` , gdy lub `SingleOrg` nie są używane do uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-675">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="73d5e-676">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="73d5e-676">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="73d5e-677">Dotyczy tylko `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="73d5e-677">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="73d5e-678">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="73d5e-678">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="73d5e-679">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="73d5e-679">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="73d5e-680">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="73d5e-680">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="73d5e-681">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="73d5e-681">SDK version</span></span> | <span data-ttu-id="73d5e-682">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="73d5e-682">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="73d5e-683">5,0</span><span class="sxs-lookup"><span data-stu-id="73d5e-683">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="73d5e-684">3,1</span><span class="sxs-lookup"><span data-stu-id="73d5e-684">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="73d5e-685">3.0</span><span class="sxs-lookup"><span data-stu-id="73d5e-685">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="73d5e-686">2.1</span><span class="sxs-lookup"><span data-stu-id="73d5e-686">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="73d5e-687">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-687">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="73d5e-688">\*\*_</span><span class="sxs-lookup"><span data-stu-id="73d5e-688">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="73d5e-689">globaljson</span><span class="sxs-lookup"><span data-stu-id="73d5e-689">globaljson</span></span>

- <span data-ttu-id="73d5e-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="73d5e-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="73d5e-691">Określa wersję zestawu SDK platformy .NET do użycia w *global.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="73d5e-691">Specifies the version of the .NET SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="73d5e-692">Przykłady</span><span class="sxs-lookup"><span data-stu-id="73d5e-692">Examples</span></span>

- <span data-ttu-id="73d5e-693">Utwórz projekt aplikacji konsolowej w języku C#, określając nazwę szablonu:</span><span class="sxs-lookup"><span data-stu-id="73d5e-693">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="73d5e-694">Utwórz projekt aplikacji konsolowej F # w bieżącym katalogu:</span><span class="sxs-lookup"><span data-stu-id="73d5e-694">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="73d5e-695">Utwórz projekt biblioteki klas .NET Standard w określonym katalogu:</span><span class="sxs-lookup"><span data-stu-id="73d5e-695">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="73d5e-696">Utwórz nowy projekt ASP.NET Core C# MVC w bieżącym katalogu bez uwierzytelniania:</span><span class="sxs-lookup"><span data-stu-id="73d5e-696">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="73d5e-697">Utwórz nowy projekt xUnit:</span><span class="sxs-lookup"><span data-stu-id="73d5e-697">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="73d5e-698">Wyświetl listę wszystkich szablonów dostępnych dla szablonów aplikacji jednostronicowych (SPA):</span><span class="sxs-lookup"><span data-stu-id="73d5e-698">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="73d5e-699">Wyświetl listę wszystkich szablonów pasujących *do* podciągu.</span><span class="sxs-lookup"><span data-stu-id="73d5e-699">List all templates matching the *we* substring.</span></span> <span data-ttu-id="73d5e-700">Nie znaleziono dokładnego dopasowania, więc Dopasowywanie podciągów działa w odniesieniu do kolumn krótkich nazw i nazw.</span><span class="sxs-lookup"><span data-stu-id="73d5e-700">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="73d5e-701">Podjęto próbę wywołania szablonu zgodnego z parametrem *ng*.</span><span class="sxs-lookup"><span data-stu-id="73d5e-701">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="73d5e-702">Jeśli nie można ustalić pojedynczego dopasowania, należy wyświetlić listę szablonów, które są dopasowań częściowych.</span><span class="sxs-lookup"><span data-stu-id="73d5e-702">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="73d5e-703">Zainstaluj wersję 2,0 szablonów SPA dla ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="73d5e-703">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="73d5e-704">Wyświetl listę zainstalowanych szablonów i szczegółowe informacje o nich, w tym sposoby ich odinstalowywania:</span><span class="sxs-lookup"><span data-stu-id="73d5e-704">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="73d5e-705">Utwórz *global.js* w bieżącym katalogu, ustawiając wersję zestawu SDK na 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="73d5e-705">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="73d5e-706">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="73d5e-706">See also</span></span>

- [<span data-ttu-id="73d5e-707">Szablony niestandardowe dla nowego dotnet</span><span class="sxs-lookup"><span data-stu-id="73d5e-707">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="73d5e-708">Tworzenie szablonu niestandardowego dla polecenia dotnet new</span><span class="sxs-lookup"><span data-stu-id="73d5e-708">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="73d5e-709">dotnet/dotnet-Template-przykłady repozytorium GitHub</span><span class="sxs-lookup"><span data-stu-id="73d5e-709">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="73d5e-710">Dostępne szablony dla nowego dotnet</span><span class="sxs-lookup"><span data-stu-id="73d5e-710">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
