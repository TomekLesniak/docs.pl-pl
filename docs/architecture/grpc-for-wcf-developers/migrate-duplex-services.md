---
title: Migrowanie usług programu WCF Duplex do gRPC-gRPC dla deweloperów programu WCF
description: Dowiedz się, jak migrować różne formy usługi programu WCF Duplex do usługi gRPC Streaming Services.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 06ac784a31df43fd270f7ef0475bcdc282efad8f
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184338"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a><span data-ttu-id="d50d2-103">Migrowanie usług programu WCF Duplex do gRPC</span><span class="sxs-lookup"><span data-stu-id="d50d2-103">Migrate WCF duplex services to gRPC</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="d50d2-104">Teraz, gdy podstawowe koncepcje są stosowane, ta sekcja będzie wyglądać na bardziej skomplikowane usługi *przesyłania strumieniowego* gRPC.</span><span class="sxs-lookup"><span data-stu-id="d50d2-104">Now that the basic concepts are in place, this section will look at the more complicated *streaming* gRPC services.</span></span>

<span data-ttu-id="d50d2-105">Istnieje wiele sposobów używania usług dupleksowych w Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d50d2-105">There are multiple ways to use duplex services in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="d50d2-106">Niektóre usługi są inicjowane przez klienta, a następnie przesyłają strumieniowo dane z serwera.</span><span class="sxs-lookup"><span data-stu-id="d50d2-106">Some services are initiated by the client and then they stream data from the server.</span></span> <span data-ttu-id="d50d2-107">Inne usługi o pełnym dupleksie mogą pociągnąć za sobą więcej trwających dwukierunkowej komunikacji, takich jak klasyczny przykład "Kalkulator" z dokumentacji programu WCF.</span><span class="sxs-lookup"><span data-stu-id="d50d2-107">Other full-duplex services might involve more ongoing two-way communication like the classic "Calculator" example from the WCF documentation.</span></span> <span data-ttu-id="d50d2-108">Ten rozdział zajmie się dwoma możliwymi implementacjami "cykl giełdowy" platformy WCF i migruje je do gRPC: jeden przy użyciu protokołu RPC przesyłania strumieniowego serwera, a drugi przy użyciu dwukierunkowego wywołania RPC przesyłania strumieniowego.</span><span class="sxs-lookup"><span data-stu-id="d50d2-108">This chapter will take two possible WCF "Stock Ticker" implementations and migrate them to gRPC: one using a server streaming RPC, and the other one using a bidirectional streaming RPC.</span></span>

## <a name="server-streaming-rpc"></a><span data-ttu-id="d50d2-109">Serwer RPC przesyłania strumieniowego</span><span class="sxs-lookup"><span data-stu-id="d50d2-109">Server streaming RPC</span></span>

