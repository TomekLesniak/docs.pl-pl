---
ms.openlocfilehash: 35dd8db243b03e1dfd6311195ec97673cf114877
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032847"
---
### <a name="razor-razortemplateengine-api-removed"></a><span data-ttu-id="c0f1a-101">Razor: Usunięto interfejs API RazorTemplateEngine</span><span class="sxs-lookup"><span data-stu-id="c0f1a-101">Razor: RazorTemplateEngine API removed</span></span>

<span data-ttu-id="c0f1a-102">Interfejs API [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) został usunięty i zastąpiony przez <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine> .</span><span class="sxs-lookup"><span data-stu-id="c0f1a-102">The [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) API was removed and replaced with <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>.</span></span>

<span data-ttu-id="c0f1a-103">Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 25215](https://github.com/dotnet/aspnetcore/issues/25215).</span><span class="sxs-lookup"><span data-stu-id="c0f1a-103">For discussion, see GitHub issue [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c0f1a-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="c0f1a-104">Version introduced</span></span>

<span data-ttu-id="c0f1a-105">3.0</span><span class="sxs-lookup"><span data-stu-id="c0f1a-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c0f1a-106">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="c0f1a-106">Old behavior</span></span>

<span data-ttu-id="c0f1a-107">Aparat szablonów może być tworzony i używany do analizowania i generowania kodu dla plików Razor.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-107">A template engine can be created and used to parse and generate code for Razor files.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c0f1a-108">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="c0f1a-108">New behavior</span></span>

<span data-ttu-id="c0f1a-109">`RazorProjectEngine` można utworzyć i podać ten sam typ informacji, jak `RazorTemplateEngine` analizowanie i generowanie kodu dla plików Razor.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-109">`RazorProjectEngine` can be created and provided the same type of information as `RazorTemplateEngine` to parse and generate code for Razor files.</span></span> <span data-ttu-id="c0f1a-110">`RazorProjectEngine` Program udostępnia również dodatkowe poziomy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-110">`RazorProjectEngine` also provides extra levels of configuration.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c0f1a-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="c0f1a-111">Reason for change</span></span>

<span data-ttu-id="c0f1a-112">`RazorTemplateEngine` był zbyt ściśle połączony z istniejącymi implementacjami.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-112">`RazorTemplateEngine` was too tightly coupled to the existing implementations.</span></span> <span data-ttu-id="c0f1a-113">To ścisłe sprzężenie prowadzi do większej liczby pytań podczas próby poprawnego skonfigurowania potoku analizowania/generowania Razor.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-113">This tight coupling led to more questions when trying to properly configure a Razor parsing/generation pipeline.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c0f1a-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="c0f1a-114">Recommended action</span></span>

<span data-ttu-id="c0f1a-115">Użyj `RazorProjectEngine` zamiast `RazorTemplateEngine` .</span><span class="sxs-lookup"><span data-stu-id="c0f1a-115">Use `RazorProjectEngine` instead of `RazorTemplateEngine`.</span></span> <span data-ttu-id="c0f1a-116">Rozważ następujące przykłady.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-116">Consider the following examples.</span></span>

##### <a name="create-and-configure-the-razorprojectengine"></a><span data-ttu-id="c0f1a-117">Utwórz i skonfiguruj RazorProjectEngine</span><span class="sxs-lookup"><span data-stu-id="c0f1a-117">Create and configure the RazorProjectEngine</span></span>

```csharp
RazorProjectEngine projectEngine =
    RazorProjectEngine.Create(RazorConfiguration.Default,
        RazorProjectFileSystem.Create(@"C:\source\repos\ConsoleApp4\ConsoleApp4"),
        builder =>
        {
            builder.ConfigureClass((document, classNode) =>
            {
                classNode.ClassName = "MyClassName";

                // Can also configure other aspects of the class here.
            });

            // More configuration can go here
        });
```

##### <a name="generate-code-for-a-razor-file"></a><span data-ttu-id="c0f1a-118">Generuj kod dla pliku Razor</span><span class="sxs-lookup"><span data-stu-id="c0f1a-118">Generate code for a Razor file</span></span>

```csharp
RazorProjectItem item = projectEngine.FileSystem.GetItem(
    @"C:\source\repos\ConsoleApp4\ConsoleApp4\Example.cshtml",
    FileKinds.Legacy);
RazorCodeDocument output = projectEngine.Process(item);

// Things available
RazorSyntaxTree syntaxTree = output.GetSyntaxTree();
DocumentIntermediateNode intermediateDocument =
    output.GetDocumentIntermediateNode();
RazorCSharpDocument csharpDocument = output.GetCSharpDocument();
```

#### <a name="category"></a><span data-ttu-id="c0f1a-119">Kategoria</span><span class="sxs-lookup"><span data-stu-id="c0f1a-119">Category</span></span>

<span data-ttu-id="c0f1a-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0f1a-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c0f1a-121">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="c0f1a-121">Affected APIs</span></span>

- [<span data-ttu-id="c0f1a-122">RazorTemplateEngine</span><span class="sxs-lookup"><span data-stu-id="c0f1a-122">RazorTemplateEngine</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2)
- [<span data-ttu-id="c0f1a-123">RazorTemplateEngineOptions</span><span class="sxs-lookup"><span data-stu-id="c0f1a-123">RazorTemplateEngineOptions</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengineoptions?view=aspnetcore-2.2)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngine`
- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngineOptions`

-->
