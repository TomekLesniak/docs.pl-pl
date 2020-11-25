---
title: 'Zmiana podziału: Kestrel: zmieniono domyślne wersje protokołu TLS'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Kestrel: zmieniono domyślne wersje protokołu TLS'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: d7018be7cc778560b7b9c65472d42d7e0fbf623d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761340"
---
# <a name="kestrel-default-supported-tls-protocol-versions-changed"></a><span data-ttu-id="8549a-103">Kestrel: zmieniono domyślne wersje protokołu TLS</span><span class="sxs-lookup"><span data-stu-id="8549a-103">Kestrel: Default supported TLS protocol versions changed</span></span>

<span data-ttu-id="8549a-104">Kestrel teraz używa domyślnych wersji protokołu TLS systemu zamiast ograniczenia połączeń z protokołami TLS 1,1 i TLS 1,2, takimi jak wcześniej.</span><span class="sxs-lookup"><span data-stu-id="8549a-104">Kestrel now uses the system default TLS protocol versions rather than restricting connections to the TLS 1.1 and TLS 1.2 protocols like it did previously.</span></span>

<span data-ttu-id="8549a-105">Ta zmiana umożliwia:</span><span class="sxs-lookup"><span data-stu-id="8549a-105">This change allows:</span></span>

* <span data-ttu-id="8549a-106">Protokołu TLS 1,3, który ma być używany domyślnie w środowiskach, które je obsługują.</span><span class="sxs-lookup"><span data-stu-id="8549a-106">TLS 1.3 to be used by default in environments that support it.</span></span>
* <span data-ttu-id="8549a-107">Protokół TLS 1,0 do użycia w niektórych środowiskach (na przykład system Windows Server 2016 domyślnie), co zazwyczaj [nie jest pożądane](/security/engineering/solving-tls1-problem).</span><span class="sxs-lookup"><span data-stu-id="8549a-107">TLS 1.0 to be used in some environments (such as Windows Server 2016 by default), which is usually [not desirable](/security/engineering/solving-tls1-problem).</span></span>

<span data-ttu-id="8549a-108">Aby zapoznać się z omówieniem, zobacz temat Issue [dotnet/aspnetcore # 22563](https://github.com/dotnet/aspnetcore/issues/22563).</span><span class="sxs-lookup"><span data-stu-id="8549a-108">For discussion, see issue [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="8549a-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="8549a-109">Version introduced</span></span>

<span data-ttu-id="8549a-110">5,0 wersja zapoznawcza 6</span><span class="sxs-lookup"><span data-stu-id="8549a-110">5.0 Preview 6</span></span>

## <a name="old-behavior"></a><span data-ttu-id="8549a-111">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="8549a-111">Old behavior</span></span>

<span data-ttu-id="8549a-112">Kestrel wymaga, aby połączenia domyślnie używały protokołu TLS 1,1 lub TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="8549a-112">Kestrel required that connections use TLS 1.1 or TLS 1.2 by default.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="8549a-113">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="8549a-113">New behavior</span></span>

<span data-ttu-id="8549a-114">Kestrel umożliwia systemowi operacyjnemu wybranie najlepszego protokołu do użycia i zablokowanie niezabezpieczonych protokołów.</span><span class="sxs-lookup"><span data-stu-id="8549a-114">Kestrel allows the operating system to choose the best protocol to use and to block insecure protocols.</span></span> <span data-ttu-id="8549a-115"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> teraz wartość domyślna to `SslProtocols.None` zamiast `SslProtocols.Tls12 | SslProtocols.Tls11` .</span><span class="sxs-lookup"><span data-stu-id="8549a-115"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> now defaults to `SslProtocols.None` instead of `SslProtocols.Tls12 | SslProtocols.Tls11`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="8549a-116">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="8549a-116">Reason for change</span></span>

<span data-ttu-id="8549a-117">Wprowadzono zmiany w celu obsługi protokołu TLS 1,3 i przyszłych wersji protokołu TLS domyślnie, gdy staną się dostępne.</span><span class="sxs-lookup"><span data-stu-id="8549a-117">The change was made to support TLS 1.3 and future TLS versions by default as they become available.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="8549a-118">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="8549a-118">Recommended action</span></span>

<span data-ttu-id="8549a-119">Jeśli aplikacja nie ma określonego powodu, należy użyć nowych wartości domyślnych.</span><span class="sxs-lookup"><span data-stu-id="8549a-119">Unless your app has a specific reason not to, you should use the new defaults.</span></span> <span data-ttu-id="8549a-120">Sprawdź, czy system jest skonfigurowany tak, aby zezwalał tylko na bezpieczne protokoły.</span><span class="sxs-lookup"><span data-stu-id="8549a-120">Verify your system is configured to allow only secure protocols.</span></span>

<span data-ttu-id="8549a-121">Aby wyłączyć starsze protokoły, wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="8549a-121">To disable older protocols, take one of the following actions:</span></span>

* <span data-ttu-id="8549a-122">Wyłącz starsze protokoły, takie jak TLS 1,0, system-Wide z [instrukcjami systemu Windows](../../../../framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry).</span><span class="sxs-lookup"><span data-stu-id="8549a-122">Disable older protocols, such as TLS 1.0, system-wide with the [Windows instructions](../../../../framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry).</span></span> <span data-ttu-id="8549a-123">Jest ona obecnie włączona domyślnie we wszystkich wersjach systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="8549a-123">It's currently enabled by default on all Windows versions.</span></span>
* <span data-ttu-id="8549a-124">Ręcznie wybierz protokoły, które mają być obsługiwane w kodzie w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8549a-124">Manually select which protocols you want to support in code as follows:</span></span>

    ```csharp
    using System.Security.Authentication;
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
                    webBuilder.UseKestrel(kestrelOptions =>
                    {
                        kestrelOptions.ConfigureHttpsDefaults(httpsOptions =>
                        {
                            httpsOptions.SslProtocols = SslProtocols.Tls12 | SslProtocols.Tls13;
                        });
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

<span data-ttu-id="8549a-125">Niestety, nie istnieje interfejs API do wykluczenia określonych protokołów.</span><span class="sxs-lookup"><span data-stu-id="8549a-125">Unfortunately, there's no API to exclude specific protocols.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="8549a-126">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8549a-126">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
