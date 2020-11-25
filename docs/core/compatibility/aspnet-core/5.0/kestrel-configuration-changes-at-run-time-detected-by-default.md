---
title: 'Zmiana podziału: Kestrel: zmiany konfiguracji w czasie wykonywania zostały wykryte domyślnie'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Kestrel: zmiany konfiguracji w czasie wykonywania zostały domyślnie wykryte'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 2e879f020dd108baa14fa8ff67dee7b948209faf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761347"
---
# <a name="kestrel-configuration-changes-at-run-time-detected-by-default"></a><span data-ttu-id="d06aa-103">Kestrel: domyślnie wykryto zmiany konfiguracji w czasie wykonywania</span><span class="sxs-lookup"><span data-stu-id="d06aa-103">Kestrel: Configuration changes at run time detected by default</span></span>

<span data-ttu-id="d06aa-104">Kestrel teraz reaguje na zmiany wprowadzone w `Kestrel` sekcji `IConfiguration` wystąpienia projektu (na przykład *appsettings.json*) w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="d06aa-104">Kestrel now reacts to changes made to the `Kestrel` section of the project's `IConfiguration` instance (for example, *appsettings.json*) at run time.</span></span> <span data-ttu-id="d06aa-105">Aby dowiedzieć się więcej o konfigurowaniu Kestrel przy użyciu *appsettings.json*, zobacz *appsettings.jsna* przykład w [konfiguracji punktu końcowego](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span><span class="sxs-lookup"><span data-stu-id="d06aa-105">To learn more about how to configure Kestrel using *appsettings.json*, see the *appsettings.json* example in [Endpoint configuration](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span></span>

<span data-ttu-id="d06aa-106">Kestrel będzie powiązać, usunąć powiązania i ponownie powiązać punkty końcowe w celu reagowania na te zmiany konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="d06aa-106">Kestrel will bind, unbind, and rebind endpoints as necessary to react to these configuration changes.</span></span>

