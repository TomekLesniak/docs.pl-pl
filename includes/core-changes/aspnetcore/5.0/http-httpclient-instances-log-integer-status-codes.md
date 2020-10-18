---
ms.openlocfilehash: f1556fac0e8aa79c87cd5e74c1b603582ff5db1b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160551"
---
### <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a><span data-ttu-id="dc375-101">HTTP: wystąpienia HttpClient utworzone przez kody stanu liczby całkowitej dziennika IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="dc375-101">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>

<span data-ttu-id="dc375-102"><xref:System.Net.Http.HttpClient> wystąpienia utworzone przez <xref:System.Net.Http.IHttpClientFactory> Rejestrowanie kodów stanu HTTP jako liczby całkowite zamiast nazw kodów stanu.</span><span class="sxs-lookup"><span data-stu-id="dc375-102"><xref:System.Net.Http.HttpClient> instances created by <xref:System.Net.Http.IHttpClientFactory> log HTTP status codes as integers instead of with status code names.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="dc375-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="dc375-103">Version introduced</span></span>

<span data-ttu-id="dc375-104">5,0 wersja zapoznawcza 1</span><span class="sxs-lookup"><span data-stu-id="dc375-104">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="dc375-105">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="dc375-105">Old behavior</span></span>

<span data-ttu-id="dc375-106">Funkcja rejestrowania używa tekstowych opisów kodów stanu HTTP.</span><span class="sxs-lookup"><span data-stu-id="dc375-106">Logging uses the textual descriptions of HTTP status codes.</span></span> <span data-ttu-id="dc375-107">Należy wziąć pod uwagę następujące komunikaty dziennika:</span><span class="sxs-lookup"><span data-stu-id="dc375-107">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

#### <a name="new-behavior"></a><span data-ttu-id="dc375-108">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="dc375-108">New behavior</span></span>

<span data-ttu-id="dc375-109">Funkcja rejestrowania używa wartości całkowitych kodów stanu HTTP.</span><span class="sxs-lookup"><span data-stu-id="dc375-109">Logging uses the integer values of HTTP status codes.</span></span> <span data-ttu-id="dc375-110">Należy wziąć pod uwagę następujące komunikaty dziennika:</span><span class="sxs-lookup"><span data-stu-id="dc375-110">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

#### <a name="reason-for-change"></a><span data-ttu-id="dc375-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="dc375-111">Reason for change</span></span>

