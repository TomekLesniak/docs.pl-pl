---
title: Implementacja metody DisposeAsync
description: Dowiedz się, jak zaimplementować metody DisposeAsync i DisposeAsyncCore, aby przeprowadzić Oczyszczanie zasobów asynchronicznych.
author: IEvangelist
ms.author: dapine
ms.date: 08/25/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 268cea7584040ad92e2da75e5e03112480cda93c
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053181"
---
# <a name="implement-a-disposeasync-method"></a><span data-ttu-id="77d3f-103">Implementacja metody DisposeAsync</span><span class="sxs-lookup"><span data-stu-id="77d3f-103">Implement a DisposeAsync method</span></span>

<span data-ttu-id="77d3f-104"><xref:System.IAsyncDisposable?displayProperty=nameWithType>Interfejs został wprowadzony jako część języka C# 8,0.</span><span class="sxs-lookup"><span data-stu-id="77d3f-104">The <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface was introduced as part of C# 8.0.</span></span> <span data-ttu-id="77d3f-105">Metodę należy zaimplementować <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> , gdy trzeba przeprowadzić Oczyszczanie zasobów, tak jak podczas [implementowania metody Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="77d3f-105">You implement the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method when you need to perform resource cleanup, just as you would when [implementing a Dispose method](implementing-dispose.md).</span></span> <span data-ttu-id="77d3f-106">Jedną z najważniejszych różnic jest jednak to, że ta implementacja umożliwia asynchroniczne czyszczenie operacji.</span><span class="sxs-lookup"><span data-stu-id="77d3f-106">One of the key differences however, is that this implementation allows for asynchronous cleanup operations.</span></span> <span data-ttu-id="77d3f-107"><xref:System.IAsyncDisposable.DisposeAsync>Zwraca wartość <xref:System.Threading.Tasks.ValueTask> reprezentującą asynchroniczną operację Dispose.</span><span class="sxs-lookup"><span data-stu-id="77d3f-107">The <xref:System.IAsyncDisposable.DisposeAsync> returns a <xref:System.Threading.Tasks.ValueTask> that represents the asynchronous dispose operation.</span></span>

