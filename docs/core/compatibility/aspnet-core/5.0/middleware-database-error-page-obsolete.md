---
title: 'Zmiana podziału: oprogramowanie pośredniczące: Strona błędu bazy danych oznaczona jako przestarzała'
description: 'Informacje o istotnej zmianie w ASP.NET Core 5,0 zatytułowanym oprogramowanie pośredniczące: Strona błędu bazy danych oznaczona jako przestarzała'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f828b5e20c2a9a709d675e435caa99727aebd5b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761603"
---
# <a name="middleware-database-error-page-marked-as-obsolete"></a>Oprogramowanie pośredniczące: Strona błędu bazy danych oznaczona jako przestarzała

[DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) i skojarzone z nią metody rozszerzenia zostały oznaczone jako przestarzałe w ASP.NET Core 5,0. Oprogramowanie pośredniczące i metody rozszerzające zostaną usunięte w ASP.NET Core 6,0. Funkcje te będą udostępniane przez program `DatabaseDeveloperPageExceptionFilter` i jego metody rozszerzające.

Aby zapoznać się z omówieniem, zobacz problem z usługą GitHub w usłudze [dotnet/aspnetcore # 24987](https://github.com/dotnet/aspnetcore/issues/24987).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC 1

## <a name="old-behavior"></a>Stare zachowanie

`DatabaseErrorPageMiddleware` i skojarzone metody rozszerzenia nie były przestarzałe.

## <a name="new-behavior"></a>Nowe zachowanie

`DatabaseErrorPageMiddleware` i skojarzone z nią metody rozszerzenia są przestarzałe.

## <a name="reason-for-change"></a>Przyczyna zmiany

`DatabaseErrorPageMiddleware` został zmigrowany do rozszerzalnego interfejsu API na [stronie wyjątku dewelopera](/aspnet/core/fundamentals/error-handling#developer-exception-page). Aby uzyskać więcej informacji na temat rozszerzalnego interfejsu API, zobacz sekcję dotyczącą usługi GitHub wydaj polecenie [dotnet/aspnetcore # 8536](https://github.com/dotnet/aspnetcore/issues/8536).

## <a name="recommended-action"></a>Zalecana akcja

Wykonaj poniższe czynności:

1. Przestań używać `DatabaseErrorPageMiddleware` w projekcie. Na przykład Usuń `UseDatabaseErrorPage` wywołanie metody z `Startup.Configure` :

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. Dodaj stronę wyjątku dewelopera do projektu. Na przykład Wywołaj <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> metodę w `Startup.Configure` :

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. Dodaj pakiet NuGet [Microsoft. AspNetCore. Diagnostics. EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) do pliku projektu.

1. Dodaj filtr wyjątku strony dewelopera bazy danych do kolekcji usług. Na przykład Wywołaj `AddDatabaseDeveloperPageExceptionFilter` metodę w `Startup.ConfigureServices` :

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

## <a name="affected-apis"></a>Dotyczy interfejsów API

- [Microsoft. AspNetCore. Builder. DatabaseErrorPageExtensions. UseDatabaseErrorPage](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [Microsoft. AspNetCore. Diagnostics. EntityFrameworkCore. DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