<span data-ttu-id="d50d2-110">W [przykładowym rozwiązaniu SIMPLESTOCKTICKER WCF](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker) *SimpleStockPriceTicker*, dostępna jest usługa dupleksowa, w której klient uruchamia połączenie z listą symboli magazynowych, a serwer używa *interfejsu wywołania zwrotnego* do wysyłania aktualizacji staną się dostępne.</span><span class="sxs-lookup"><span data-stu-id="d50d2-110">In the [sample SimpleStockTicker WCF solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *SimpleStockPriceTicker*, there's a duplex service where the client starts the connection with a list of stock symbols, and the server uses the *callback interface* to send updates as they become available.</span></span> <span data-ttu-id="d50d2-111">Klient implementuje ten interfejs, aby odpowiedzieć na wywołania z serwera.</span><span class="sxs-lookup"><span data-stu-id="d50d2-111">The client implements that interface to respond to calls from the server.</span></span>

### <a name="the-wcf-solution"></a><span data-ttu-id="d50d2-112">Rozwiązanie WCF</span><span class="sxs-lookup"><span data-stu-id="d50d2-112">The WCF solution</span></span>

<span data-ttu-id="d50d2-113">Rozwiązanie WCF jest zaimplementowane jako samodzielny serwer NetTCP w aplikacji konsolowej programu .NET Framework 4. x.</span><span class="sxs-lookup"><span data-stu-id="d50d2-113">The WCF solution is implemented as a self-hosted NetTCP server in a .NET Framework 4.x console application.</span></span>

#### <a name="the-servicecontract"></a><span data-ttu-id="d50d2-114">ServiceContract</span><span class="sxs-lookup"><span data-stu-id="d50d2-114">The ServiceContract</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

<span data-ttu-id="d50d2-115">Usługa ma jedną metodę bez zwracanego typu, ponieważ będzie używać interfejsu `ISimpleStockTickerCallback` wywołania zwrotnego do wysyłania danych do klienta w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="d50d2-115">The service has a single method with no return type, because it will be using the callback interface `ISimpleStockTickerCallback` to send data to the client in real time.</span></span>

#### <a name="the-callback-interface"></a><span data-ttu-id="d50d2-116">Interfejs wywołania zwrotnego</span><span class="sxs-lookup"><span data-stu-id="d50d2-116">The callback interface</span></span>

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

<span data-ttu-id="d50d2-117">Implementacje tych interfejsów można znaleźć w rozwiązaniu wraz z niektórymi zewnętrznymi zależnościami w celu zapewnienia danych testowych.</span><span class="sxs-lookup"><span data-stu-id="d50d2-117">The implementations of these interfaces can be found in the solution, along with faked external dependencies to provide test data.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="d50d2-118">gRPC Streaming</span><span class="sxs-lookup"><span data-stu-id="d50d2-118">gRPC streaming</span></span>

<span data-ttu-id="d50d2-119">GRPC sposób obsługi danych w czasie rzeczywistym jest różny.</span><span class="sxs-lookup"><span data-stu-id="d50d2-119">The gRPC way of handling real-time data is different.</span></span> <span data-ttu-id="d50d2-120">Wywołanie z klienta do serwera może utworzyć trwały strumień, który może być monitorowany w przypadku komunikatów przychodzących asynchronicznie.</span><span class="sxs-lookup"><span data-stu-id="d50d2-120">A call from client to server can create a persistent stream, which can be monitored for messages arriving asynchronously.</span></span> <span data-ttu-id="d50d2-121">Pomimo różnic między strumieniami może być bardziej intuicyjny sposób postępowania z danymi i są one bardziej istotne w nowoczesnych programowaniu, z naciskiem na LINQ, reaktywne strumienie, programowanie funkcjonalne i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="d50d2-121">Despite the difference, streams can be a more intuitive way of dealing with this data and are more relevant in modern programming with the emphasis on LINQ, Reactive Streams, functional programming, and so on.</span></span>

<span data-ttu-id="d50d2-122">Definicja usługi wymaga dwóch komunikatów: jeden dla żądania oraz jeden dla strumienia.</span><span class="sxs-lookup"><span data-stu-id="d50d2-122">The service definition needs two messages: one for the request, and one for the stream.</span></span> <span data-ttu-id="d50d2-123">Usługa zwraca strumień `StockTickerUpdate` wiadomości `stream` za pomocą słowa kluczowego w jego `return` deklaracji.</span><span class="sxs-lookup"><span data-stu-id="d50d2-123">The service returns a stream of the `StockTickerUpdate` message using the `stream` keyword in its `return` declaration.</span></span> <span data-ttu-id="d50d2-124">Zalecamy dodanie `Timestamp` do aktualizacji, aby pokazać dokładną godzinę zmiany ceny.</span><span class="sxs-lookup"><span data-stu-id="d50d2-124">It's recommended that you add a `Timestamp` to the update to show the exact time the price changed.</span></span>

#### <a name="simple_stock_tickerproto"></a><span data-ttu-id="d50d2-125">simple_stock_ticker. proto</span><span class="sxs-lookup"><span data-stu-id="d50d2-125">simple_stock_ticker.proto</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.SimpleStockTickerServer.Protos";

import "google/protobuf/timestamp.proto";

package SimpleStockTickerServer;

service SimpleStockTicker {
  rpc Subscribe (SubscribeRequest) returns (stream StockTickerUpdate);
}

message SubscribeRequest {
  repeated string symbols = 1;
}

message StockTickerUpdate {
  string symbol = 1;
  int32 priceCents = 2;
  google.protobuf.Timestamp time = 3;
}
```

### <a name="implement-the-simplestockticker"></a><span data-ttu-id="d50d2-126">Implementowanie SimpleStockTicker</span><span class="sxs-lookup"><span data-stu-id="d50d2-126">Implement the SimpleStockTicker</span></span>

<span data-ttu-id="d50d2-127">Użyj ponownie fałszywego `StockPriceSubscriber` z projektu WCF, kopiując trzy klasy `TraderSys.StockMarket` z biblioteki klas do nowej biblioteki klas .NET standard w rozwiązaniu docelowym.</span><span class="sxs-lookup"><span data-stu-id="d50d2-127">Reuse the fake `StockPriceSubscriber` from the WCF project by copying the three classes from the `TraderSys.StockMarket` class library into a new .NET Standard class library in the target solution.</span></span> <span data-ttu-id="d50d2-128">W celu lepszego przestrzegania najlepszych rozwiązań należy `Factory` dodać typ, aby utworzyć jego wystąpienia, i `IStockPriceSubscriberFactory` zarejestrować ASP.NET Core usług iniekcji zależności.</span><span class="sxs-lookup"><span data-stu-id="d50d2-128">To better follow best practices, add a `Factory` type to create instances of it and register the `IStockPriceSubscriberFactory` with ASP.NET Core's dependency injection services.</span></span>

#### <a name="the-factory-implementation"></a><span data-ttu-id="d50d2-129">Implementacja fabryki</span><span class="sxs-lookup"><span data-stu-id="d50d2-129">The factory implementation</span></span>

```csharp
public interface IStockPriceSubscriberFactory
{
    IStockPriceSubscriber GetSubscriber(string[] symbols);
}

public class StockPriceSubscriberFactory : IStockPriceSubscriberFactory
{
    public IStockPriceSubscriber GetSubscriber(string[] symbols)
    {
        return new StockPriceSubscriber(symbols);
    }
}
```

#### <a name="registering-the-factory"></a><span data-ttu-id="d50d2-130">Rejestrowanie fabryki</span><span class="sxs-lookup"><span data-stu-id="d50d2-130">Registering the factory</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

<span data-ttu-id="d50d2-131">Teraz można użyć tej klasy do zaimplementowania usługi gRPC StockTicker.</span><span class="sxs-lookup"><span data-stu-id="d50d2-131">Now, this class can be used to implement the gRPC StockTicker service.</span></span>

#### <a name="stocktickerservicecs"></a><span data-ttu-id="d50d2-132">StockTickerService.cs</span><span class="sxs-lookup"><span data-stu-id="d50d2-132">StockTickerService.cs</span></span>

```csharp
public class StockTickerService : Protos.SimpleStockTicker.SimpleStockTickerBase
{
    private readonly IStockPriceSubscriberFactory _subscriberFactory;

    public StockTickerService(IStockPriceSubscriberFactory subscriberFactory)
    {
        _subscriberFactory = subscriberFactory;
    }

    public override async Task Subscribe(SubscribeRequest request, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
    {
        var subscriber = _subscriberFactory.GetSubscriber(request.Symbols.ToArray());

        subscriber.Update += async (sender, args) =>
            await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

        await AwaitCancellation(context.CancellationToken);
    }

    private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
    {
        try
        {
            await stream.WriteAsync(new StockTickerUpdate
            {
                Symbol = symbol,
                PriceCents = (int)(price * 100),
                Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
            });
        }
        catch (Exception e)
        {
            // Handle any errors due to broken connection etc.
            _logger.LogError($"Failed to write message: {e.Message}");
        }
    }

    private static Task AwaitCancellation(CancellationToken token)
    {
        var completion = new TaskCompletionSource<object>();
        token.Register(() => completion.SetResult(null));
        return completion.Task;
    }
}
```

<span data-ttu-id="d50d2-133">Jak widać, chociaż deklaracja w `.proto` pliku mówi metody "Returns" `StockTickerUpdate` strumienia komunikatów, w rzeczywistości zwraca wanilię `Task`.</span><span class="sxs-lookup"><span data-stu-id="d50d2-133">As you can see, although the declaration in the `.proto` file says the method "returns" a stream of `StockTickerUpdate` messages, in fact it returns a vanilla `Task`.</span></span> <span data-ttu-id="d50d2-134">Zadanie tworzenia strumienia jest obsługiwane przez wygenerowany kod i biblioteki środowiska uruchomieniowego gRPC, które zapewniają `IServerStreamWriter<StockTickerUpdate>` strumień odpowiedzi, gotowy do użycia.</span><span class="sxs-lookup"><span data-stu-id="d50d2-134">The job of creating the stream is handled by the generated code and the gRPC runtime libraries, which provide the `IServerStreamWriter<StockTickerUpdate>` response stream, ready to use.</span></span>

<span data-ttu-id="d50d2-135">W przeciwieństwie do usługi WCF Duplex, w której wystąpienie klasy usługi jest utrzymywane, gdy połączenie jest otwarte, usługa gRPC używa zwracanego zadania, aby zachować aktywność usługi.</span><span class="sxs-lookup"><span data-stu-id="d50d2-135">Unlike a WCF duplex service, where the instance of the service class is kept alive while the connection is open, the gRPC service uses the returned Task to keep the service alive.</span></span> <span data-ttu-id="d50d2-136">Zadanie nie powinno zostać ukończone do momentu zamknięcia połączenia.</span><span class="sxs-lookup"><span data-stu-id="d50d2-136">The Task shouldn't complete until the connection is closed.</span></span>

<span data-ttu-id="d50d2-137">Usługa może określić, kiedy klient zamknął połączenie przy użyciu narzędzia `CancellationToken` `ServerCallContext`z.</span><span class="sxs-lookup"><span data-stu-id="d50d2-137">The service can tell when the client has closed the connection by using the `CancellationToken` from the `ServerCallContext`.</span></span> <span data-ttu-id="d50d2-138">Prosta metoda `AwaitCancellation`statyczna, jest używana do tworzenia zadania, które kończy się po anulowaniu tokenu.</span><span class="sxs-lookup"><span data-stu-id="d50d2-138">A simple static method, `AwaitCancellation`, is used to create a Task that completes when the token is canceled.</span></span>

<span data-ttu-id="d50d2-139">W metodzie, należy `StockPriceSubscriber` uzyskać i dodać program obsługi zdarzeń, który zapisuje w strumieniu odpowiedzi. `Subscribe`</span><span class="sxs-lookup"><span data-stu-id="d50d2-139">In the `Subscribe` method, then, get a `StockPriceSubscriber` and add an event handler that writes to the response stream.</span></span> <span data-ttu-id="d50d2-140">Następnie poczekaj na zamknięcie połączenia przed natychmiastowe `subscriber` usunięciem, aby zapobiec próbie zapisu danych do zamkniętego strumienia.</span><span class="sxs-lookup"><span data-stu-id="d50d2-140">Then wait for the connection to be closed, before immediately disposing the `subscriber` to prevent it trying to write data to the closed stream.</span></span>

<span data-ttu-id="d50d2-141">`WriteUpdateAsync` Metoda mablokdoobsługi`try` wszelkich błędów, które mogą wystąpić podczas zapisywania komunikatu w strumieniu. / `catch`</span><span class="sxs-lookup"><span data-stu-id="d50d2-141">The `WriteUpdateAsync` method has a `try`/`catch` block to handle any errors that might happen when writing a message to the stream.</span></span> <span data-ttu-id="d50d2-142">Jest to ważne zagadnienie w przypadku trwałych połączeń za pośrednictwem sieci, które mogą być uszkodzone w dowolnym milisekundach, niezależnie od tego, czy wystąpił błąd w dowolnym miejscu.</span><span class="sxs-lookup"><span data-stu-id="d50d2-142">This is an important consideration in persistent connections over networks, which could be broken at any millisecond, whether intentionally or because of a failure somewhere.</span></span>

### <a name="using-the-stocktickerservice-from-a-client-application"></a><span data-ttu-id="d50d2-143">Korzystanie z StockTickerService z aplikacji klienckiej</span><span class="sxs-lookup"><span data-stu-id="d50d2-143">Using the StockTickerService from a client application</span></span>

<span data-ttu-id="d50d2-144">Wykonaj te same kroki w poprzedniej sekcji, aby utworzyć udostępnioną bibliotekę klas klientów z `.proto` pliku.</span><span class="sxs-lookup"><span data-stu-id="d50d2-144">Follow the same steps in the previous section to create a shareable client class library from the `.proto` file.</span></span> <span data-ttu-id="d50d2-145">W przykładzie znajduje się Aplikacja konsolowa programu .NET Core 3,0, która pokazuje, jak korzystać z klienta programu.</span><span class="sxs-lookup"><span data-stu-id="d50d2-145">In the sample, there's a .NET Core 3.0 console application that demonstrates how to use the client.</span></span>

#### <a name="example-programcs"></a><span data-ttu-id="d50d2-146">Przykład Program.cs</span><span class="sxs-lookup"><span data-stu-id="d50d2-146">Example Program.cs</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using var channel = GrpcChannel.ForAddress("https://localhost:5001");
        var client = new SimpleStockTicker.SimpleStockTickerClient(channel);

        var request = new SubscribeRequest();
        request.Symbols.AddRange(args);

        using var stream = client.Subscribe(request);

        var tokenSource = new CancellationTokenSource();

        var task = DisplayAsync(stream.ResponseStream, tokenSource.Token);

        WaitForExitKey();

        tokenSource.Cancel();
        await task;
    }
}
```

<span data-ttu-id="d50d2-147">W takim przypadku `Subscribe` Metoda wygenerowanego klienta nie jest asynchroniczna.</span><span class="sxs-lookup"><span data-stu-id="d50d2-147">In this case, the `Subscribe` method on the generated client isn't asynchronous.</span></span> <span data-ttu-id="d50d2-148">Strumień jest tworzony i użyteczny od razu, ponieważ jego `MoveNext` Metoda jest asynchroniczna i po raz pierwszy jest wywoływana, dopóki połączenie nie będzie aktywne.</span><span class="sxs-lookup"><span data-stu-id="d50d2-148">The stream is created and usable right away, because its `MoveNext` method is asynchronous and the first time it's called it won't complete until the connection is alive.</span></span>

<span data-ttu-id="d50d2-149">Strumień jest przesyłany do metody asynchronicznej `DisplayAsync` . aplikacja czeka, aż użytkownik naciśnie klawisz, a następnie anuluje `DisplayAsync` metodę i czeka na ukończenie zadania przed wyjściem.</span><span class="sxs-lookup"><span data-stu-id="d50d2-149">The stream is passed to an async `DisplayAsync` method; the application then waits for the user to press a key, then cancels the `DisplayAsync` method and waits for the task to complete before exiting.</span></span>

> [!NOTE]
> <span data-ttu-id="d50d2-150">Ten kod używa składni New C# 8 "Using deklaracji", aby usunąć strumień i kanał, gdy metoda zostanie `Main` zakończona.</span><span class="sxs-lookup"><span data-stu-id="d50d2-150">This code is using the new C# 8 "using declaration" syntax to dispose of the stream and the channel when the `Main` method exits.</span></span> <span data-ttu-id="d50d2-151">Jest to mała zmiana, ale całkiem taka, która zmniejsza wcięcia i puste wiersze.</span><span class="sxs-lookup"><span data-stu-id="d50d2-151">It's a small change, but a nice one that reduces indentations and empty lines.</span></span>

#### <a name="consume-the-stream"></a><span data-ttu-id="d50d2-152">Korzystanie z strumienia</span><span class="sxs-lookup"><span data-stu-id="d50d2-152">Consume the stream</span></span>

<span data-ttu-id="d50d2-153">Funkcja WCF użyła interfejsów wywołania zwrotnego, aby umożliwić serwerowi wywoływanie metod bezpośrednio na kliencie.</span><span class="sxs-lookup"><span data-stu-id="d50d2-153">WCF used callback interfaces to allow the server to call methods directly on the client.</span></span> <span data-ttu-id="d50d2-154">strumienie gRPC działają inaczej.</span><span class="sxs-lookup"><span data-stu-id="d50d2-154">gRPC streams work differently.</span></span> <span data-ttu-id="d50d2-155">Klient wykonuje iterację na zwracanym strumieniu i przetwarza komunikaty, tak jakby były zwracane z metody lokalnej zwracającej `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="d50d2-155">The client iterates over the returned stream and processes messages, just as though they were returned from a local method returning an `IEnumerable`.</span></span>

<span data-ttu-id="d50d2-156">Typ działa `MoveNext` podobnie do `Current` : istnieje metoda, która zwróci wartość PRAWDA, o ile istnieje więcej danych, i Właściwość zwracająca najnowszą wartość. `IEnumerator<T>` `IAsyncStreamReader<T>`</span><span class="sxs-lookup"><span data-stu-id="d50d2-156">The `IAsyncStreamReader<T>` type works much like an `IEnumerator<T>`: there's a `MoveNext` method that will return true as long as there's more data, and a `Current` property that returns the latest value.</span></span> <span data-ttu-id="d50d2-157">Jedyną różnicą jest to, `MoveNext` że metoda zwraca `Task<bool>` a nie tylko `bool`.</span><span class="sxs-lookup"><span data-stu-id="d50d2-157">The only difference is that the `MoveNext` method returns a `Task<bool>` instead of just a `bool`.</span></span> <span data-ttu-id="d50d2-158">Metoda rozszerzenia otacza strumień C# w standardzie 8 `IAsyncEnumerable` , który może być używany z nową `await foreach` składnią. `ReadAllAsync`</span><span class="sxs-lookup"><span data-stu-id="d50d2-158">The `ReadAllAsync` extension method wraps the stream in a standard C# 8 `IAsyncEnumerable` that can be used with the new `await foreach` syntax.</span></span>

```csharp
static async Task DisplayAsync(IAsyncStreamReader<StockTickerUpdate> stream, CancellationToken token)
{
    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            Console.WriteLine($"{update.Symbol}: {update.Price}");
        }
    }
    catch (RpcException e) when (e.StatusCode == StatusCode.Cancelled)
    {
        return;
    }
    catch (OperationCanceledException)
    {
        Console.WriteLine("Finished.");
    }
}
```

> [!TIP]
> <span data-ttu-id="d50d2-159">Sekcja w [bibliotekach klienta](client-libraries.md#iobservable) na końcu tego rozdziału przedstawia sposób dodawania metody rozszerzenia i klas, które mają być zawijane `IAsyncStreamReader<T>` `IObservable<T>` dla deweloperów za pomocą reaktywnych wzorców programistycznych.</span><span class="sxs-lookup"><span data-stu-id="d50d2-159">The section on [client libraries](client-libraries.md#iobservable) at the end of this chapter looks at how to add an extension method and classes to wrap `IAsyncStreamReader<T>` in an `IObservable<T>` for developers using reactive programming patterns.</span></span>

<span data-ttu-id="d50d2-160">Ponownie należy zachować ostrożność, aby przechwytywać wyjątki w tym miejscu ze względu na możliwość awarii sieci <xref:System.OperationCanceledException> , a także to, że będzie ono nieuniknione, ponieważ <xref:System.Threading.CancellationToken> kod używa pętli do przerwania.</span><span class="sxs-lookup"><span data-stu-id="d50d2-160">Again, be careful to catch exceptions here because of the possibility of network failure, as well as the <xref:System.OperationCanceledException> that will inevitably be thrown because the code is using a <xref:System.Threading.CancellationToken> to break the loop.</span></span> <span data-ttu-id="d50d2-161">Typ zawiera wiele przydatnych informacji o błędach środowiska uruchomieniowego gRPC, w `StatusCode`tym. `RpcException`</span><span class="sxs-lookup"><span data-stu-id="d50d2-161">The `RpcException` type has a lot of useful information about gRPC runtime errors, including the `StatusCode`.</span></span> <span data-ttu-id="d50d2-162">Aby uzyskać więcej informacji, zobacz [ *Obsługa błędów* w rozdziale 4](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="d50d2-162">For more information, see [*Error handling* in Chapter 4](error-handling.md)</span></span>

## <a name="bidirectional-streaming"></a><span data-ttu-id="d50d2-163">Przesyłanie strumieniowe dwukierunkowe</span><span class="sxs-lookup"><span data-stu-id="d50d2-163">Bidirectional streaming</span></span>

<span data-ttu-id="d50d2-164">Usługa WCF Full-Duplex umożliwia asynchroniczne wysyłanie komunikatów w czasie rzeczywistym w obu kierunkach.</span><span class="sxs-lookup"><span data-stu-id="d50d2-164">A WCF full-duplex service allows for asynchronous, real-time messaging in both directions.</span></span> <span data-ttu-id="d50d2-165">W przykładzie przesyłania strumieniowego serwera klient uruchamia żądanie, a następnie odbiera strumień aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="d50d2-165">In the server streaming example, the client starts a request, then receives a stream of updates.</span></span> <span data-ttu-id="d50d2-166">Lepsza wersja tej usługi pozwala klientowi dodawać i usuwać zasoby z listy bez konieczności zatrzymywania i tworzenia nowej subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="d50d2-166">A better version of that service would allow the client to add and remove stocks from the list without having to stop and create a new subscription.</span></span> <span data-ttu-id="d50d2-167">Ta funkcja została zaimplementowana w [przykładowym rozwiązaniu FullStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="d50d2-167">That functionality has been implemented in the [FullStockTicker sample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span></span>

<span data-ttu-id="d50d2-168">`IFullStockTickerService` Interfejs zawiera trzy metody:</span><span class="sxs-lookup"><span data-stu-id="d50d2-168">The `IFullStockTickerService` interface provides three methods:</span></span>

- <span data-ttu-id="d50d2-169">`Subscribe`uruchamia połączenie.</span><span class="sxs-lookup"><span data-stu-id="d50d2-169">`Subscribe` starts the connection.</span></span>
- <span data-ttu-id="d50d2-170">`AddSymbol`Dodaje symbol giełdowy do obejrzenia.</span><span class="sxs-lookup"><span data-stu-id="d50d2-170">`AddSymbol` adds a stock symbol to watch.</span></span>
- <span data-ttu-id="d50d2-171">`RemoveSymbol`usuwa symbol z listy obserwowanych.</span><span class="sxs-lookup"><span data-stu-id="d50d2-171">`RemoveSymbol` removes a symbol from the watched list.</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(IFullStockTickerCallback))]
public interface IFullStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe();

    [OperationContract(IsOneWay = true)]
    void AddSymbol(string symbol);

    [OperationContract(IsOneWay = true)]
    void RemoveSymbol(string symbol);
}
```

