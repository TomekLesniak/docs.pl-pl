---
title: 'Nieprzerwana zmiana: HTTP: wystąpienia HttpClient utworzone przez kody stanu liczby całkowitej dziennika IHttpClientFactory'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej HTTP: wystąpienia HttpClient utworzone przez kody stanu liczby całkowitej dziennika IHttpClientFactory'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 964c0a65a07816acea8016d42a66a6bf84aba7c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761352"
---
# <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a>HTTP: wystąpienia HttpClient utworzone przez kody stanu liczby całkowitej dziennika IHttpClientFactory

<xref:System.Net.Http.HttpClient> wystąpienia utworzone przez <xref:System.Net.Http.IHttpClientFactory> Rejestrowanie kodów stanu HTTP jako liczby całkowite zamiast nazw kodów stanu.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 1

## <a name="old-behavior"></a>Stare zachowanie

Funkcja rejestrowania używa tekstowych opisów kodów stanu HTTP. Należy wziąć pod uwagę następujące komunikaty dziennika:

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

## <a name="new-behavior"></a>Nowe zachowanie

Funkcja rejestrowania używa wartości całkowitych kodów stanu HTTP. Należy wziąć pod uwagę następujące komunikaty dziennika:

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

## <a name="reason-for-change"></a>Przyczyna zmiany

Oryginalne zachowanie tego rejestrowania jest niespójne z innymi częściami ASP.NET Core, które mają zawsze używane wartości całkowite. Niespójność sprawia, że dzienniki są trudne do wykonywania zapytań za pośrednictwem systemów rejestrowania strukturalnego, takich jak [Elasticsearch](https://www.elastic.co/elasticsearch/). Aby uzyskać więcej kontekstu, zobacz [dotnet/Extensions # 1549](https://github.com/dotnet/extensions/issues/1549).

Użycie wartości całkowitych jest bardziej elastyczne niż tekst, ponieważ pozwala na zapytania dotyczące zakresów wartości.

Dodano kolejną wartość dziennika w celu przechwycenia kodu stanu liczby całkowitej. Niestety, spowodowałoby to powstanie innej niespójności z resztą ASP.NET Core. Rejestrowanie HttpClient oraz serwer HTTP/rejestrowanie hostingu używają tej samej `StatusCode` nazwy klucza.

## <a name="recommended-action"></a>Zalecana akcja

Najlepszą opcją jest aktualizowanie zapytań rejestrowania, aby użyć wartości całkowitych kodów stanu. Ta opcja może spowodować pewne trudności z pisaniem zapytań w wielu wersjach ASP.NET Core. Jednak użycie liczb całkowitych w tym celu jest znacznie bardziej elastyczne dla zapytań dzienników.

Jeśli chcesz wymusić zgodność ze starym zachowaniem i użyć tekstowych kodów stanu, Zastąp `IHttpClientFactory` Rejestrowanie własnym:

1. Skopiuj wersje programu .NET Core 3,1 następujących klas do projektu:

    * [LoggingHttpMessageHandlerBuilderFilter](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [LoggingHttpMessageHandler](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [LoggingScopeHttpMessageHandler](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [HttpHeadersLogValue](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. Zmień nazwy klas, aby uniknąć konfliktów z typami publicznymi w pakiecie NuGet [Microsoft. Extensions. http](https://www.nuget.org/packages/Microsoft.Extensions.Http) .

1. Zastąp wbudowaną implementację `LoggingHttpMessageHandlerBuilderFilter` własnymi w `Startup.ConfigureServices` metodzie projektu. Na przykład:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        // Other service registrations go first. Code omitted for brevity.

        // Place the following after all AddHttpClient registrations.
        services.RemoveAll<IHttpMessageHandlerBuilderFilter>();

        services.AddSingleton<IHttpMessageHandlerBuilderFilter,
                              MyLoggingHttpMessageHandlerBuilderFilter>();
    }
    ```

## <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:System.Net.Http.HttpClient`

-->