<span data-ttu-id="d06aa-107">Aby zapoznać się z omówieniem, zobacz temat Issue [dotnet/aspnetcore # 22807](https://github.com/dotnet/aspnetcore/issues/22807).</span><span class="sxs-lookup"><span data-stu-id="d06aa-107">For discussion, see issue [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d06aa-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="d06aa-108">Version introduced</span></span>

<span data-ttu-id="d06aa-109">5,0 wersja zapoznawcza 7</span><span class="sxs-lookup"><span data-stu-id="d06aa-109">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="d06aa-110">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="d06aa-110">Old behavior</span></span>

<span data-ttu-id="d06aa-111">Przed ASP.NET Core 5,0 wersji zapoznawczej 6 Kestrel nie obsługiwał zmiany konfiguracji w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="d06aa-111">Before ASP.NET Core 5.0 Preview 6, Kestrel didn't support changing configuration at run time.</span></span>

<span data-ttu-id="d06aa-112">W ASP.NET Core 5,0 w wersji zapoznawczej 6 można przystąpić do domyślnego zachowania, które odbędzie się do zmian konfiguracji w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="d06aa-112">In ASP.NET Core 5.0 Preview 6, you could opt into the now-default behavior of reacting to configuration changes at run time.</span></span> <span data-ttu-id="d06aa-113">Ręczne wyKestrelnie wymaganej konfiguracji powiązanego powiązania:</span><span class="sxs-lookup"><span data-stu-id="d06aa-113">Opting in required binding Kestrel's configuration manually:</span></span>

```csharp
using Microsoft.AspNetCore.Hosting;
using Microsoft.Extensions.Hosting;

public class Program
{
    public static void Main(string[] args) =>
        CreateHostBuilder(args).Build().Run();

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                {
                    kestrelOptions.Configure(
                        builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: true);
                });

                webBuilder.UseStartup<Startup>();
            });
}
```

## <a name="new-behavior"></a><span data-ttu-id="d06aa-114">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="d06aa-114">New behavior</span></span>

<span data-ttu-id="d06aa-115">Kestrel domyślnie reaguje na zmiany konfiguracji w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="d06aa-115">Kestrel reacts to configuration changes at run time by default.</span></span> <span data-ttu-id="d06aa-116">W celu obsługi tej zmiany <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> program `KestrelServerOptions.Configure(IConfiguration, bool)` Domyślnie wywołuje program `reloadOnChange: true` .</span><span class="sxs-lookup"><span data-stu-id="d06aa-116">To support that change, <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> calls `KestrelServerOptions.Configure(IConfiguration, bool)` with `reloadOnChange: true` by default.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d06aa-117">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="d06aa-117">Reason for change</span></span>

<span data-ttu-id="d06aa-118">Wprowadzono zmiany w celu obsługi ponownej konfiguracji punktu końcowego w czasie wykonywania bez całkowitego ponownego uruchomienia serwera.</span><span class="sxs-lookup"><span data-stu-id="d06aa-118">The change was made to support endpoint reconfiguration at run time without completely restarting the server.</span></span> <span data-ttu-id="d06aa-119">W przeciwieństwie do pełnego ponownego uruchomienia serwera, niezmienione punkty końcowe nie są nawet tymczasowo niepowiązane.</span><span class="sxs-lookup"><span data-stu-id="d06aa-119">Unlike with a full server restart, unchanged endpoints aren't unbound even temporarily.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d06aa-120">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="d06aa-120">Recommended action</span></span>

* <span data-ttu-id="d06aa-121">W przypadku większości scenariuszy, w których domyślna sekcja konfiguracji Kestrel nie zmienia się w czasie wykonywania, ta zmiana nie ma wpływu i nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="d06aa-121">For most scenarios in which Kestrel's default configuration section doesn't change at run time, this change has no impact and no action is needed.</span></span>
* <span data-ttu-id="d06aa-122">W przypadku scenariuszy, w których domyślna sekcja konfiguracji Kestrel zmienia się w czasie wykonywania, a Kestrel powinna reagować na nie, jest to teraz zachowanie domyślne.</span><span class="sxs-lookup"><span data-stu-id="d06aa-122">For scenarios in which Kestrel's default configuration section does change at run time and Kestrel should react to it, this is now the default behavior.</span></span>
* <span data-ttu-id="d06aa-123">W przypadku scenariuszy, w których domyślna sekcja konfiguracji Kestrel jest zmieniana w czasie wykonywania, a Kestrel nie powinna reagować na nią, można zrezygnować z następujących metod:</span><span class="sxs-lookup"><span data-stu-id="d06aa-123">For scenarios in which Kestrel's default configuration section changes at run time and Kestrel shouldn't react to it, you can opt out as follows:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Hosting;

    public class Program
    {
        public static void Main(string[] args) =>
            CreateHostBuilder(args).Build().Run();

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                    {
                        kestrelOptions.Configure(
                            builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: false);
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

<span data-ttu-id="d06aa-124">**Uwagi:**</span><span class="sxs-lookup"><span data-stu-id="d06aa-124">**Notes:**</span></span>

<span data-ttu-id="d06aa-125">Ta zmiana nie modyfikuje zachowania `KestrelServerOptions.Configure(IConfiguration)` przeciążenia, które nadal jest `reloadOnChange: false` zachowaniem domyślnym.</span><span class="sxs-lookup"><span data-stu-id="d06aa-125">This change doesn't modify the behavior of the `KestrelServerOptions.Configure(IConfiguration)` overload, which still defaults to the `reloadOnChange: false` behavior.</span></span>

<span data-ttu-id="d06aa-126">Ważne jest również, aby upewnić się, że źródło konfiguracji obsługuje ponowne ładowanie.</span><span class="sxs-lookup"><span data-stu-id="d06aa-126">It's also important to make sure the configuration source supports reloading.</span></span> <span data-ttu-id="d06aa-127">W przypadku źródeł JSON ponowne ładowanie jest konfigurowane przez wywołanie metody `AddJsonFile(path, reloadOnChange: true)` .</span><span class="sxs-lookup"><span data-stu-id="d06aa-127">For JSON sources, reloading is configured by calling `AddJsonFile(path, reloadOnChange: true)`.</span></span> <span data-ttu-id="d06aa-128">Ponowne ładowanie jest już skonfigurowane domyślnie dla *appsettings.jsw* i *appSettings. { Environment}. JSON*.</span><span class="sxs-lookup"><span data-stu-id="d06aa-128">Reloading is already configured by default for *appsettings.json* and *appsettings.{Environment}.json*.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d06aa-129">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d06aa-129">Affected APIs</span></span>

<xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults`

-->
