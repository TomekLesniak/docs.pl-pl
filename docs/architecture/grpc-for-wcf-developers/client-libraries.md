---
title: Tworzenie bibliotek klienckich gRPC — gRPC dla deweloperów WCF
description: Omówienie udostępnionych bibliotek klientów/pakietów dla usług gRPC Services.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 44a749c888528ca244f41b5b88354d7ed1db4190
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184590"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="24603-103">Tworzenie bibliotek klienckich gRPC</span><span class="sxs-lookup"><span data-stu-id="24603-103">Create gRPC client libraries</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="24603-104">Nie jest konieczne dystrybuowanie bibliotek klienckich dla aplikacji gPRC.</span><span class="sxs-lookup"><span data-stu-id="24603-104">It isn't necessary to distribute client libraries for a gPRC application.</span></span> <span data-ttu-id="24603-105">Można utworzyć udostępnioną bibliotekę `.proto` plików w organizacji, a inne zespoły mogą używać tych plików do generowania kodu klienta w swoich własnych projektach.</span><span class="sxs-lookup"><span data-stu-id="24603-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="24603-106">Ale jeśli masz prywatne repozytorium NuGet i wiele innych zespołów używa platformy .NET Core, tworzenie i publikowanie pakietów NuGet klienta w ramach projektu usługi może być dobrym sposobem udostępniania i promowania usługi.</span><span class="sxs-lookup"><span data-stu-id="24603-106">But if you have a private NuGet repository and many other teams are using .NET Core, creating and publishing client NuGet packages as part of your service project may be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="24603-107">Jedną z zalet dystrybucji biblioteki klienta jest możliwość udoskonalenia wygenerowanych klas gRPC i protobuf przy użyciu przydatnych metod i właściwości.</span><span class="sxs-lookup"><span data-stu-id="24603-107">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="24603-108">W kodzie klienta, podobnie jak na serwerze, wszystkie klasy są deklarowane jako `partial` tak, aby można je było rozwijać bez konieczności edytowania wygenerowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="24603-108">In the client code, as in the server, all the classes are declared as `partial` so you can extend them without editing the generated code.</span></span> <span data-ttu-id="24603-109">Oznacza to, że można łatwo dodawać konstruktory, metody, właściwości obliczeniowe i nie tylko do typów podstawowych.</span><span class="sxs-lookup"><span data-stu-id="24603-109">This means it's easy to add constructors, methods, calculated properties, and more to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="24603-110">**Nie** należy używać niestandardowego kodu w celu zapewnienia podstawowych funkcji, ponieważ oznacza to, że funkcje byłyby ograniczone do zespołów .NET korzystających z biblioteki udostępnionej, a nie do zespołów korzystających z innych języków lub platform, takich jak Python lub Java.</span><span class="sxs-lookup"><span data-stu-id="24603-110">You should **not** use custom code to provide essential functionality, as this would mean that functionality would be restricted to .NET teams using the shared library, and not to teams using other languages or platforms such as Python or Java.</span></span>

<span data-ttu-id="24603-111">W środowisku wieloplatformowym, w którym różne zespoły często korzystają z różnych języków programowania i struktur, lub gdzie interfejs API jest dostępny zewnętrznie, wystarczy `.proto` udostępnić pliki, aby deweloperzy mogli generować własnych klientów, najlepszym sposobem Upewnij się, jak wiele zespołów może uzyskać dostęp do usługi gRPC.</span><span class="sxs-lookup"><span data-stu-id="24603-111">In a multi-platform environment where different teams frequently use different programming languages and frameworks, or where your API is externally accessible, simply sharing `.proto` files so developers can generate their own clients is the best way to ensure as many teams as possible can access your gRPC service.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="24603-112">Przydatne rozszerzenia</span><span class="sxs-lookup"><span data-stu-id="24603-112">Useful extensions</span></span>

<span data-ttu-id="24603-113">Istnieją dwa często używane interfejsy w programie .NET do obsługi strumieni obiektów: <xref:System.Collections.Generic.IEnumerable%601> i. <xref:System.IObservable%601></span><span class="sxs-lookup"><span data-stu-id="24603-113">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="24603-114">Począwszy od platformy .NET Core 3,0 C# i 8,0, istnieje <xref:System.Collections.Generic.IAsyncEnumerable%601> interfejs do przetwarzania strumieni `await foreach` asynchronicznie i Składnia służąca do korzystania z interfejsu.</span><span class="sxs-lookup"><span data-stu-id="24603-114">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="24603-115">Ta sekcja przedstawia kod wielokrotnego użytku do zastosowania tych interfejsów do strumieni gRPC.</span><span class="sxs-lookup"><span data-stu-id="24603-115">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="24603-116">W przypadku bibliotek klienckich programu .NET Core gRPC istnieje `ReadAllAsync` Metoda rozszerzająca dla `IAsyncStreamReader<T>` programu, która tworzy `IAsyncEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="24603-116">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>`.</span></span> <span data-ttu-id="24603-117">W przypadku deweloperów korzystających z programu reaktywnie programowanie taka metoda `IObservable<T>` rozszerzania może wyglądać następująco.</span><span class="sxs-lookup"><span data-stu-id="24603-117">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` might look like this.</span></span>

### <a name="iobservable"></a><span data-ttu-id="24603-118">IObservable</span><span class="sxs-lookup"><span data-stu-id="24603-118">IObservable</span></span>