<span data-ttu-id="d50d2-172">Interfejs wywołania zwrotnego pozostaje taki sam.</span><span class="sxs-lookup"><span data-stu-id="d50d2-172">The callback interface remains the same.</span></span>

<span data-ttu-id="d50d2-173">Implementacja tego wzorca w gRPC jest mniej prosta, ponieważ istnieją teraz dwa strumienie danych z przekazywaniem komunikatów: jeden z klienta do serwera, a drugi z serwera do klienta.</span><span class="sxs-lookup"><span data-stu-id="d50d2-173">Implementing this pattern in gRPC is less straightforward, because there are now two streams of data with messages being passed: one from client to server, and another from server to client.</span></span> <span data-ttu-id="d50d2-174">Nie jest możliwe użycie wielu metod w celu zaimplementowania operacji dodawania i usuwania, ale więcej niż jeden typ komunikatu może być przekazano do pojedynczego strumienia przy użyciu `Any` typu lub `oneof` słowa kluczowego, które zostały omówione w [rozdziale 3](protobuf-any-oneof.md).</span><span class="sxs-lookup"><span data-stu-id="d50d2-174">It isn't possible to use multiple methods to implement the Add and Remove operation, but more than one type of message can be passed on a single stream, using either the `Any` type or `oneof` keyword, which were covered in [Chapter 3](protobuf-any-oneof.md).</span></span>

