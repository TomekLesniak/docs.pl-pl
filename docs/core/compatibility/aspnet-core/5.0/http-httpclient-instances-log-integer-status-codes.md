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
# <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a><span data-ttu-id="b7d04-103">HTTP: wystąpienia HttpClient utworzone przez kody stanu liczby całkowitej dziennika IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="b7d04-103">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>

<span data-ttu-id="b7d04-104"><xref:System.Net.Http.HttpClient> wystąpienia utworzone przez <xref:System.Net.Http.IHttpClientFactory> Rejestrowanie kodów stanu HTTP jako liczby całkowite zamiast nazw kodów stanu.</span><span class="sxs-lookup"><span data-stu-id="b7d04-104"><xref:System.Net.Http.HttpClient> instances created by <xref:System.Net.Http.IHttpClientFactory> log HTTP status codes as integers instead of with status code names.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b7d04-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="b7d04-105">Version introduced</span></span>

<span data-ttu-id="b7d04-106">5,0 wersja zapoznawcza 1</span><span class="sxs-lookup"><span data-stu-id="b7d04-106">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="b7d04-107">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="b7d04-107">Old behavior</span></span>

<span data-ttu-id="b7d04-108">Funkcja rejestrowania używa tekstowych opisów kodów stanu HTTP.</span><span class="sxs-lookup"><span data-stu-id="b7d04-108">Logging uses the textual descriptions of HTTP status codes.</span></span> <span data-ttu-id="b7d04-109">Należy wziąć pod uwagę następujące komunikaty dziennika:</span><span class="sxs-lookup"><span data-stu-id="b7d04-109">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

## <a name="new-behavior"></a><span data-ttu-id="b7d04-110">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="b7d04-110">New behavior</span></span>

<span data-ttu-id="b7d04-111">Funkcja rejestrowania używa wartości całkowitych kodów stanu HTTP.</span><span class="sxs-lookup"><span data-stu-id="b7d04-111">Logging uses the integer values of HTTP status codes.</span></span> <span data-ttu-id="b7d04-112">Należy wziąć pod uwagę następujące komunikaty dziennika:</span><span class="sxs-lookup"><span data-stu-id="b7d04-112">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

## <a name="reason-for-change"></a><span data-ttu-id="b7d04-113">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="b7d04-113">Reason for change</span></span>