<span data-ttu-id="24603-119">Interfejs jest odwrotny od `IEnumerable<T>`. `IObservable<T>`</span><span class="sxs-lookup"><span data-stu-id="24603-119">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="24603-120">Zamiast ściągania elementów ze strumienia, podejście reaktywne umożliwia wypychanie elementów do subskrybenta.</span><span class="sxs-lookup"><span data-stu-id="24603-120">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="24603-121">Jest to bardzo podobne do gRPC strumieni i można je łatwo otoczyć `IObservable<T>` `IAsyncStreamReader<T>`wokół siebie.</span><span class="sxs-lookup"><span data-stu-id="24603-121">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` around an `IAsyncStreamReader<T>`.</span></span>

<span data-ttu-id="24603-122">Ten kod jest dłuższy niż `IAsyncEnumerable<T>` kod, ponieważ C# nie ma wbudowanej obsługi pracy z observables, więc należy utworzyć klasę implementacji ręcznie.</span><span class="sxs-lookup"><span data-stu-id="24603-122">This code is longer than the `IAsyncEnumerable<T>` code because C# doesn't have built-in support for working with observables, so the implementation class has to be created manually.</span></span> <span data-ttu-id="24603-123">Jest to Klasa generyczna, dlatego jedna implementacja będzie działała dla wszystkich typów.</span><span class="sxs-lookup"><span data-stu-id="24603-123">It's a generic class, though, so a single implementation will work across all types.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public class GrpcStreamObservable<T> : IObservable<T>
    {
        private readonly IAsyncStreamReader<T> _reader;
        private readonly CancellationToken _token;
        private int _used;

        public Observable(IAsyncStreamReader<T> reader, CancellationToken token = default)
        {
            _reader = reader;
            _token = token;
            _used = 0;
        }

        public IDisposable Subscribe(IObserver<T> observer) =>
            Interlocked.Exchange(ref _used, 1) == 0
                ? new GrpcStreamSubscription(_reader, observer, _token)
                : throw new InvalidOperationException("Subscribe can only be called once.");

    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="24603-124">Ta niezauważalna implementacja umożliwia `Subscribe` tylko jednokrotne wywołanie metody, ponieważ wielu subskrybentów próbujących odczytać dane ze strumienia mógłby spowodować chaos.</span><span class="sxs-lookup"><span data-stu-id="24603-124">This observable implementation only allows the `Subscribe` method to be called once, as having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="24603-125">Istnieją operatory, takie jak `Replay` [System. Reactive. LINQ](https://www.nuget.org/packages/System.Reactive.Linq) , które umożliwiają buforowanie i powtarzanie udostępniania observables, które mogą być używane z tą implementacją.</span><span class="sxs-lookup"><span data-stu-id="24603-125">There are operators such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq) that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="24603-126">Klasa obsługuje Wyliczenie `IAsyncStreamReader`. `GrpcStreamSubscription`</span><span class="sxs-lookup"><span data-stu-id="24603-126">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`.</span></span>

```csharp
public class GrpcStreamSubscription : IDisposable
{
    private readonly Task _task;
    private readonly CancellationTokenSource _tokenSource;
    private bool _completed;

    public Subscription(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        Debug.Assert(reader != null);
        Debug.Assert(observer != null);
        _tokenSource = new CancellationTokenSource();
        token.Register(_tokenSource.Cancel);
        _task = Run(reader, observer, _tokenSource.Token);
    }

    private async Task Run(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        while (!token.IsCancellationRequested)
        {
            try
            {
                if (!await reader.MoveNext(token)) break;
            }
            catch (RpcException e) when (e.StatusCode == Grpc.Core.StatusCode.NotFound)
            {
                break;
            }
            catch (OperationCanceledException)
            {
                break;
            }
            catch (Exception e)
            {
                observer.OnError(e);
                _completed = true;
                return;
            }

            observer.OnNext(reader.Current);
        }

        _completed = true;
        observer.OnCompleted();
    }

    public void Dispose()
    {
        if (!_completed && !_tokenSource.IsCancellationRequested)
        {
            _tokenSource.Cancel();
        }

        _tokenSource.Dispose();
        _task.Dispose();
    }

}
```

<span data-ttu-id="24603-127">Wszystkie wymagane teraz jest prostą metodą rozszerzenia, aby można było uzyskać zauważalność z czytnika strumienia.</span><span class="sxs-lookup"><span data-stu-id="24603-127">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public static class AsyncStreamReaderObservableExtensions
    {
        public static IObservable<T> AsObservable<T>(this IAsyncStreamReader<T> reader) =>
            new GrpcStreamObservable<T>(reader);
    }
}
```

## <a name="summary"></a><span data-ttu-id="24603-128">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="24603-128">Summary</span></span>

<span data-ttu-id="24603-129">Modele `IAsyncEnumerable` i`IObservable` są dobrze obsługiwane i dobrze udokumentowane sposoby postępowania z asynchronicznymi strumieniami danych w programie .NET.</span><span class="sxs-lookup"><span data-stu-id="24603-129">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="24603-130">Mapa gRPC strumienie w obu odmianach oferuje bliską integrację z nowoczesnymi i nieaktywnymi/asynchronicznymi stylami programowania.</span><span class="sxs-lookup"><span data-stu-id="24603-130">gRPC streams map well to both paradigms, offering close integration with the modern .NET Core framework and reactive/asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="24603-131">[Poprzedni](streaming-versus-repeated.md)
>[Następny](security.md)</span><span class="sxs-lookup"><span data-stu-id="24603-131">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>