<span data-ttu-id="d50d2-175">W przypadku gdy istnieje konkretny zestaw typów, które są akceptowalne, `oneof` jest lepszym rozwiązaniem.</span><span class="sxs-lookup"><span data-stu-id="d50d2-175">For a case where there's a specific set of types that are acceptable, `oneof` is a better way to go.</span></span> <span data-ttu-id="d50d2-176">Użyj elementu `ActionMessage` , który może zawierać `AddSymbolRequest` lub `RemoveSymbolRequest`.</span><span class="sxs-lookup"><span data-stu-id="d50d2-176">Use an `ActionMessage` that can hold either an `AddSymbolRequest` or a `RemoveSymbolRequest`.</span></span>

```protobuf
message ActionMessage {
  oneof action {
    AddSymbolRequest add = 1;
    RemoveSymbolRequest remove = 2;
  }
}

message AddSymbolRequest {
  string symbol = 1;
}

message RemoveSymbolRequest {
  string symbol = 1;
}
```

<span data-ttu-id="d50d2-177">Zadeklaruj dwukierunkową usługę przesyłania strumieniowego, która pobiera strumień `ActionMessage` komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d50d2-177">Declare a bi-directional streaming service that takes a stream of `ActionMessage` messages.</span></span>

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

<span data-ttu-id="d50d2-178">Implementacja tej usługi jest podobna do powyższego przykładu, z wyjątkiem `Subscribe` pierwszego parametru metody jest `IAsyncStreamReader<ActionMessage>`teraz, który może służyć do obsługi `Add` żądań i `Remove` .</span><span class="sxs-lookup"><span data-stu-id="d50d2-178">The implementation for this service is similar to the previous example, except the first parameter of the `Subscribe` method is now an `IAsyncStreamReader<ActionMessage>`, which can be used to handle the `Add` and `Remove` requests.</span></span>

