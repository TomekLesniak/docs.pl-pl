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
# <a name="kestrel-default-supported-tls-protocol-versions-changed"></a>Kestrel: zmieniono domyślne wersje protokołu TLS

Kestrel teraz używa domyślnych wersji protokołu TLS systemu zamiast ograniczenia połączeń z protokołami TLS 1,1 i TLS 1,2, takimi jak wcześniej.

Ta zmiana umożliwia:

* Protokołu TLS 1,3, który ma być używany domyślnie w środowiskach, które je obsługują.
* Protokół TLS 1,0 do użycia w niektórych środowiskach (na przykład system Windows Server 2016 domyślnie), co zazwyczaj [nie jest pożądane](/security/engineering/solving-tls1-problem).

Aby zapoznać się z omówieniem, zobacz temat Issue [dotnet/aspnetcore # 22563](https://github.com/dotnet/aspnetcore/issues/22563).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 6

## <a name="old-behavior"></a>Stare zachowanie

Kestrel wymaga, aby połączenia domyślnie używały protokołu TLS 1,1 lub TLS 1,2.

## <a name="new-behavior"></a>Nowe zachowanie

Kestrel umożliwia systemowi operacyjnemu wybranie najlepszego protokołu do użycia i zablokowanie niezabezpieczonych protokołów. <xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> teraz wartość domyślna to `SslProtocols.None` zamiast `SslProtocols.Tls12 | SslProtocols.Tls11` .

## <a name="reason-for-change"></a>Przyczyna zmiany

Wprowadzono zmiany w celu obsługi protokołu TLS 1,3 i przyszłych wersji protokołu TLS domyślnie, gdy staną się dostępne.

## <a name="recommended-action"></a>Zalecana akcja

Jeśli aplikacja nie ma określonego powodu, należy użyć nowych wartości domyślnych. Sprawdź, czy system jest skonfigurowany tak, aby zezwalał tylko na bezpieczne protokoły.

Aby wyłączyć starsze protokoły, wykonaj jedną z następujących czynności:

* Wyłącz starsze protokoły, takie jak TLS 1,0, system-Wide z [instrukcjami systemu Windows](../../../../framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry). Jest ona obecnie włączona domyślnie we wszystkich wersjach systemu Windows.
* Ręcznie wybierz protokoły, które mają być obsługiwane w kodzie w następujący sposób:

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

Niestety, nie istnieje interfejs API do wykluczenia określonych protokołów.

## <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
