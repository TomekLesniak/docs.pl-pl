---
ms.openlocfilehash: 10521759d31c3183232cdb1793d78d139f13ce41
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077569"
---
### <a name="middleware-database-error-page-marked-as-obsolete"></a><span data-ttu-id="89f56-101">Oprogramowanie pośredniczące: Strona błędu bazy danych oznaczona jako przestarzała</span><span class="sxs-lookup"><span data-stu-id="89f56-101">Middleware: Database error page marked as obsolete</span></span>

<span data-ttu-id="89f56-102">[DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) i skojarzone z nią metody rozszerzenia zostały oznaczone jako przestarzałe w ASP.NET Core 5,0.</span><span class="sxs-lookup"><span data-stu-id="89f56-102">The [DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) and its associated extension methods were marked as obsolete in ASP.NET Core 5.0.</span></span> <span data-ttu-id="89f56-103">Oprogramowanie pośredniczące i metody rozszerzające zostaną usunięte w ASP.NET Core 6,0.</span><span class="sxs-lookup"><span data-stu-id="89f56-103">The middleware and extension methods will be removed in ASP.NET Core 6.0.</span></span> <span data-ttu-id="89f56-104">Funkcje te będą udostępniane przez program `DatabaseDeveloperPageExceptionFilter` i jego metody rozszerzające.</span><span class="sxs-lookup"><span data-stu-id="89f56-104">The functionality will instead be provided by `DatabaseDeveloperPageExceptionFilter` and its extension methods.</span></span>

<span data-ttu-id="89f56-105">Aby zapoznać się z omówieniem, zobacz problem z usługą GitHub w usłudze [dotnet/aspnetcore # 24987](https://github.com/dotnet/aspnetcore/issues/24987).</span><span class="sxs-lookup"><span data-stu-id="89f56-105">For discussion, see the GitHub issue at [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="89f56-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="89f56-106">Version introduced</span></span>

<span data-ttu-id="89f56-107">5,0 RC 1</span><span class="sxs-lookup"><span data-stu-id="89f56-107">5.0 RC 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="89f56-108">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="89f56-108">Old behavior</span></span>

<span data-ttu-id="89f56-109">`DatabaseErrorPageMiddleware` i skojarzone metody rozszerzenia nie były przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="89f56-109">`DatabaseErrorPageMiddleware` and its associated extension methods weren't obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="89f56-110">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="89f56-110">New behavior</span></span>

<span data-ttu-id="89f56-111">`DatabaseErrorPageMiddleware` i skojarzone z nią metody rozszerzenia są przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="89f56-111">`DatabaseErrorPageMiddleware` and its associated extension methods are obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="89f56-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="89f56-112">Reason for change</span></span>

<span data-ttu-id="89f56-113">`DatabaseErrorPageMiddleware` został zmigrowany do rozszerzalnego interfejsu API na [stronie wyjątku dewelopera](/aspnet/core/fundamentals/error-handling#developer-exception-page).</span><span class="sxs-lookup"><span data-stu-id="89f56-113">`DatabaseErrorPageMiddleware` was migrated to an extensible API for the [developer exception page](/aspnet/core/fundamentals/error-handling#developer-exception-page).</span></span> <span data-ttu-id="89f56-114">Aby uzyskać więcej informacji na temat rozszerzalnego interfejsu API, zobacz sekcję dotyczącą usługi GitHub wydaj polecenie [dotnet/aspnetcore # 8536](https://github.com/dotnet/aspnetcore/issues/8536).</span><span class="sxs-lookup"><span data-stu-id="89f56-114">For more information on the extensible API, see GitHub issue [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="89f56-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="89f56-115">Recommended action</span></span>

<span data-ttu-id="89f56-116">Wykonaj poniższe czynności:</span><span class="sxs-lookup"><span data-stu-id="89f56-116">Complete the following steps:</span></span>

1. <span data-ttu-id="89f56-117">Przestań używać `DatabaseErrorPageMiddleware` w projekcie.</span><span class="sxs-lookup"><span data-stu-id="89f56-117">Stop using `DatabaseErrorPageMiddleware` in your project.</span></span> <span data-ttu-id="89f56-118">Na przykład Usuń `UseDatabaseErrorPage` wywołanie metody z `Startup.Configure` :</span><span class="sxs-lookup"><span data-stu-id="89f56-118">For example, remove the `UseDatabaseErrorPage` method call from `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. <span data-ttu-id="89f56-119">Dodaj stronę wyjątku dewelopera do projektu.</span><span class="sxs-lookup"><span data-stu-id="89f56-119">Add the developer exception page to your project.</span></span> <span data-ttu-id="89f56-120">Na przykład Wywołaj <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> metodę w `Startup.Configure` :</span><span class="sxs-lookup"><span data-stu-id="89f56-120">For example, call the <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> method in `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. <span data-ttu-id="89f56-121">Dodaj pakiet NuGet [Microsoft. AspNetCore. Diagnostics. EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) do pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="89f56-121">Add the [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) NuGet package to the project file.</span></span>

1. <span data-ttu-id="89f56-122">Dodaj filtr wyjątku strony dewelopera bazy danych do kolekcji usług.</span><span class="sxs-lookup"><span data-stu-id="89f56-122">Add the database developer page exception filter to the services collection.</span></span> <span data-ttu-id="89f56-123">Na przykład Wywołaj `AddDatabaseDeveloperPageExceptionFilter` metodę w `Startup.ConfigureServices` :</span><span class="sxs-lookup"><span data-stu-id="89f56-123">For example, call the `AddDatabaseDeveloperPageExceptionFilter` method in `Startup.ConfigureServices`:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

#### <a name="category"></a><span data-ttu-id="89f56-124">Kategoria</span><span class="sxs-lookup"><span data-stu-id="89f56-124">Category</span></span>

<span data-ttu-id="89f56-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="89f56-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="89f56-126">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="89f56-126">Affected APIs</span></span>

- [<span data-ttu-id="89f56-127">Microsoft. AspNetCore. Builder. DatabaseErrorPageExtensions. UseDatabaseErrorPage</span><span class="sxs-lookup"><span data-stu-id="89f56-127">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span></span>](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [<span data-ttu-id="89f56-128">Microsoft. AspNetCore. Diagnostics. EntityFrameworkCore. DatabaseErrorPageMiddleware</span><span class="sxs-lookup"><span data-stu-id="89f56-128">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span></span>](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!-- 

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