```csharp
public override async Task Subscribe(IAsyncStreamReader<ActionMessage> requestStream, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
{
    using var subscriber = _subscriberFactory.GetSubscriber();

    subscriber.Update += async (sender, args) =>
        await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

    var actionsTask = HandleActions(requestStream, subscriber, context.CancellationToken);

    _logger.LogInformation("Subscription started.");
    await AwaitCancellation(context.CancellationToken);

    try { await actionsTask; } catch { /* Ignored */ }

    _logger.LogInformation("Subscription finished.");
}

private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
{
    try
    {
        await stream.WriteAsync(new StockTickerUpdate
        {
            Symbol = symbol,
            PriceCents = (int)(price * 100),
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }
    catch (Exception e)
    {
        // Handle any errors due to broken connection etc.
        _logger.LogError($"Failed to write message: {e.Message}");
    }
}

private static Task AwaitCancellation(CancellationToken token)
{
    var completion = new TaskCompletionSource<object>();
    token.Register(() => completion.SetResult(null));
    return completion.Task;
}
```

<span data-ttu-id="d50d2-179">Klasa, która gRPC wygenerowała gwarancje dla Stanów Zjednoczonych, `Add` że `Remove` tylko jedna z właściwości i może być ustawiona, i `null` znalezienie, która z nich nie jest prawidłowym sposobem wyszukiwania, który typ komunikatu jest używany, ale istnieje lepszy sposób `ActionMessage` .</span><span class="sxs-lookup"><span data-stu-id="d50d2-179">The `ActionMessage` class that gRPC has generated for us guarantees that only one of the `Add` and `Remove` properties can be set, and finding which one isn't `null` is a valid way of finding which type of message is used, but there's a better way.</span></span> <span data-ttu-id="d50d2-180">Generowanie kodu spowodowało również utworzenie `enum ActionOneOfCase` `ActionMessage` w klasie klasy, która wygląda następująco:</span><span class="sxs-lookup"><span data-stu-id="d50d2-180">The code generation also created an `enum ActionOneOfCase` in the `ActionMessage` class, which looks like this:</span></span>

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