<span data-ttu-id="b7d04-114">Oryginalne zachowanie tego rejestrowania jest niespójne z innymi częściami ASP.NET Core, które mają zawsze używane wartości całkowite.</span><span class="sxs-lookup"><span data-stu-id="b7d04-114">The original behavior of this logging is inconsistent with other parts of ASP.NET Core that have always used integer values.</span></span> <span data-ttu-id="b7d04-115">Niespójność sprawia, że dzienniki są trudne do wykonywania zapytań za pośrednictwem systemów rejestrowania strukturalnego, takich jak [Elasticsearch](https://www.elastic.co/elasticsearch/).</span><span class="sxs-lookup"><span data-stu-id="b7d04-115">The inconsistency makes logs difficult to query via structured logging systems such as [Elasticsearch](https://www.elastic.co/elasticsearch/).</span></span> <span data-ttu-id="b7d04-116">Aby uzyskać więcej kontekstu, zobacz [dotnet/Extensions # 1549](https://github.com/dotnet/extensions/issues/1549).</span><span class="sxs-lookup"><span data-stu-id="b7d04-116">For more context, see [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span></span>

<span data-ttu-id="b7d04-117">Użycie wartości całkowitych jest bardziej elastyczne niż tekst, ponieważ pozwala na zapytania dotyczące zakresów wartości.</span><span class="sxs-lookup"><span data-stu-id="b7d04-117">Using integer values is more flexible than text because it allows queries on ranges of values.</span></span>

<span data-ttu-id="b7d04-118">Dodano kolejną wartość dziennika w celu przechwycenia kodu stanu liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="b7d04-118">Adding another log value to capture the integer status code was considered.</span></span> <span data-ttu-id="b7d04-119">Niestety, spowodowałoby to powstanie innej niespójności z resztą ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b7d04-119">Unfortunately, doing so would introduce another inconsistency with the rest of ASP.NET Core.</span></span> <span data-ttu-id="b7d04-120">Rejestrowanie HttpClient oraz serwer HTTP/rejestrowanie hostingu używają tej samej `StatusCode` nazwy klucza.</span><span class="sxs-lookup"><span data-stu-id="b7d04-120">HttpClient logging and HTTP server/hosting logging use the same `StatusCode` key name already.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b7d04-121">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="b7d04-121">Recommended action</span></span>

<span data-ttu-id="b7d04-122">Najlepszą opcją jest aktualizowanie zapytań rejestrowania, aby użyć wartości całkowitych kodów stanu.</span><span class="sxs-lookup"><span data-stu-id="b7d04-122">The best option is to update logging queries to use the integer values of status codes.</span></span> <span data-ttu-id="b7d04-123">Ta opcja może spowodować pewne trudności z pisaniem zapytań w wielu wersjach ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b7d04-123">This option may cause some difficulty writing queries across multiple ASP.NET Core versions.</span></span> <span data-ttu-id="b7d04-124">Jednak użycie liczb całkowitych w tym celu jest znacznie bardziej elastyczne dla zapytań dzienników.</span><span class="sxs-lookup"><span data-stu-id="b7d04-124">However, using integers for this purpose is much more flexible for querying logs.</span></span>

<span data-ttu-id="b7d04-125">Jeśli chcesz wymusić zgodność ze starym zachowaniem i użyć tekstowych kodów stanu, Zastąp `IHttpClientFactory` Rejestrowanie własnym:</span><span class="sxs-lookup"><span data-stu-id="b7d04-125">If you need to force compatibility with the old behavior and use textual status codes, replace the `IHttpClientFactory` logging with your own:</span></span>

1. <span data-ttu-id="b7d04-126">Skopiuj wersje programu .NET Core 3,1 następujących klas do projektu:</span><span class="sxs-lookup"><span data-stu-id="b7d04-126">Copy the .NET Core 3.1 versions of the following classes into your project:</span></span>

    * [<span data-ttu-id="b7d04-127">LoggingHttpMessageHandlerBuilderFilter</span><span class="sxs-lookup"><span data-stu-id="b7d04-127">LoggingHttpMessageHandlerBuilderFilter</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [<span data-ttu-id="b7d04-128">LoggingHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="b7d04-128">LoggingHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [<span data-ttu-id="b7d04-129">LoggingScopeHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="b7d04-129">LoggingScopeHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [<span data-ttu-id="b7d04-130">HttpHeadersLogValue</span><span class="sxs-lookup"><span data-stu-id="b7d04-130">HttpHeadersLogValue</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. <span data-ttu-id="b7d04-131">Zmień nazwy klas, aby uniknąć konfliktów z typami publicznymi w pakiecie NuGet [Microsoft. Extensions. http](https://www.nuget.org/packages/Microsoft.Extensions.Http) .</span><span class="sxs-lookup"><span data-stu-id="b7d04-131">Rename the classes to avoid conflicts with public types in the [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) NuGet package.</span></span>

1. <span data-ttu-id="b7d04-132">Zastąp wbudowaną implementację `LoggingHttpMessageHandlerBuilderFilter` własnymi w `Startup.ConfigureServices` metodzie projektu.</span><span class="sxs-lookup"><span data-stu-id="b7d04-132">Replace the built-in implementation of `LoggingHttpMessageHandlerBuilderFilter` with your own in the project's `Startup.ConfigureServices` method.</span></span> <span data-ttu-id="b7d04-133">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="b7d04-133">For example:</span></span>

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

## <a name="affected-apis"></a><span data-ttu-id="b7d04-134">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b7d04-134">Affected APIs</span></span>

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:System.Net.Http.HttpClient`

-->
