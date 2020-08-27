---
ms.openlocfilehash: 35dd8db243b03e1dfd6311195ec97673cf114877
ms.sourcegitcommit: 60dc0a11ebdd77f969f41891d5cca06335cda6a7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2020
ms.locfileid: "88957692"
---
### <a name="razor-razortemplateengine-api-removed"></a>Razor: Usunięto interfejs API RazorTemplateEngine

Interfejs API [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) został usunięty i zastąpiony przez <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine> .

Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 25215](https://github.com/dotnet/aspnetcore/issues/25215).

#### <a name="version-introduced"></a>Wprowadzona wersja

3,0

#### <a name="old-behavior"></a>Stare zachowanie

Aparat szablonów może być tworzony i używany do analizowania i generowania kodu dla plików Razor.

#### <a name="new-behavior"></a>Nowe zachowanie

`RazorProjectEngine` można utworzyć i podać ten sam typ informacji, jak `RazorTemplateEngine` analizowanie i generowanie kodu dla plików Razor. `RazorProjectEngine` Program udostępnia również dodatkowe poziomy konfiguracji.

#### <a name="reason-for-change"></a>Przyczyna zmiany

`RazorTemplateEngine` był zbyt ściśle połączony z istniejącymi implementacjami. To ścisłe sprzężenie prowadzi do większej liczby pytań podczas próby poprawnego skonfigurowania potoku analizowania/generowania Razor.

#### <a name="recommended-action"></a>Zalecana akcja

Użyj `RazorProjectEngine` zamiast `RazorTemplateEngine` . Rozważ następujące przykłady.

##### <a name="create-and-configure-the-razorprojectengine"></a>Utwórz i skonfiguruj RazorProjectEngine

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

##### <a name="generate-code-for-a-razor-file"></a>Generuj kod dla pliku Razor

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

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2)
- [RazorTemplateEngineOptions](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengineoptions?view=aspnetcore-2.2)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngine`
- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngineOptions`

-->