<span data-ttu-id="d50d2-181">Właściwość `ActionCase` obiektu`ActionMessage` możebyćużywanazinstrukcją,abyokreślić,które`switch` pole jest ustawione.</span><span class="sxs-lookup"><span data-stu-id="d50d2-181">The property `ActionCase` on the `ActionMessage` object can be used with a `switch` statement to determine which field is set.</span></span>

```csharp
private async Task HandleActions(IAsyncStreamReader<ActionMessage> requestStream, IFullStockPriceSubscriber subscriber, CancellationToken token)
{
    await foreach (var action in requestStream.ReadAllAsync(token))
    {
        switch (action.ActionCase)
        {
            case ActionMessage.ActionOneofCase.None:
                _logger.LogWarning("No Action specified.");
                break;
            case ActionMessage.ActionOneofCase.Add:
                subscriber.Add(action.Add.Symbol);
                break;
            case ActionMessage.ActionOneofCase.Remove:
                subscriber.Remove(action.Remove.Symbol);
                break;
            default:
                _logger.LogWarning($"Unknown Action '{action.ActionCase}'.");
                break;
        }
    }
}
```

> [!TIP]
> <span data-ttu-id="d50d2-182">Instrukcja ma przypadek, który rejestruje ostrzeżenie w przypadku napotkania nieznanej `ActionOneOfCase` wartości. `default` `switch`</span><span class="sxs-lookup"><span data-stu-id="d50d2-182">The `switch` statement has a `default` case that logs a warning if an unknown `ActionOneOfCase` value is encountered.</span></span> <span data-ttu-id="d50d2-183">Może to być przydatne w przypadku, gdy klient korzysta z nowszej wersji `.proto` pliku, który dodał więcej akcji.</span><span class="sxs-lookup"><span data-stu-id="d50d2-183">This could be useful in indicating that a client is using a later version of the `.proto` file which has added more actions.</span></span> <span data-ttu-id="d50d2-184">Jest to jedną z przyczyn, przy `switch` użyciu której lepszym rozwiązaniem `null` jest testowanie w przypadku znanych pól.</span><span class="sxs-lookup"><span data-stu-id="d50d2-184">This is one reason why using a `switch` is better than testing for `null` on known fields.</span></span>

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a><span data-ttu-id="d50d2-185">Korzystanie z FullStockTickerService z aplikacji klienckiej</span><span class="sxs-lookup"><span data-stu-id="d50d2-185">Use the FullStockTickerService from a client application</span></span>