<span data-ttu-id="77d3f-108">Typowym scenariuszem jest implementowanie <xref:System.IAsyncDisposable> interfejsu, który klasy również implementują <xref:System.IDisposable> interfejs.</span><span class="sxs-lookup"><span data-stu-id="77d3f-108">It is typical when implementing the <xref:System.IAsyncDisposable> interface that classes will also implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="77d3f-109">Dobry wzorzec implementacji <xref:System.IAsyncDisposable> interfejsu jest przygotowany do synchronicznej lub asynchronicznej operacji Dispose.</span><span class="sxs-lookup"><span data-stu-id="77d3f-109">A good implementation pattern of the <xref:System.IAsyncDisposable> interface is to be prepared for either synchronous, or asynchronous dispose.</span></span> <span data-ttu-id="77d3f-110">Wszystkie wskazówki dotyczące wdrażania wzorca Dispose dotyczą również implementacji asynchronicznej.</span><span class="sxs-lookup"><span data-stu-id="77d3f-110">All of the guidance for implementing the dispose pattern also applies to the asynchronous implementation.</span></span> <span data-ttu-id="77d3f-111">W tym artykule założono, że wiesz już, jak [zaimplementować metodę Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="77d3f-111">This article assumes that you're already familiar with how to [implement a Dispose method](implementing-dispose.md).</span></span>

## <a name="disposeasync-and-disposeasynccore"></a><span data-ttu-id="77d3f-112">DisposeAsync () i DisposeAsyncCore ()</span><span class="sxs-lookup"><span data-stu-id="77d3f-112">DisposeAsync() and DisposeAsyncCore()</span></span>

<span data-ttu-id="77d3f-113"><xref:System.IAsyncDisposable>Interfejs deklaruje pojedynczą metodę bez parametrów, <xref:System.IAsyncDisposable.DisposeAsync> .</span><span class="sxs-lookup"><span data-stu-id="77d3f-113">The <xref:System.IAsyncDisposable> interface declares a single parameterless method, <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="77d3f-114">Każda Klasa Niezapieczętowana powinna mieć dodatkową `DisposeAsyncCore()` metodę, która również zwraca wartość <xref:System.Threading.Tasks.ValueTask> .</span><span class="sxs-lookup"><span data-stu-id="77d3f-114">Any non-sealed class should have an additional `DisposeAsyncCore()` method that also returns a <xref:System.Threading.Tasks.ValueTask>.</span></span>

- <span data-ttu-id="77d3f-115">`public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> Implementacja, która nie ma parametrów.</span><span class="sxs-lookup"><span data-stu-id="77d3f-115">A `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementation that has no parameters.</span></span>
- <span data-ttu-id="77d3f-116">`protected virtual ValueTask DisposeAsyncCore()`Metoda, której sygnatura:</span><span class="sxs-lookup"><span data-stu-id="77d3f-116">A `protected virtual ValueTask DisposeAsyncCore()` method whose signature is:</span></span>

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a><span data-ttu-id="77d3f-117">DisposeAsync () — Metoda</span><span class="sxs-lookup"><span data-stu-id="77d3f-117">The DisposeAsync() method</span></span>

<span data-ttu-id="77d3f-118">`public` `DisposeAsync()` Metoda bez parametrów jest wywoływana niejawnie w `await using` instrukcji i jej celem jest zwolnienie niezarządzanych zasobów, wykonanie ogólnego czyszczenia i wskazanie, że finalizator, jeśli taki istnieje, nie musi być uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="77d3f-118">The `public` parameterless `DisposeAsync()` method is called implicitly in an `await using` statement, and its purpose is to free unmanaged resources, perform general cleanup, and to indicate that the finalizer, if one is present, need not run.</span></span> <span data-ttu-id="77d3f-119">Zwalnianie pamięci skojarzonej z zarządzanym obiektem jest zawsze domeną [modułu wyrzucania elementów bezużytecznych](index.md).</span><span class="sxs-lookup"><span data-stu-id="77d3f-119">Freeing the memory associated with a managed object is always the domain of the [garbage collector](index.md).</span></span> <span data-ttu-id="77d3f-120">Z tego powodu ma standardową implementację:</span><span class="sxs-lookup"><span data-stu-id="77d3f-120">Because of this, it has a standard implementation:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of unmanaged resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> <span data-ttu-id="77d3f-121">Podstawowa różnica w asynchronicznym wzorcu usuwania w porównaniu do wzorca Dispose polega na tym, że wywołanie z <xref:System.IAsyncDisposable.DisposeAsync> `Dispose(bool)` metody przeciążenia jest podawane `false` jako argument.</span><span class="sxs-lookup"><span data-stu-id="77d3f-121">One primary difference in the async dispose pattern compared to the dispose pattern, is that the call from <xref:System.IAsyncDisposable.DisposeAsync> to the `Dispose(bool)` overload method is given `false` as an argument.</span></span> <span data-ttu-id="77d3f-122">Podczas implementowania <xref:System.IDisposable.Dispose?displayProperty=nameWithType> metody, jednak `true` zamiast tego jest przesyłane.</span><span class="sxs-lookup"><span data-stu-id="77d3f-122">When implementing the <xref:System.IDisposable.Dispose?displayProperty=nameWithType> method, however; `true` is passed instead.</span></span> <span data-ttu-id="77d3f-123">Dzięki temu można zapewnić równoważność funkcjonalną z synchronicznym wzorcem usuwania, a dodatkowo zapewnić, że ścieżki kodu finalizatora nadal są wywoływane.</span><span class="sxs-lookup"><span data-stu-id="77d3f-123">This helps ensure functional equivalence with the synchronous dispose pattern, and further ensures that finalizer code paths still get invoked.</span></span> <span data-ttu-id="77d3f-124">Innymi słowy, `DisposeAsyncCore()` Metoda usunie zarządzane zasoby asynchronicznie, więc nie ma potrzeby ich synchronicznego usuwania.</span><span class="sxs-lookup"><span data-stu-id="77d3f-124">In other words, the `DisposeAsyncCore()` method will dispose of managed resources asynchronously, so you don't want to dispose of them synchronously as well.</span></span> <span data-ttu-id="77d3f-125">W związku `Dispose(false)` z tym zamiast `Dispose(true)` .</span><span class="sxs-lookup"><span data-stu-id="77d3f-125">Therefore, call `Dispose(false)` instead of `Dispose(true)`.</span></span>

### <a name="the-disposeasynccore-method"></a><span data-ttu-id="77d3f-126">DisposeAsyncCore () — Metoda</span><span class="sxs-lookup"><span data-stu-id="77d3f-126">The DisposeAsyncCore() method</span></span>

<span data-ttu-id="77d3f-127">`DisposeAsyncCore()`Metoda jest przeznaczona do przeprowadzania asynchronicznego oczyszczania zarządzanych zasobów lub łączenia kaskadowego z `DisposeAsync()` .</span><span class="sxs-lookup"><span data-stu-id="77d3f-127">The `DisposeAsyncCore()` method is intended to perform the asynchronous cleanup of managed resources or for cascading calls to `DisposeAsync()`.</span></span> <span data-ttu-id="77d3f-128">Hermetyzuje typowe asynchroniczne operacje czyszczenia, gdy Podklasa dziedziczy klasę bazową, która jest implementacją <xref:System.IAsyncDisposable> .</span><span class="sxs-lookup"><span data-stu-id="77d3f-128">It encapsulates the common asynchronous cleanup operations when a subclass inherits a base class that is an implementation of <xref:System.IAsyncDisposable>.</span></span> <span data-ttu-id="77d3f-129">`DisposeAsyncCore()`Metoda polega na `virtual` tym, że klasy pochodne mogą definiować dodatkowe czyszczenie w ich zastąpień.</span><span class="sxs-lookup"><span data-stu-id="77d3f-129">The `DisposeAsyncCore()` method is `virtual` so that derived classes can define additional cleanup in their overrides.</span></span>

> [!TIP]
> <span data-ttu-id="77d3f-130">Jeśli implementacja programu <xref:System.IAsyncDisposable> ma wartość `sealed` , `DisposeAsyncCore()` Metoda nie jest wymagana, a oczyszczanie asynchroniczne można wykonać bezpośrednio w <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> metodzie.</span><span class="sxs-lookup"><span data-stu-id="77d3f-130">If an implementation of <xref:System.IAsyncDisposable> is `sealed`, the `DisposeAsyncCore()` method is not needed, and the asynchronous cleanup can be performed directly in the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method.</span></span>

## <a name="implement-the-async-dispose-pattern"></a><span data-ttu-id="77d3f-131">Implementowanie wzorca usuwania asynchronicznego</span><span class="sxs-lookup"><span data-stu-id="77d3f-131">Implement the async dispose pattern</span></span>

<span data-ttu-id="77d3f-132">Wszystkie niezapieczętowane klasy należy traktować jako potencjalną klasę bazową, ponieważ mogą one być dziedziczone.</span><span class="sxs-lookup"><span data-stu-id="77d3f-132">All non-sealed classes should be considered a potential base class, because they could be inherited.</span></span> <span data-ttu-id="77d3f-133">W przypadku zaimplementowania wzorca usuwania asynchronicznego dla dowolnej potencjalnej klasy podstawowej należy podać `protected virtual ValueTask DisposeAsyncCore()` metodę.</span><span class="sxs-lookup"><span data-stu-id="77d3f-133">If you implement the async dispose pattern for any potential base class, you must provide the `protected virtual ValueTask DisposeAsyncCore()` method.</span></span> <span data-ttu-id="77d3f-134">Oto Przykładowa implementacja asynchronicznego wzorca Dispose, który używa <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="77d3f-134">Here is an example implementation of the async dispose pattern that uses a <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

<span data-ttu-id="77d3f-135">Poprzedni przykład używa <xref:System.Text.Json.Utf8JsonWriter> .</span><span class="sxs-lookup"><span data-stu-id="77d3f-135">The preceding example uses the <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="77d3f-136">Aby uzyskać więcej informacji o `System.Text.Json` programie, zobacz [Jak przeprowadzić migrację z Newtonsoft.Js, aby System.Text.Js](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="77d3f-136">For more information about `System.Text.Json`, see [How to migrate from Newtonsoft.Json to System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

## <a name="using-async-disposable"></a><span data-ttu-id="77d3f-137">Korzystanie z asynchronicznej operacji jednorazowej</span><span class="sxs-lookup"><span data-stu-id="77d3f-137">Using async disposable</span></span>

<span data-ttu-id="77d3f-138">Aby prawidłowo korzystać z obiektu, który implementuje <xref:System.IAsyncDisposable> interfejs, należy użyć słów kluczowych [await](../../csharp/language-reference/operators/await.md)i [using](../../csharp/language-reference/keywords/using-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="77d3f-138">To properly consume an object that implements the <xref:System.IAsyncDisposable> interface, you use the [await](../../csharp/language-reference/operators/await.md), and [using](../../csharp/language-reference/keywords/using-statement.md) keywords together.</span></span> <span data-ttu-id="77d3f-139">Rozważmy następujący przykład, w którym `ExampleAsyncDisposable` tworzona jest instancja klasy, a następnie zawinięte w `await using` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="77d3f-139">Consider the following example, where the `ExampleAsyncDisposable` class is instantiated and then wrapped in an `await using` statement.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> <span data-ttu-id="77d3f-140">Użyj <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> metody rozszerzenia <xref:System.IAsyncDisposable> interfejsu, aby skonfigurować sposób przyprowadzenia zadania do jego oryginalnego kontekstu lub harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="77d3f-140">Use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> extension method of the <xref:System.IAsyncDisposable> interface to configure how the continuation of the task is marshalled on its original context or scheduler.</span></span> <span data-ttu-id="77d3f-141">Aby uzyskać więcej informacji na temat `ConfigureAwait` , zobacz temat [ConfigureAwait — często zadawane pytania](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span><span class="sxs-lookup"><span data-stu-id="77d3f-141">For more information on `ConfigureAwait`, see [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span></span>

<span data-ttu-id="77d3f-142">W sytuacjach, gdy użycie `ConfigureAwait` nie jest wymagane, `await using` instrukcja może być uproszczona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="77d3f-142">For situations where the usage of `ConfigureAwait` is not needed, the `await using` statement could be simplified as follows:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

<span data-ttu-id="77d3f-143">Ponadto można napisać, aby użyć niejawnego zakresu [deklaracji using](../../csharp/whats-new/csharp-8.md#using-declarations).</span><span class="sxs-lookup"><span data-stu-id="77d3f-143">Furthermore, it could be written to use the implicit scoping of a [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations).</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a><span data-ttu-id="77d3f-144">Stos użycia</span><span class="sxs-lookup"><span data-stu-id="77d3f-144">Stacked usings</span></span>

<span data-ttu-id="77d3f-145">W sytuacjach, gdy tworzysz i używasz wielu obiektów, które implementują <xref:System.IAsyncDisposable> , możliwe jest, aby `using` instrukcje stosujące w warunkach errant mogły uniemożliwić wywoływanie <xref:System.IAsyncDisposable.DisposeAsync> .</span><span class="sxs-lookup"><span data-stu-id="77d3f-145">In situations where you create and use multiple objects that implement <xref:System.IAsyncDisposable>, it's possible that stacking `using` statements in errant conditions could prevent calls to <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="77d3f-146">Aby zapobiec potencjalnym problemom, należy unikać tworzenia stosów, a zamiast tego postępować zgodnie z poniższym przykładowym wzorcem:</span><span class="sxs-lookup"><span data-stu-id="77d3f-146">In order to help prevent potential concern, you should avoid stacking, and instead follow this example pattern:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a><span data-ttu-id="77d3f-147">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="77d3f-147">See also</span></span>

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
