---
title: polecenie dotnet New
description: Polecenie dotnet New umożliwia tworzenie nowych projektów platformy .NET Core na podstawie określonego szablonu.
no-loc:
- ':::no-loc(Blazor):::'
- ':::no-loc(WebAssembly):::'
ms.date: 09/04/2020
ms.openlocfilehash: 2ee06c37cd950f3b9771db2f30fe353435641d67
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400594"
---
# <a name="dotnet-new"></a><span data-ttu-id="6d8b8-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="6d8b8-103">dotnet new</span></span>

<span data-ttu-id="6d8b8-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,0 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="6d8b8-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6d8b8-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="6d8b8-105">Name</span></span>

<span data-ttu-id="6d8b8-106">`dotnet new` -Tworzy nowy projekt, plik konfiguracji lub rozwiązanie na podstawie określonego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6d8b8-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="6d8b8-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="6d8b8-108">Opis</span><span class="sxs-lookup"><span data-stu-id="6d8b8-108">Description</span></span>

<span data-ttu-id="6d8b8-109">`dotnet new`Polecenie tworzy projekt .NET Core lub inne artefakty na podstawie szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="6d8b8-110">Polecenie wywołuje [aparat szablonu](https://github.com/dotnet/templating) , aby utworzyć artefakty na dysku na podstawie określonego szablonu i opcji.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="6d8b8-111">Przywracanie niejawne</span><span class="sxs-lookup"><span data-stu-id="6d8b8-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="6d8b8-112">Argumenty</span><span class="sxs-lookup"><span data-stu-id="6d8b8-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="6d8b8-113">Szablon do wystąpienia po wywołaniu polecenia.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="6d8b8-114">Każdy szablon może mieć określone opcje, które można przekazać.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="6d8b8-115">Aby uzyskać więcej informacji, zobacz [Opcje szablonu](#template-options).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="6d8b8-116">Można uruchomić `dotnet new --list` lub `dotnet new -l` wyświetlić listę wszystkich zainstalowanych szablonów.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="6d8b8-117">Jeśli `TEMPLATE` wartość nie jest dokładnym dopasowaniem do tekstu w kolumnie **Szablony** lub **krótka nazwa** z zwróconej tabeli, do tych dwóch kolumn jest wykonywane dopasowanie podciągu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="6d8b8-118">Począwszy od zestawu SDK platformy .NET Core 3,0, interfejs wiersza polecenia wyszukuje szablony w NuGet.org, gdy wywoła `dotnet new` polecenie w następujących warunkach:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="6d8b8-119">Jeśli interfejs wiersza polecenia nie może znaleźć dopasowania szablonu podczas wywoływania `dotnet new` , nie nawet częściowej.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="6d8b8-120">Jeśli jest dostępna nowsza wersja szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="6d8b8-121">W takim przypadku projekt lub artefakt jest tworzony, ale interfejs wiersza polecenia ostrzega użytkownika o zaktualizowanej wersji szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="6d8b8-122">W poniższej tabeli przedstawiono szablony, które są wstępnie zainstalowane wraz z zestaw .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="6d8b8-123">Język domyślny dla szablonu jest pokazywany w nawiasach.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="6d8b8-124">Kliknij link krótkiej nazwy, aby wyświetlić opcje konkretnego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="6d8b8-125">Szablony</span><span class="sxs-lookup"><span data-stu-id="6d8b8-125">Templates</span></span>                                    | <span data-ttu-id="6d8b8-126">Krótka nazwa</span><span class="sxs-lookup"><span data-stu-id="6d8b8-126">Short name</span></span>                      | <span data-ttu-id="6d8b8-127">Język</span><span class="sxs-lookup"><span data-stu-id="6d8b8-127">Language</span></span>     | <span data-ttu-id="6d8b8-128">Tagi</span><span class="sxs-lookup"><span data-stu-id="6d8b8-128">Tags</span></span>                                  | <span data-ttu-id="6d8b8-129">Wprowadzono</span><span class="sxs-lookup"><span data-stu-id="6d8b8-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="6d8b8-130">Aplikacja konsoli</span><span class="sxs-lookup"><span data-stu-id="6d8b8-130">Console Application</span></span>                          | [<span data-ttu-id="6d8b8-131">konsoli</span><span class="sxs-lookup"><span data-stu-id="6d8b8-131">console</span></span>](#console)             | <span data-ttu-id="6d8b8-132">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-132">[C#], F#, VB</span></span> | <span data-ttu-id="6d8b8-133">Wspólna/konsola</span><span class="sxs-lookup"><span data-stu-id="6d8b8-133">Common/Console</span></span>                        | <span data-ttu-id="6d8b8-134">1.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-134">1.0</span></span>        |
| <span data-ttu-id="6d8b8-135">Biblioteka klas</span><span class="sxs-lookup"><span data-stu-id="6d8b8-135">Class library</span></span>                                | [<span data-ttu-id="6d8b8-136">określono</span><span class="sxs-lookup"><span data-stu-id="6d8b8-136">classlib</span></span>](#classlib)           | <span data-ttu-id="6d8b8-137">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-137">[C#], F#, VB</span></span> | <span data-ttu-id="6d8b8-138">Wspólna/Biblioteka</span><span class="sxs-lookup"><span data-stu-id="6d8b8-138">Common/Library</span></span>                        | <span data-ttu-id="6d8b8-139">1.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-139">1.0</span></span>        |
| <span data-ttu-id="6d8b8-140">Aplikacja WPF</span><span class="sxs-lookup"><span data-stu-id="6d8b8-140">WPF Application</span></span>                              | [<span data-ttu-id="6d8b8-141">kodow</span><span class="sxs-lookup"><span data-stu-id="6d8b8-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="6d8b8-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-142">[C#], VB</span></span>     | <span data-ttu-id="6d8b8-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="6d8b8-143">Common/WPF</span></span>                            | <span data-ttu-id="6d8b8-144">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="6d8b8-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="6d8b8-145">Biblioteka klas WPF</span><span class="sxs-lookup"><span data-stu-id="6d8b8-145">WPF Class library</span></span>                            | [<span data-ttu-id="6d8b8-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="6d8b8-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="6d8b8-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-147">[C#], VB</span></span>     | <span data-ttu-id="6d8b8-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="6d8b8-148">Common/WPF</span></span>                            | <span data-ttu-id="6d8b8-149">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="6d8b8-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="6d8b8-150">Biblioteka kontrolek niestandardowych WPF</span><span class="sxs-lookup"><span data-stu-id="6d8b8-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="6d8b8-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="6d8b8-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="6d8b8-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-152">[C#], VB</span></span>     | <span data-ttu-id="6d8b8-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="6d8b8-153">Common/WPF</span></span>                            | <span data-ttu-id="6d8b8-154">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="6d8b8-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="6d8b8-155">Biblioteka kontrolek użytkownika WPF</span><span class="sxs-lookup"><span data-stu-id="6d8b8-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="6d8b8-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="6d8b8-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="6d8b8-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-157">[C#], VB</span></span>     | <span data-ttu-id="6d8b8-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="6d8b8-158">Common/WPF</span></span>                            | <span data-ttu-id="6d8b8-159">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="6d8b8-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="6d8b8-160">Aplikacja Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="6d8b8-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="6d8b8-161">WinForms</span><span class="sxs-lookup"><span data-stu-id="6d8b8-161">winforms</span></span>](#winforms)           | <span data-ttu-id="6d8b8-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-162">[C#], VB</span></span>     | <span data-ttu-id="6d8b8-163">Typowe/WinForms</span><span class="sxs-lookup"><span data-stu-id="6d8b8-163">Common/WinForms</span></span>                       | <span data-ttu-id="6d8b8-164">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="6d8b8-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="6d8b8-165">Biblioteka klas Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="6d8b8-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="6d8b8-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="6d8b8-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="6d8b8-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-167">[C#], VB</span></span>     | <span data-ttu-id="6d8b8-168">Typowe/WinForms</span><span class="sxs-lookup"><span data-stu-id="6d8b8-168">Common/WinForms</span></span>                       | <span data-ttu-id="6d8b8-169">3,0 (5,0 dla VB)</span><span class="sxs-lookup"><span data-stu-id="6d8b8-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="6d8b8-170">Usługa procesu roboczego</span><span class="sxs-lookup"><span data-stu-id="6d8b8-170">Worker Service</span></span>                               | [<span data-ttu-id="6d8b8-171">odpowiedzialn</span><span class="sxs-lookup"><span data-stu-id="6d8b8-171">worker</span></span>](#web-others)           | <span data-ttu-id="6d8b8-172">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-172">[C#]</span></span>         | <span data-ttu-id="6d8b8-173">Common/Worker/sieć Web</span><span class="sxs-lookup"><span data-stu-id="6d8b8-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="6d8b8-174">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-174">3.0</span></span>        |
| <span data-ttu-id="6d8b8-175">Projekt testu jednostkowego</span><span class="sxs-lookup"><span data-stu-id="6d8b8-175">Unit Test Project</span></span>                            | [<span data-ttu-id="6d8b8-176">MSTest</span><span class="sxs-lookup"><span data-stu-id="6d8b8-176">mstest</span></span>](#test)                 | <span data-ttu-id="6d8b8-177">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-177">[C#], F#, VB</span></span> | <span data-ttu-id="6d8b8-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="6d8b8-178">Test/MSTest</span></span>                           | <span data-ttu-id="6d8b8-179">1.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-179">1.0</span></span>        |
| <span data-ttu-id="6d8b8-180">Projekt testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="6d8b8-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="6d8b8-181">NUnit</span><span class="sxs-lookup"><span data-stu-id="6d8b8-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="6d8b8-182">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-182">[C#], F#, VB</span></span> | <span data-ttu-id="6d8b8-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="6d8b8-183">Test/NUnit</span></span>                            | <span data-ttu-id="6d8b8-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="6d8b8-184">2.1.400</span></span>    |
| <span data-ttu-id="6d8b8-185">Element testowy NUnit 3</span><span class="sxs-lookup"><span data-stu-id="6d8b8-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="6d8b8-186">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-186">[C#], F#, VB</span></span> | <span data-ttu-id="6d8b8-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="6d8b8-187">Test/NUnit</span></span>                            | <span data-ttu-id="6d8b8-188">2.2</span><span class="sxs-lookup"><span data-stu-id="6d8b8-188">2.2</span></span>        |
| <span data-ttu-id="6d8b8-189">Projekt testu xUnit</span><span class="sxs-lookup"><span data-stu-id="6d8b8-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="6d8b8-190">xUnit</span><span class="sxs-lookup"><span data-stu-id="6d8b8-190">xunit</span></span>](#test)                  | <span data-ttu-id="6d8b8-191">[C#], F #, VB</span><span class="sxs-lookup"><span data-stu-id="6d8b8-191">[C#], F#, VB</span></span> | <span data-ttu-id="6d8b8-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="6d8b8-192">Test/xUnit</span></span>                            | <span data-ttu-id="6d8b8-193">1.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-193">1.0</span></span>        |
| <span data-ttu-id="6d8b8-194">Składnik Razor</span><span class="sxs-lookup"><span data-stu-id="6d8b8-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="6d8b8-195">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-195">[C#]</span></span>         | <span data-ttu-id="6d8b8-196">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="6d8b8-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="6d8b8-197">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-197">3.0</span></span>        |
| <span data-ttu-id="6d8b8-198">Strona Razor</span><span class="sxs-lookup"><span data-stu-id="6d8b8-198">Razor Page</span></span>                                   | [<span data-ttu-id="6d8b8-199">stronic</span><span class="sxs-lookup"><span data-stu-id="6d8b8-199">page</span></span>](#page)                   | <span data-ttu-id="6d8b8-200">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-200">[C#]</span></span>         | <span data-ttu-id="6d8b8-201">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="6d8b8-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="6d8b8-202">2,0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-202">2.0</span></span>        |
| <span data-ttu-id="6d8b8-203">ViewImports MVC</span><span class="sxs-lookup"><span data-stu-id="6d8b8-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="6d8b8-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="6d8b8-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="6d8b8-205">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-205">[C#]</span></span>         | <span data-ttu-id="6d8b8-206">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="6d8b8-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="6d8b8-207">2,0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-207">2.0</span></span>        |
| <span data-ttu-id="6d8b8-208">ViewStart MVC</span><span class="sxs-lookup"><span data-stu-id="6d8b8-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="6d8b8-209">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-209">[C#]</span></span>         | <span data-ttu-id="6d8b8-210">Web/ASP. NET</span><span class="sxs-lookup"><span data-stu-id="6d8b8-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="6d8b8-211">2,0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-211">2.0</span></span>        |
| <span data-ttu-id="6d8b8-212">:::no-loc(Blazor)::: Aplikacja serwera</span><span class="sxs-lookup"><span data-stu-id="6d8b8-212">:::no-loc(Blazor)::: Server App</span></span>                            | [<span data-ttu-id="6d8b8-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="6d8b8-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="6d8b8-214">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-214">[C#]</span></span>         | <span data-ttu-id="6d8b8-215">Witrynę:::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="6d8b8-215">Web/:::no-loc(Blazor):::</span></span>                            | <span data-ttu-id="6d8b8-216">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-216">3.0</span></span>        |
| <span data-ttu-id="6d8b8-217">:::no-loc(Blazor)::::::no-loc(WebAssembly):::Aplikacja</span><span class="sxs-lookup"><span data-stu-id="6d8b8-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: App</span></span>                       | [<span data-ttu-id="6d8b8-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="6d8b8-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="6d8b8-219">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-219">[C#]</span></span>         | <span data-ttu-id="6d8b8-220">Witrynę:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="6d8b8-220">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span></span>                | <span data-ttu-id="6d8b8-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="6d8b8-221">3.1.300</span></span>    |
| <span data-ttu-id="6d8b8-222">ASP.NET Core puste</span><span class="sxs-lookup"><span data-stu-id="6d8b8-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="6d8b8-223">witrynę</span><span class="sxs-lookup"><span data-stu-id="6d8b8-223">web</span></span>](#web)                     | <span data-ttu-id="6d8b8-224">[C#], F #</span><span class="sxs-lookup"><span data-stu-id="6d8b8-224">[C#], F#</span></span>     | <span data-ttu-id="6d8b8-225">Sieć Web/pusta</span><span class="sxs-lookup"><span data-stu-id="6d8b8-225">Web/Empty</span></span>                             | <span data-ttu-id="6d8b8-226">1.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-226">1.0</span></span>        |
| <span data-ttu-id="6d8b8-227">Aplikacja sieci Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="6d8b8-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="6d8b8-228">Standard</span><span class="sxs-lookup"><span data-stu-id="6d8b8-228">mvc</span></span>](#web-options)             | <span data-ttu-id="6d8b8-229">[C#], F #</span><span class="sxs-lookup"><span data-stu-id="6d8b8-229">[C#], F#</span></span>     | <span data-ttu-id="6d8b8-230">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="6d8b8-230">Web/MVC</span></span>                               | <span data-ttu-id="6d8b8-231">1.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-231">1.0</span></span>        |
| <span data-ttu-id="6d8b8-232">Aplikacja sieci Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6d8b8-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="6d8b8-233">webapp, Razor</span><span class="sxs-lookup"><span data-stu-id="6d8b8-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="6d8b8-234">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-234">[C#]</span></span>         | <span data-ttu-id="6d8b8-235">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="6d8b8-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="6d8b8-236">2,2, 2,0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="6d8b8-237">ASP.NET Core ze Skośnością</span><span class="sxs-lookup"><span data-stu-id="6d8b8-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="6d8b8-238">kątow</span><span class="sxs-lookup"><span data-stu-id="6d8b8-238">angular</span></span>](#spa)                 | <span data-ttu-id="6d8b8-239">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-239">[C#]</span></span>         | <span data-ttu-id="6d8b8-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6d8b8-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="6d8b8-241">2,0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-241">2.0</span></span>        |
| <span data-ttu-id="6d8b8-242">ASP.NET Core z React.js</span><span class="sxs-lookup"><span data-stu-id="6d8b8-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="6d8b8-243">biern</span><span class="sxs-lookup"><span data-stu-id="6d8b8-243">react</span></span>](#spa)                   | <span data-ttu-id="6d8b8-244">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-244">[C#]</span></span>         | <span data-ttu-id="6d8b8-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6d8b8-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="6d8b8-246">2,0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-246">2.0</span></span>        |
| <span data-ttu-id="6d8b8-247">ASP.NET Core z React.js i Redux</span><span class="sxs-lookup"><span data-stu-id="6d8b8-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="6d8b8-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="6d8b8-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="6d8b8-249">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-249">[C#]</span></span>         | <span data-ttu-id="6d8b8-250">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6d8b8-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="6d8b8-251">2,0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-251">2.0</span></span>        |
| <span data-ttu-id="6d8b8-252">Biblioteka klas Razor</span><span class="sxs-lookup"><span data-stu-id="6d8b8-252">Razor Class Library</span></span>                          | [<span data-ttu-id="6d8b8-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="6d8b8-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="6d8b8-254">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-254">[C#]</span></span>         | <span data-ttu-id="6d8b8-255">Biblioteka klas sieci Web/Razor/Biblioteka/Razor</span><span class="sxs-lookup"><span data-stu-id="6d8b8-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="6d8b8-256">2.1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-256">2.1</span></span>        |
| <span data-ttu-id="6d8b8-257">Internetowy interfejs API platformy ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6d8b8-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="6d8b8-258">WebApi</span><span class="sxs-lookup"><span data-stu-id="6d8b8-258">webapi</span></span>](#webapi)               | <span data-ttu-id="6d8b8-259">[C#], F #</span><span class="sxs-lookup"><span data-stu-id="6d8b8-259">[C#], F#</span></span>     | <span data-ttu-id="6d8b8-260">Sieć Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="6d8b8-260">Web/WebAPI</span></span>                            | <span data-ttu-id="6d8b8-261">1.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-261">1.0</span></span>        |
| <span data-ttu-id="6d8b8-262">ASP.NET Core usługi gRPC</span><span class="sxs-lookup"><span data-stu-id="6d8b8-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="6d8b8-263">grpc</span><span class="sxs-lookup"><span data-stu-id="6d8b8-263">grpc</span></span>](#web-others)             | <span data-ttu-id="6d8b8-264">Znajd</span><span class="sxs-lookup"><span data-stu-id="6d8b8-264">[C#]</span></span>         | <span data-ttu-id="6d8b8-265">Sieć Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="6d8b8-265">Web/gRPC</span></span>                              | <span data-ttu-id="6d8b8-266">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-266">3.0</span></span>        |
| <span data-ttu-id="6d8b8-267">plik GITIGNORE dotnet</span><span class="sxs-lookup"><span data-stu-id="6d8b8-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="6d8b8-268">Config</span><span class="sxs-lookup"><span data-stu-id="6d8b8-268">Config</span></span>                                | <span data-ttu-id="6d8b8-269">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-269">3.0</span></span>        |
| <span data-ttu-id="6d8b8-270">global.jspliku</span><span class="sxs-lookup"><span data-stu-id="6d8b8-270">global.json file</span></span>                             | [<span data-ttu-id="6d8b8-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="6d8b8-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="6d8b8-272">Config</span><span class="sxs-lookup"><span data-stu-id="6d8b8-272">Config</span></span>                                | <span data-ttu-id="6d8b8-273">2,0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-273">2.0</span></span>        |
| <span data-ttu-id="6d8b8-274">Konfiguracja narzędzia NuGet</span><span class="sxs-lookup"><span data-stu-id="6d8b8-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="6d8b8-275">Config</span><span class="sxs-lookup"><span data-stu-id="6d8b8-275">Config</span></span>                                | <span data-ttu-id="6d8b8-276">1.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-276">1.0</span></span>        |
| <span data-ttu-id="6d8b8-277">Plik manifestu narzędzia lokalnego dotnet</span><span class="sxs-lookup"><span data-stu-id="6d8b8-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="6d8b8-278">Config</span><span class="sxs-lookup"><span data-stu-id="6d8b8-278">Config</span></span>                                | <span data-ttu-id="6d8b8-279">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-279">3.0</span></span>        |
| <span data-ttu-id="6d8b8-280">Konfiguracja sieci Web</span><span class="sxs-lookup"><span data-stu-id="6d8b8-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="6d8b8-281">Config</span><span class="sxs-lookup"><span data-stu-id="6d8b8-281">Config</span></span>                                | <span data-ttu-id="6d8b8-282">1.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-282">1.0</span></span>        |
| <span data-ttu-id="6d8b8-283">Plik rozwiązania</span><span class="sxs-lookup"><span data-stu-id="6d8b8-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="6d8b8-284">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="6d8b8-284">Solution</span></span>                              | <span data-ttu-id="6d8b8-285">1.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-285">1.0</span></span>        |
| <span data-ttu-id="6d8b8-286">Plik buforu protokołu</span><span class="sxs-lookup"><span data-stu-id="6d8b8-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="6d8b8-287">proto</span><span class="sxs-lookup"><span data-stu-id="6d8b8-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="6d8b8-288">Sieć Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="6d8b8-288">Web/gRPC</span></span>                              | <span data-ttu-id="6d8b8-289">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="6d8b8-290">Opcje</span><span class="sxs-lookup"><span data-stu-id="6d8b8-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="6d8b8-291">Wyświetla podsumowanie tego, co się stanie w przypadku uruchomienia danego polecenia, jeśli mogłoby to spowodować utworzenie szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="6d8b8-292">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="6d8b8-293">Wymusza wygenerowanie zawartości nawet w przypadku zmiany istniejących plików.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="6d8b8-294">Jest to wymagane, gdy wybrany szablon spowoduje zastąpienie istniejących plików w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="6d8b8-295">Drukuje pomoc dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-295">Prints out help for the command.</span></span> <span data-ttu-id="6d8b8-296">Może być wywoływana dla `dotnet new` samego polecenia lub dla dowolnego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="6d8b8-297">Na przykład `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="6d8b8-298">Instaluje pakiet szablonów z `PATH` lub `NUGET_ID` dostarczone.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="6d8b8-299">Jeśli chcesz zainstalować wersję wstępną pakietu szablonu, musisz określić wersję w formacie `<package-name>::<package-version>` .</span><span class="sxs-lookup"><span data-stu-id="6d8b8-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="6d8b8-300">Domyślnie program `dotnet new` przekazuje \* wersję, która reprezentuje najnowszą stabilną wersję pakietu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="6d8b8-301">Zobacz przykład w sekcji [przykładów](#examples) .</span><span class="sxs-lookup"><span data-stu-id="6d8b8-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="6d8b8-302">Jeśli wersja szablonu została już zainstalowana po uruchomieniu tego polecenia, szablon zostanie zaktualizowany do określonej wersji lub do najnowszej wersji stabilnej, jeśli nie określono żadnej wersji.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="6d8b8-303">Aby uzyskać informacje na temat tworzenia szablonów niestandardowych, zobacz [Szablony niestandardowe dla usługi dotnet New](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="6d8b8-304">Wyświetla listę szablonów zawierających określoną nazwę.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="6d8b8-305">Jeśli nazwa nie zostanie określona, program wyświetli listę wszystkich szablonów.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="6d8b8-306">Język szablonu do utworzenia.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-306">The language of the template to create.</span></span> <span data-ttu-id="6d8b8-307">Zaakceptowany język zależy od szablonu (zobacz wartości domyślne w sekcji [argumenty](#arguments) ).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="6d8b8-308">Nieprawidłowy dla niektórych szablonów.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6d8b8-309">Niektóre powłoki interpretują `#` jako znak specjalny.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="6d8b8-310">W takich przypadkach należy ująć wartość parametru Language w cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="6d8b8-311">Na przykład `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="6d8b8-312">Nazwa dla utworzonych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-312">The name for the created output.</span></span> <span data-ttu-id="6d8b8-313">Jeśli nazwa nie zostanie określona, zostanie użyta nazwa bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="6d8b8-314">Określa źródło NuGet do użycia podczas instalacji.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-314">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="6d8b8-315">Dostępne od wersji .NET Core 2,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-315">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="6d8b8-316">Lokalizacja, w której mają zostać umieszczone wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-316">Location to place the generated output.</span></span> <span data-ttu-id="6d8b8-317">Ustawieniem domyślnym jest bieżący katalog.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-317">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="6d8b8-318">Filtruje szablony w oparciu o dostępne typy.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-318">Filters templates based on available types.</span></span> <span data-ttu-id="6d8b8-319">Wstępnie zdefiniowane wartości to `project` i `item` .</span><span class="sxs-lookup"><span data-stu-id="6d8b8-319">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="6d8b8-320">Odinstalowuje pakiet szablonów w `PATH` lub `NUGET_ID` udostępniony.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-320">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="6d8b8-321">Gdy `<PATH|NUGET_ID>` wartość nie jest określona, wyświetlane są wszystkie aktualnie zainstalowane pakiety szablonów i skojarzone z nimi szablony.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-321">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="6d8b8-322">Podczas określania `NUGET_ID` nie należy umieszczać numeru wersji.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-322">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="6d8b8-323">Jeśli nie określisz parametru do tej opcji, polecenie wyświetli listę zainstalowanych szablonów i szczegółowe informacje o nich.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-323">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6d8b8-324">Aby odinstalować szablon przy użyciu programu `PATH` , należy w pełni zakwalifikować ścieżkę.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-324">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="6d8b8-325">Na przykład *C:/Users/ \<USER> /Documents/templates/GarciaSoftware.ConsoleTemplate.CSharp* będzie działał, ale *./GarciaSoftware.ConsoleTemplate.CSharp* z folderu zawierającego nie będzie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-325">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="6d8b8-326">Nie dołączaj ostatecznego ukośnika katalogu w ścieżce szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-326">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="6d8b8-327">Sprawdza, czy są dostępne aktualizacje pakietów szablonów, które są obecnie zainstalowane i instaluje je.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-327">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="6d8b8-328">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-328">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="6d8b8-329">Sprawdza, czy są dostępne aktualizacje pakietów szablonów, które są obecnie zainstalowane.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-329">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="6d8b8-330">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-330">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="6d8b8-331">Opcje szablonu</span><span class="sxs-lookup"><span data-stu-id="6d8b8-331">Template options</span></span>

<span data-ttu-id="6d8b8-332">Każdy szablon projektu może mieć dodatkowe opcje dostępne.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-332">Each project template may have additional options available.</span></span> <span data-ttu-id="6d8b8-333">Szablony podstawowe mają następujące dodatkowe opcje:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-333">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="6d8b8-334">console</span><span class="sxs-lookup"><span data-stu-id="6d8b8-334">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="6d8b8-335">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-335">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6d8b8-336">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-336">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="6d8b8-337">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-337">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="6d8b8-338">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="6d8b8-338">SDK version</span></span> | <span data-ttu-id="6d8b8-339">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="6d8b8-339">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="6d8b8-340">3,1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="6d8b8-341">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="6d8b8-342">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="6d8b8-343">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="6d8b8-344">Nieobsługiwane dla języka F #.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-344">Not supported for F#.</span></span> <span data-ttu-id="6d8b8-345">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="6d8b8-346">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="6d8b8-347">Jeśli określony, nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="6d8b8-348">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="6d8b8-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="6d8b8-350">określono</span><span class="sxs-lookup"><span data-stu-id="6d8b8-350">classlib</span></span>

- <span data-ttu-id="6d8b8-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="6d8b8-352">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6d8b8-353">Wartości: `netcoreapp<version>` Aby utworzyć bibliotekę klas platformy .NET Core lub `netstandard<version>` utworzyć bibliotekę klas .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-353">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="6d8b8-354">Wartość domyślna to `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-354">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="6d8b8-355">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="6d8b8-356">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="6d8b8-357">Nieobsługiwane dla języka F #.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-357">Not supported for F#.</span></span> <span data-ttu-id="6d8b8-358">Dostępne od wersji .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="6d8b8-359">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="6d8b8-360">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6d8b8-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="6d8b8-362">WPF, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="6d8b8-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="6d8b8-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="6d8b8-364">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6d8b8-365">Wartość domyślna to `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-365">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="6d8b8-366">Dostępne od wersji .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="6d8b8-367">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="6d8b8-368">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="6d8b8-369">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="6d8b8-370">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6d8b8-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="6d8b8-372">WinForms, winformslib</span><span class="sxs-lookup"><span data-stu-id="6d8b8-372">winforms, winformslib</span></span>

- <span data-ttu-id="6d8b8-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="6d8b8-374">Ustawia `LangVersion` Właściwość w utworzonym pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="6d8b8-375">Na przykład użyj, `--langVersion 7.3` Aby użyć języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="6d8b8-376">Listę domyślnych wersji języka C# można znaleźć w temacie [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="6d8b8-377">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6d8b8-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="6d8b8-379">proces roboczy, GRPC</span><span class="sxs-lookup"><span data-stu-id="6d8b8-379">worker, grpc</span></span>

- <span data-ttu-id="6d8b8-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="6d8b8-381">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6d8b8-382">Wartość domyślna to `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="6d8b8-383">Dostępne od wersji .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="6d8b8-384">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="6d8b8-385">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6d8b8-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="6d8b8-387">MSTest, xUnit</span><span class="sxs-lookup"><span data-stu-id="6d8b8-387">mstest, xunit</span></span>

- <span data-ttu-id="6d8b8-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="6d8b8-389">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6d8b8-390">Opcja dostępna od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="6d8b8-391">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="6d8b8-392">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="6d8b8-392">SDK version</span></span> | <span data-ttu-id="6d8b8-393">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="6d8b8-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="6d8b8-394">3,1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-394">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="6d8b8-395">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-395">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="6d8b8-396">Włącza pakowanie dla projektu przy użyciu [pakietu dotnet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="6d8b8-397">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-397">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6d8b8-398">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-398">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="6d8b8-399">NUnit</span><span class="sxs-lookup"><span data-stu-id="6d8b8-399">nunit</span></span>

- <span data-ttu-id="6d8b8-400">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-400">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="6d8b8-401">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-401">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="6d8b8-402">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-402">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="6d8b8-403">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="6d8b8-403">SDK version</span></span> | <span data-ttu-id="6d8b8-404">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="6d8b8-404">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="6d8b8-405">3,1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-405">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="6d8b8-406">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-406">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="6d8b8-407">2.2</span><span class="sxs-lookup"><span data-stu-id="6d8b8-407">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="6d8b8-408">2.1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-408">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="6d8b8-409">Włącza pakowanie dla projektu przy użyciu [pakietu dotnet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-409">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="6d8b8-410">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-410">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6d8b8-411">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-411">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="6d8b8-412">stronic</span><span class="sxs-lookup"><span data-stu-id="6d8b8-412">page</span></span>

- <span data-ttu-id="6d8b8-413">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-413">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="6d8b8-414">Przestrzeń nazw dla wygenerowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-414">Namespace for the generated code.</span></span> <span data-ttu-id="6d8b8-415">Wartość domyślna to `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-415">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="6d8b8-416">Tworzy stronę bez PageModel.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-416">Creates the page without a PageModel.</span></span>

<span data-ttu-id="6d8b8-417">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-417">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="6d8b8-418">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="6d8b8-418">viewimports, proto</span></span>

- <span data-ttu-id="6d8b8-419">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-419">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="6d8b8-420">Przestrzeń nazw dla wygenerowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-420">Namespace for the generated code.</span></span> <span data-ttu-id="6d8b8-421">Wartość domyślna to `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-421">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="6d8b8-422">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-422">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="6d8b8-423">blazorserver</span><span class="sxs-lookup"><span data-stu-id="6d8b8-423">blazorserver</span></span>

- <span data-ttu-id="6d8b8-424">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-424">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="6d8b8-425">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-425">The type of authentication to use.</span></span> <span data-ttu-id="6d8b8-426">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-426">The possible values are:</span></span>

  - <span data-ttu-id="6d8b8-427">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-427">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="6d8b8-428">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-428">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="6d8b8-429">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-429">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="6d8b8-430">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-430">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="6d8b8-431">`MultiOrg` -Organizacja uwierzytelnianie dla wielu dzierżawców.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-431">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="6d8b8-432">`Windows` — Uwierzytelnianie systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-432">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="6d8b8-433">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-433">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="6d8b8-434">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-434">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-435">Wartość domyślna to `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-435">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="6d8b8-436">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-436">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="6d8b8-437">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-437">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="6d8b8-438">Identyfikator zasad resetowania hasła dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-438">The reset password policy ID for this project.</span></span> <span data-ttu-id="6d8b8-439">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-439">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="6d8b8-440">Edytuj identyfikator zasad profilu dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-440">The edit profile policy ID for this project.</span></span> <span data-ttu-id="6d8b8-441">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-441">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="6d8b8-442">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-442">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="6d8b8-443">Używanie z usługą `SingleOrg` lub `MultiOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-443">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="6d8b8-444">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-444">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="6d8b8-445">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-445">The Client ID for this project.</span></span> <span data-ttu-id="6d8b8-446">Użyj z `IndividualB2C` , `SingleOrg` lub `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-446">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="6d8b8-447">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-447">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="6d8b8-448">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-448">The domain for the directory tenant.</span></span> <span data-ttu-id="6d8b8-449">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-449">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-450">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-450">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="6d8b8-451">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-451">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="6d8b8-452">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-452">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6d8b8-453">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-453">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="6d8b8-454">Ścieżka żądania w ścieżce podstawowej identyfikatora URI przekierowania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-454">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="6d8b8-455">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-455">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-456">Wartość domyślna to `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-456">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="6d8b8-457">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-457">Allows this application read-access to the directory.</span></span> <span data-ttu-id="6d8b8-458">Dotyczy tylko `SingleOrg` `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-458">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="6d8b8-459">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-459">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="6d8b8-460">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-460">Turns off HTTPS.</span></span> <span data-ttu-id="6d8b8-461">Ta opcja ma zastosowanie tylko wtedy, gdy,, `Individual` `IndividualB2C` `SingleOrg` lub `MultiOrg` nie są używane w programie `--auth` .</span><span class="sxs-lookup"><span data-stu-id="6d8b8-461">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="6d8b8-462">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-462">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6d8b8-463">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-463">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="6d8b8-464">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-464">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6d8b8-465">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-465">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="6d8b8-466">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="6d8b8-466">blazorwasm</span></span>

- <span data-ttu-id="6d8b8-467">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-467">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="6d8b8-468">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-468">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="6d8b8-469">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-469">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="6d8b8-470">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="6d8b8-470">SDK version</span></span> | <span data-ttu-id="6d8b8-471">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="6d8b8-471">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="6d8b8-472">5,0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-472">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="6d8b8-473">3,1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-473">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="6d8b8-474">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-474">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="6d8b8-475">Zawiera ASP.NET Core hosta dla :::no-loc(Blazor)::: :::no-loc(WebAssembly)::: aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-475">Includes an ASP.NET Core host for the :::no-loc(Blazor)::: :::no-loc(WebAssembly)::: app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="6d8b8-476">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-476">The type of authentication to use.</span></span> <span data-ttu-id="6d8b8-477">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-477">The possible values are:</span></span>

  - <span data-ttu-id="6d8b8-478">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-478">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="6d8b8-479">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-479">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="6d8b8-480">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-480">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="6d8b8-481">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-481">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="6d8b8-482">Urząd dostawcy OIDC.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-482">The authority of the OIDC provider.</span></span> <span data-ttu-id="6d8b8-483">Użyj z `Individual` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-483">Use with `Individual` authentication.</span></span> <span data-ttu-id="6d8b8-484">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-484">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="6d8b8-485">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-485">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="6d8b8-486">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-486">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-487">Wartość domyślna to `https://aadB2CInstance.b2clogin.com/`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-487">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="6d8b8-488">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-488">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="6d8b8-489">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-489">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="6d8b8-490">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-490">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="6d8b8-491">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-491">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6d8b8-492">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-492">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="6d8b8-493">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-493">The Client ID for this project.</span></span> <span data-ttu-id="6d8b8-494">Używanie z `IndividualB2C` , `SingleOrg` lub `Individual` uwierzytelnianie w scenariuszach autonomicznych.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-494">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="6d8b8-495">Wartość domyślna to `33333333-3333-3333-33333333333333333`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-495">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="6d8b8-496">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-496">The domain for the directory tenant.</span></span> <span data-ttu-id="6d8b8-497">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-497">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-498">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-498">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="6d8b8-499">Identyfikator URI identyfikatora aplikacji dla interfejsu API serwera, który chcesz wywołać.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-499">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="6d8b8-500">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-500">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-501">Wartość domyślna to `api.id.uri`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-501">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="6d8b8-502">Identyfikator klienta dla interfejsu API, który jest hostem serwera.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-502">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="6d8b8-503">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-503">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-504">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-504">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="6d8b8-505">Zakres interfejsu API, do którego klient musi zażądać tokenu dostępu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-505">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="6d8b8-506">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-506">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-507">Wartość domyślna to `user_impersonation`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-507">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="6d8b8-508">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-508">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="6d8b8-509">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-509">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6d8b8-510">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-510">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="6d8b8-511">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-511">Allows this application read-access to the directory.</span></span> <span data-ttu-id="6d8b8-512">Dotyczy tylko `SingleOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-512">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="6d8b8-513">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-513">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="6d8b8-514">tworzy progresywną aplikację sieci Web (PWA), która obsługuje instalację i użycie w trybie offline.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-514">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="6d8b8-515">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-515">Turns off HTTPS.</span></span> <span data-ttu-id="6d8b8-516">Ta opcja ma zastosowanie tylko wtedy `Individual` , gdy `IndividualB2C` lub `SingleOrg` nie są używane dla `--auth` .</span><span class="sxs-lookup"><span data-stu-id="6d8b8-516">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="6d8b8-517">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-517">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6d8b8-518">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-518">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="6d8b8-519">Adres URL interfejsu API do wywołania z aplikacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-519">URL of the API to call from the web app.</span></span> <span data-ttu-id="6d8b8-520">Dotyczy tylko `SingleOrg` `IndividualB2C` uwierzytelniania bez określonego hosta ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-520">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="6d8b8-521">Wartość domyślna to `https://graph.microsoft.com/v1.0/me`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-521">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="6d8b8-522">Określa, czy aplikacja sieci Web wywołuje Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-522">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="6d8b8-523">Dotyczy tylko `SingleOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-523">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="6d8b8-524">Zakresy do żądania wywołania interfejsu API z aplikacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-524">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="6d8b8-525">Dotyczy tylko `SingleOrg` `IndividualB2C` uwierzytelniania bez określonego hosta ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-525">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="6d8b8-526">Wartość domyślna to `user.read`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-526">The default is `user.read`.</span></span>

<span data-ttu-id="6d8b8-527">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-527">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="6d8b8-528">web</span><span class="sxs-lookup"><span data-stu-id="6d8b8-528">web</span></span>

- <span data-ttu-id="6d8b8-529">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-529">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="6d8b8-530">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="6d8b8-531">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6d8b8-532">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="6d8b8-533">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="6d8b8-534">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="6d8b8-534">SDK version</span></span> | <span data-ttu-id="6d8b8-535">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="6d8b8-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="6d8b8-536">3,1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="6d8b8-537">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="6d8b8-538">2.1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-538">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="6d8b8-539">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="6d8b8-540">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-540">Turns off HTTPS.</span></span>

<span data-ttu-id="6d8b8-541">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-541">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="6d8b8-542">MVC, webapp</span><span class="sxs-lookup"><span data-stu-id="6d8b8-542">mvc, webapp</span></span>

- <span data-ttu-id="6d8b8-543">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-543">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="6d8b8-544">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-544">The type of authentication to use.</span></span> <span data-ttu-id="6d8b8-545">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-545">The possible values are:</span></span>

  - <span data-ttu-id="6d8b8-546">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="6d8b8-547">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-547">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="6d8b8-548">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-548">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="6d8b8-549">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-549">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="6d8b8-550">`MultiOrg` -Organizacja uwierzytelnianie dla wielu dzierżawców.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-550">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="6d8b8-551">`Windows` — Uwierzytelnianie systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="6d8b8-552">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="6d8b8-553">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-554">Wartość domyślna to `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="6d8b8-555">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="6d8b8-556">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-556">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="6d8b8-557">Identyfikator zasad resetowania hasła dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-557">The reset password policy ID for this project.</span></span> <span data-ttu-id="6d8b8-558">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-558">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="6d8b8-559">Edytuj identyfikator zasad profilu dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-559">The edit profile policy ID for this project.</span></span> <span data-ttu-id="6d8b8-560">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-560">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="6d8b8-561">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-561">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="6d8b8-562">Używanie z usługą `SingleOrg` lub `MultiOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-562">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="6d8b8-563">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-563">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="6d8b8-564">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-564">The Client ID for this project.</span></span> <span data-ttu-id="6d8b8-565">Użyj z `IndividualB2C` , `SingleOrg` lub `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-565">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="6d8b8-566">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-566">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="6d8b8-567">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-567">The domain for the directory tenant.</span></span> <span data-ttu-id="6d8b8-568">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-568">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-569">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-569">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="6d8b8-570">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-570">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="6d8b8-571">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-571">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6d8b8-572">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-572">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="6d8b8-573">Ścieżka żądania w ścieżce podstawowej identyfikatora URI przekierowania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-573">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="6d8b8-574">Używanie z usługą `SingleOrg` lub `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-574">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-575">Wartość domyślna to `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-575">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="6d8b8-576">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-576">Allows this application read-access to the directory.</span></span> <span data-ttu-id="6d8b8-577">Dotyczy tylko `SingleOrg` `MultiOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-577">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="6d8b8-578">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-578">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="6d8b8-579">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-579">Turns off HTTPS.</span></span> <span data-ttu-id="6d8b8-580">Ta opcja ma zastosowanie tylko wtedy, gdy,, `Individual` `IndividualB2C` `SingleOrg` lub `MultiOrg` nie jest używany.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-580">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="6d8b8-581">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-581">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6d8b8-582">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-582">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="6d8b8-583">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-583">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6d8b8-584">Opcja dostępna od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-584">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="6d8b8-585">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-585">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="6d8b8-586">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="6d8b8-586">SDK version</span></span> | <span data-ttu-id="6d8b8-587">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="6d8b8-587">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="6d8b8-588">3,1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-588">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="6d8b8-589">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-589">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="6d8b8-590">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-590">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="6d8b8-591">Zawiera BrowserLink w projekcie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-591">Includes BrowserLink in the project.</span></span> <span data-ttu-id="6d8b8-592">Opcja nie jest dostępna w programie .NET Core 2,2 i 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-592">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="6d8b8-593">Określa, czy projekt jest skonfigurowany do używania [kompilacji środowiska uruchomieniowego Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) w kompilacjach debugowania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-593">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="6d8b8-594">Opcja dostępna od wersji .NET Core 3.1.201 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-594">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="6d8b8-595">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-595">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="6d8b8-596">kątowy, reagowanie</span><span class="sxs-lookup"><span data-stu-id="6d8b8-596">angular, react</span></span>

- <span data-ttu-id="6d8b8-597">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-597">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="6d8b8-598">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-598">The type of authentication to use.</span></span> <span data-ttu-id="6d8b8-599">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-599">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="6d8b8-600">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-600">The possible values are:</span></span>

  - <span data-ttu-id="6d8b8-601">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-601">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="6d8b8-602">`Individual` -Uwierzytelnianie indywidualne.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-602">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="6d8b8-603">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="6d8b8-604">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-604">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="6d8b8-605">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-605">Turns off HTTPS.</span></span> <span data-ttu-id="6d8b8-606">Ta opcja ma zastosowanie tylko wtedy, gdy uwierzytelnianie jest `None` .</span><span class="sxs-lookup"><span data-stu-id="6d8b8-606">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="6d8b8-607">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6d8b8-608">Dotyczy tylko `Individual` `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-608">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-609">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-609">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="6d8b8-610">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-610">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6d8b8-611">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-611">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="6d8b8-612">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-612">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="6d8b8-613">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="6d8b8-613">SDK version</span></span> | <span data-ttu-id="6d8b8-614">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="6d8b8-614">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="6d8b8-615">3,1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-615">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="6d8b8-616">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-616">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="6d8b8-617">2.1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-617">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="6d8b8-618">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-618">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="6d8b8-619">reactredux</span><span class="sxs-lookup"><span data-stu-id="6d8b8-619">reactredux</span></span>

- <span data-ttu-id="6d8b8-620">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-620">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="6d8b8-621">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-621">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="6d8b8-622">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-622">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6d8b8-623">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-623">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="6d8b8-624">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-624">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="6d8b8-625">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="6d8b8-625">SDK version</span></span> | <span data-ttu-id="6d8b8-626">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="6d8b8-626">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="6d8b8-627">3,1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-627">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="6d8b8-628">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-628">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="6d8b8-629">2.1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-629">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="6d8b8-630">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-630">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="6d8b8-631">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-631">Turns off HTTPS.</span></span>

<span data-ttu-id="6d8b8-632">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-632">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="6d8b8-633">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="6d8b8-633">razorclasslib</span></span>

- <span data-ttu-id="6d8b8-634">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-634">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="6d8b8-635">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-635">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="6d8b8-636">Obsługuje dodawanie tradycyjnych stron Razor i widoków oprócz składników do tej biblioteki.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-636">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="6d8b8-637">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-637">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="6d8b8-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-638">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="6d8b8-639">WebApi</span><span class="sxs-lookup"><span data-stu-id="6d8b8-639">webapi</span></span>

- <span data-ttu-id="6d8b8-640">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-640">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="6d8b8-641">Typ uwierzytelniania do użycia.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-641">The type of authentication to use.</span></span> <span data-ttu-id="6d8b8-642">Możliwe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-642">The possible values are:</span></span>

  - <span data-ttu-id="6d8b8-643">`None` -Brak uwierzytelniania (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="6d8b8-643">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="6d8b8-644">`IndividualB2C` -Uwierzytelnianie indywidualne przy użyciu Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-644">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="6d8b8-645">`SingleOrg` -Organizacja uwierzytelnianie dla pojedynczej dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-645">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="6d8b8-646">`Windows` — Uwierzytelnianie systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-646">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="6d8b8-647">Wystąpienie Azure Active Directory B2C, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-647">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="6d8b8-648">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-648">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="6d8b8-649">Wartość domyślna to `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-649">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="6d8b8-650">Identyfikator zasad logowania i rejestrowania dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-650">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="6d8b8-651">Użyj z `IndividualB2C` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-651">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="6d8b8-652">Wystąpienie Azure Active Directory, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-652">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="6d8b8-653">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-653">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6d8b8-654">Wartość domyślna to `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-654">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="6d8b8-655">Identyfikator klienta dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-655">The Client ID for this project.</span></span> <span data-ttu-id="6d8b8-656">Używanie z usługą `IndividualB2C` lub `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-656">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="6d8b8-657">Wartość domyślna to `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-657">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="6d8b8-658">Domena dzierżawy katalogu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-658">The domain for the directory tenant.</span></span> <span data-ttu-id="6d8b8-659">Używanie z usługą `IndividualB2C` lub `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-659">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="6d8b8-660">Wartość domyślna to `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-660">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="6d8b8-661">Identyfikator TenantId katalogu, z którym ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-661">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="6d8b8-662">Użyj z `SingleOrg` uwierzytelnianiem.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-662">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6d8b8-663">Wartość domyślna to `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-663">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="6d8b8-664">Zezwala tej aplikacji na dostęp do odczytu do katalogu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-664">Allows this application read-access to the directory.</span></span> <span data-ttu-id="6d8b8-665">Dotyczy tylko `SingleOrg` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-665">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="6d8b8-666">Wyklucza *launchSettings.js* z wygenerowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-666">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="6d8b8-667">Wyłącza protokół HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-667">Turns off HTTPS.</span></span> <span data-ttu-id="6d8b8-668">`app.UseHsts` i `app.UseHttpsRedirection` nie są dodawane do `Startup.Configure` .</span><span class="sxs-lookup"><span data-stu-id="6d8b8-668">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="6d8b8-669">Ta opcja ma zastosowanie tylko wtedy `IndividualB2C` , gdy lub `SingleOrg` nie są używane do uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-669">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="6d8b8-670">Należy używać LocalDB zamiast oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-670">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6d8b8-671">Dotyczy tylko `IndividualB2C` uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-671">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="6d8b8-672">Określa [platformę](../../standard/frameworks.md) docelową.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-672">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6d8b8-673">Opcja nie jest dostępna w zestawie SDK platformy .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-673">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="6d8b8-674">W poniższej tabeli wymieniono wartości domyślne zgodnie z używanym numerem wersji zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-674">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="6d8b8-675">Wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="6d8b8-675">SDK version</span></span> | <span data-ttu-id="6d8b8-676">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="6d8b8-676">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="6d8b8-677">3,1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-677">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="6d8b8-678">3.0</span><span class="sxs-lookup"><span data-stu-id="6d8b8-678">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="6d8b8-679">2.1</span><span class="sxs-lookup"><span data-stu-id="6d8b8-679">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="6d8b8-680">Nie wykonuje przywracania niejawnego podczas tworzenia projektu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-680">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6d8b8-681">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6d8b8-681">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="6d8b8-682">globaljson</span><span class="sxs-lookup"><span data-stu-id="6d8b8-682">globaljson</span></span>

- <span data-ttu-id="6d8b8-683">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="6d8b8-683">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="6d8b8-684">Określa wersję zestaw .NET Core SDK, która ma być używana w *global.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-684">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="6d8b8-685">Przykłady</span><span class="sxs-lookup"><span data-stu-id="6d8b8-685">Examples</span></span>

- <span data-ttu-id="6d8b8-686">Utwórz projekt aplikacji konsolowej w języku C#, określając nazwę szablonu:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-686">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="6d8b8-687">Utwórz projekt aplikacji konsolowej F # w bieżącym katalogu:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-687">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="6d8b8-688">Utwórz projekt biblioteki klas .NET Standard w określonym katalogu:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-688">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="6d8b8-689">Utwórz nowy projekt ASP.NET Core C# MVC w bieżącym katalogu bez uwierzytelniania:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-689">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="6d8b8-690">Utwórz nowy projekt xUnit:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-690">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="6d8b8-691">Wyświetl listę wszystkich szablonów dostępnych dla szablonów aplikacji jednostronicowych (SPA):</span><span class="sxs-lookup"><span data-stu-id="6d8b8-691">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="6d8b8-692">Wyświetl listę wszystkich szablonów pasujących *do* podciągu.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-692">List all templates matching the *we* substring.</span></span> <span data-ttu-id="6d8b8-693">Nie znaleziono dokładnego dopasowania, więc Dopasowywanie podciągów działa w odniesieniu do kolumn krótkich nazw i nazw.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-693">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="6d8b8-694">Podjęto próbę wywołania szablonu zgodnego z parametrem *ng*.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-694">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="6d8b8-695">Jeśli nie można ustalić pojedynczego dopasowania, należy wyświetlić listę szablonów, które są dopasowań częściowych.</span><span class="sxs-lookup"><span data-stu-id="6d8b8-695">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="6d8b8-696">Zainstaluj wersję 2,0 szablonów SPA dla ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-696">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="6d8b8-697">Wyświetl listę zainstalowanych szablonów i szczegółowe informacje o nich, w tym sposoby ich odinstalowywania:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-697">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="6d8b8-698">Utwórz *global.js* w bieżącym katalogu, ustawiając wersję zestawu SDK na 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="6d8b8-698">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="6d8b8-699">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6d8b8-699">See also</span></span>

- [<span data-ttu-id="6d8b8-700">Szablony niestandardowe dla nowego dotnet</span><span class="sxs-lookup"><span data-stu-id="6d8b8-700">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="6d8b8-701">Tworzenie szablonu niestandardowego dla polecenia dotnet new</span><span class="sxs-lookup"><span data-stu-id="6d8b8-701">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="6d8b8-702">dotnet/dotnet-Template-przykłady repozytorium GitHub</span><span class="sxs-lookup"><span data-stu-id="6d8b8-702">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="6d8b8-703">Dostępne szablony dla nowego dotnet</span><span class="sxs-lookup"><span data-stu-id="6d8b8-703">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