<span data-ttu-id="d50d2-186">Istnieje prosta aplikacja WPF platformy .NET Core 3,0, która przedstawia użycie tego bardziej złożonego klienta.</span><span class="sxs-lookup"><span data-stu-id="d50d2-186">There's a simple .NET Core 3.0 WPF application to demonstrate use of this more complex client.</span></span> <span data-ttu-id="d50d2-187">Pełną aplikację można znaleźć [w witrynie GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="d50d2-187">The full application can be found [on GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span></span>

<span data-ttu-id="d50d2-188">Klient jest używany w `MainWindowViewModel` klasie, która pobiera wystąpienie `FullStockTicker.FullStockTickerClient` typu z iniekcji zależności.</span><span class="sxs-lookup"><span data-stu-id="d50d2-188">The client is used in the `MainWindowViewModel` class, which gets an instance of the `FullStockTicker.FullStockTickerClient` type from dependency injection.</span></span>

```csharp
public class MainWindowViewModel : IAsyncDisposable, INotifyPropertyChanged
{
    private readonly FullStockTicker.FullStockTickerClient _client;
    private readonly AsyncDuplexStreamingCall<ActionMessage, StockTickerUpdate> _duplexStream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _responseTask;
    private string _addSymbol;

    public MainWindowViewModel(FullStockTicker.FullStockTickerClient client)
    {
        _cancellationTokenSource = new CancellationTokenSource();
        _client = client;
        _duplexStream = _client.Subscribe();
        _responseTask = HandleResponsesAsync(_cancellationTokenSource.Token);

        AddCommand = new AsyncCommand(Add, CanAdd);
    }
```