<span data-ttu-id="dc375-112">Oryginalne zachowanie tego rejestrowania jest niespójne z innymi częściami ASP.NET Core, które mają zawsze używane wartości całkowite.</span><span class="sxs-lookup"><span data-stu-id="dc375-112">The original behavior of this logging is inconsistent with other parts of ASP.NET Core that have always used integer values.</span></span> <span data-ttu-id="dc375-113">Niespójność sprawia, że dzienniki są trudne do wykonywania zapytań za pośrednictwem systemów rejestrowania strukturalnego, takich jak [Elasticsearch](https://www.elastic.co/elasticsearch/).</span><span class="sxs-lookup"><span data-stu-id="dc375-113">The inconsistency makes logs difficult to query via structured logging systems such as [Elasticsearch](https://www.elastic.co/elasticsearch/).</span></span> <span data-ttu-id="dc375-114">Aby uzyskać więcej kontekstu, zobacz [dotnet/Extensions # 1549](https://github.com/dotnet/extensions/issues/1549).</span><span class="sxs-lookup"><span data-stu-id="dc375-114">For more context, see [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span></span>

<span data-ttu-id="dc375-115">Użycie wartości całkowitych jest bardziej elastyczne niż tekst, ponieważ pozwala na zapytania dotyczące zakresów wartości.</span><span class="sxs-lookup"><span data-stu-id="dc375-115">Using integer values is more flexible than text because it allows queries on ranges of values.</span></span>

<span data-ttu-id="dc375-116">Dodano kolejną wartość dziennika w celu przechwycenia kodu stanu liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="dc375-116">Adding another log value to capture the integer status code was considered.</span></span> <span data-ttu-id="dc375-117">Niestety, spowodowałoby to powstanie innej niespójności z resztą ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc375-117">Unfortunately, doing so would introduce another inconsistency with the rest of ASP.NET Core.</span></span> <span data-ttu-id="dc375-118">Rejestrowanie HttpClient oraz serwer HTTP/rejestrowanie hostingu używają tej samej `StatusCode` nazwy klucza.</span><span class="sxs-lookup"><span data-stu-id="dc375-118">HttpClient logging and HTTP server/hosting logging use the same `StatusCode` key name already.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dc375-119">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="dc375-119">Recommended action</span></span>

<span data-ttu-id="dc375-120">Najlepszą opcją jest aktualizowanie zapytań rejestrowania, aby użyć wartości całkowitych kodów stanu.</span><span class="sxs-lookup"><span data-stu-id="dc375-120">The best option is to update logging queries to use the integer values of status codes.</span></span> <span data-ttu-id="dc375-121">Ta opcja może spowodować pewne trudności z pisaniem zapytań w wielu wersjach ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc375-121">This option may cause some difficulty writing queries across multiple ASP.NET Core versions.</span></span> <span data-ttu-id="dc375-122">Jednak użycie liczb całkowitych w tym celu jest znacznie bardziej elastyczne dla zapytań dzienników.</span><span class="sxs-lookup"><span data-stu-id="dc375-122">However, using integers for this purpose is much more flexible for querying logs.</span></span>

<span data-ttu-id="dc375-123">Jeśli chcesz wymusić zgodność ze starym zachowaniem i użyć tekstowych kodów stanu, Zastąp `IHttpClientFactory` Rejestrowanie własnym:</span><span class="sxs-lookup"><span data-stu-id="dc375-123">If you need to force compatibility with the old behavior and use textual status codes, replace the `IHttpClientFactory` logging with your own:</span></span>

1. <span data-ttu-id="dc375-124">Skopiuj wersje programu .NET Core 3,1 następujących klas do projektu:</span><span class="sxs-lookup"><span data-stu-id="dc375-124">Copy the .NET Core 3.1 versions of the following classes into your project:</span></span>

    * [<span data-ttu-id="dc375-125">LoggingHttpMessageHandlerBuilderFilter</span><span class="sxs-lookup"><span data-stu-id="dc375-125">LoggingHttpMessageHandlerBuilderFilter</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [<span data-ttu-id="dc375-126">LoggingHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="dc375-126">LoggingHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [<span data-ttu-id="dc375-127">LoggingScopeHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="dc375-127">LoggingScopeHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [<span data-ttu-id="dc375-128">HttpHeadersLogValue</span><span class="sxs-lookup"><span data-stu-id="dc375-128">HttpHeadersLogValue</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. <span data-ttu-id="dc375-129">Zmień nazwy klas, aby uniknąć konfliktów z typami publicznymi w pakiecie NuGet [Microsoft. Extensions. http](https://www.nuget.org/packages/Microsoft.Extensions.Http) .</span><span class="sxs-lookup"><span data-stu-id="dc375-129">Rename the classes to avoid conflicts with public types in the [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) NuGet package.</span></span>

1. <span data-ttu-id="dc375-130">Zastąp wbudowaną implementację `LoggingHttpMessageHandlerBuilderFilter` własnymi w `Startup.ConfigureServices` metodzie projektu.</span><span class="sxs-lookup"><span data-stu-id="dc375-130">Replace the built-in implementation of `LoggingHttpMessageHandlerBuilderFilter` with your own in the project's `Startup.ConfigureServices` method.</span></span> <span data-ttu-id="dc375-131">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="dc375-131">For example:</span></span>

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

#### <a name="category"></a><span data-ttu-id="dc375-132">Kategoria</span><span class="sxs-lookup"><span data-stu-id="dc375-132">Category</span></span>

<span data-ttu-id="dc375-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dc375-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dc375-134">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="dc375-134">Affected APIs</span></span>

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:System.Net.Http.HttpClient`

-->