<span data-ttu-id="d50d2-189">Obiekt zwrócony przez `client.Subscribe()` metodę jest teraz wystąpieniem typu `AsyncDuplexStreamingCall<TRequest, TResponse>`biblioteki gRPC, który umożliwia `RequestStream` wysyłanie żądań do serwera i a `ResponseStream` do obsługi odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="d50d2-189">The object returned by the `client.Subscribe()` method is now an instance of the gRPC library type `AsyncDuplexStreamingCall<TRequest, TResponse>`, which provides a `RequestStream` for sending requests to the server, and a `ResponseStream` for handling responses.</span></span>

<span data-ttu-id="d50d2-190">Strumień żądania jest używany z niektórych metod WPF `ICommand` do dodawania i usuwania symboli.</span><span class="sxs-lookup"><span data-stu-id="d50d2-190">The request stream is used from some WPF `ICommand` methods to add and remove symbols.</span></span> <span data-ttu-id="d50d2-191">Dla każdej operacji Ustaw odpowiednie pole na `ActionMessage` obiekcie:</span><span class="sxs-lookup"><span data-stu-id="d50d2-191">For each operation, set the relevant field on an `ActionMessage` object:</span></span>

```csharp
private async Task Add()
{
    if (CanAdd())
    {
        await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Add = new AddSymbolRequest {Symbol = AddSymbol}});
    }
}

public async Task Remove(PriceViewModel priceViewModel)
{
    await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Remove = new RemoveSymbolRequest {Symbol = priceViewModel.Symbol}});
    Prices.Remove(priceViewModel);
}
```

> [!IMPORTANT]
> <span data-ttu-id="d50d2-192">Ustawienie wartości `oneof` pola w komunikacie automatycznie czyści wszystkie pola, które zostały wcześniej ustawione.</span><span class="sxs-lookup"><span data-stu-id="d50d2-192">Setting a `oneof` field's value on a message automatically clears any fields that have been previously set.</span></span>

<span data-ttu-id="d50d2-193">Strumień odpowiedzi jest obsługiwany w `async` metodzie, a zwracane przez nią wartości `Task` są usuwane, gdy okno zostanie zamknięte.</span><span class="sxs-lookup"><span data-stu-id="d50d2-193">The stream of responses is handled in an `async` method, and the `Task` it returns is held to be disposed when the window is closed.</span></span>

```csharp
private async Task HandleResponsesAsync(CancellationToken token)
{
    var stream = _duplexStream.ResponseStream;

    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            var price = Prices.FirstOrDefault(p => p.Symbol.Equals(update.Symbol));
            if (price == null)
            {
                price = new PriceViewModel(this) {Symbol = update.Symbol, Price = update.PriceCents / 100m};
                Prices.Add(price);
            }
            else
            {
                price.Price = update.PriceCents / 100m;
            }
        }
    }
    catch (OperationCancelledException) { }
}
```

### <a name="client-clean-up"></a><span data-ttu-id="d50d2-194">Czyszczenie klienta</span><span class="sxs-lookup"><span data-stu-id="d50d2-194">Client clean-up</span></span>

<span data-ttu-id="d50d2-195">Gdy `MainWindowViewModel` okno zostanie zamknięte i zostanie usunięte ( `Closed` ze zdarzenia `MainWindow`), zalecamy poprawność usuwania `AsyncDuplexStreamingCall` obiektu.</span><span class="sxs-lookup"><span data-stu-id="d50d2-195">When the window is closed and the `MainWindowViewModel` is disposed (from the `Closed` event of `MainWindow`), it's recommended that you properly dispose the `AsyncDuplexStreamingCall` object.</span></span> <span data-ttu-id="d50d2-196">W szczególności `CompleteAsync` Metoda `RequestStream` powinna zostać wywołana, aby bezpiecznie zamknąć strumień na serwerze.</span><span class="sxs-lookup"><span data-stu-id="d50d2-196">In particular, the `CompleteAsync` method on the `RequestStream` should be called to gracefully close the stream on the server.</span></span> <span data-ttu-id="d50d2-197">Poniższy przykład przedstawia `DisposeAsync` metodę z przykładowego widoku — model:</span><span class="sxs-lookup"><span data-stu-id="d50d2-197">The following example shows the `DisposeAsync` method from the sample view-model:</span></span>

```csharp
public ValueTask DisposeAsync()
{
    try
    {
        await _duplexStream.RequestStream.CompleteAsync().ConfigureAwait(false);
        await _responseTask.ConfigureAwait(false);
    }
    finally
    {
        _duplexStream.Dispose();
    }
}
```

<span data-ttu-id="d50d2-198">Zamykające strumienie żądań umożliwia serwerowi usuwanie własnych zasobów w odpowiednim czasie.</span><span class="sxs-lookup"><span data-stu-id="d50d2-198">Closing request streams enables the server to dispose of its own resources in a timely manner.</span></span> <span data-ttu-id="d50d2-199">Poprawia to wydajność i skalowalność usług i zapobiega wyjątkom.</span><span class="sxs-lookup"><span data-stu-id="d50d2-199">This improves the efficiency and scalability of services and prevents exceptions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d50d2-200">[Poprzedni](migrate-request-reply.md)
>[Następny](streaming-versus-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="d50d2-200">[Previous](migrate-request-reply.md)
[Next](streaming-versus-repeated.md)</span></span>