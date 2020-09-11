---
title: Implementacja metody DisposeAsync
description: Dowiedz się, jak zaimplementować metody DisposeAsync i DisposeAsyncCore, aby przeprowadzić Oczyszczanie zasobów asynchronicznych.
author: IEvangelist
ms.author: dapine
ms.date: 09/10/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 88adf9e484baa0e65e2ff093b4649cf35b8c86dc
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022912"
---
# <a name="implement-a-disposeasync-method"></a>Implementacja metody DisposeAsync

<xref:System.IAsyncDisposable?displayProperty=nameWithType>Interfejs został wprowadzony jako część języka C# 8,0. Metodę należy zaimplementować <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> , gdy trzeba przeprowadzić Oczyszczanie zasobów, tak jak podczas [implementowania metody Dispose](implementing-dispose.md). Jedną z najważniejszych różnic jest jednak to, że ta implementacja umożliwia asynchroniczne czyszczenie operacji. <xref:System.IAsyncDisposable.DisposeAsync>Zwraca wartość <xref:System.Threading.Tasks.ValueTask> reprezentującą asynchroniczną operację Dispose.

Typowym scenariuszem jest implementowanie <xref:System.IAsyncDisposable> interfejsu, który klasy również implementują <xref:System.IDisposable> interfejs. Dobry wzorzec implementacji <xref:System.IAsyncDisposable> interfejsu jest przygotowany do synchronicznej lub asynchronicznej operacji Dispose. Wszystkie wskazówki dotyczące wdrażania wzorca Dispose dotyczą również implementacji asynchronicznej. W tym artykule założono, że wiesz już, jak [zaimplementować metodę Dispose](implementing-dispose.md).

## <a name="disposeasync-and-disposeasynccore"></a>DisposeAsync () i DisposeAsyncCore ()

<xref:System.IAsyncDisposable>Interfejs deklaruje pojedynczą metodę bez parametrów, <xref:System.IAsyncDisposable.DisposeAsync> . Każda Klasa Niezapieczętowana powinna mieć dodatkową `DisposeAsyncCore()` metodę, która również zwraca wartość <xref:System.Threading.Tasks.ValueTask> .

- `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> Implementacja, która nie ma parametrów.
- `protected virtual ValueTask DisposeAsyncCore()`Metoda, której sygnatura:

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a>DisposeAsync () — Metoda

`public` `DisposeAsync()` Metoda bez parametrów jest wywoływana niejawnie w `await using` instrukcji i jej celem jest zwolnienie niezarządzanych zasobów, wykonanie ogólnego czyszczenia i wskazanie, że finalizator, jeśli taki istnieje, nie musi być uruchomiony. Zwalnianie pamięci skojarzonej z zarządzanym obiektem jest zawsze domeną [modułu wyrzucania elementów bezużytecznych](index.md). Z tego powodu ma standardową implementację:

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
> Podstawowa różnica w asynchronicznym wzorcu usuwania w porównaniu do wzorca Dispose polega na tym, że wywołanie z <xref:System.IAsyncDisposable.DisposeAsync> `Dispose(bool)` metody przeciążenia jest podawane `false` jako argument. Podczas implementowania <xref:System.IDisposable.Dispose?displayProperty=nameWithType> metody, jednak `true` zamiast tego jest przesyłane. Dzięki temu można zapewnić równoważność funkcjonalną z synchronicznym wzorcem usuwania, a dodatkowo zapewnić, że ścieżki kodu finalizatora nadal są wywoływane. Innymi słowy, `DisposeAsyncCore()` Metoda usunie zarządzane zasoby asynchronicznie, więc nie ma potrzeby ich synchronicznego usuwania. W związku `Dispose(false)` z tym zamiast `Dispose(true)` .

### <a name="the-disposeasynccore-method"></a>DisposeAsyncCore () — Metoda

`DisposeAsyncCore()`Metoda jest przeznaczona do przeprowadzania asynchronicznego oczyszczania zarządzanych zasobów lub łączenia kaskadowego z `DisposeAsync()` . Hermetyzuje typowe asynchroniczne operacje czyszczenia, gdy Podklasa dziedziczy klasę bazową, która jest implementacją <xref:System.IAsyncDisposable> . `DisposeAsyncCore()`Metoda polega na `virtual` tym, że klasy pochodne mogą definiować dodatkowe czyszczenie w ich zastąpień.

> [!TIP]
> Jeśli implementacja programu <xref:System.IAsyncDisposable> ma wartość `sealed` , `DisposeAsyncCore()` Metoda nie jest wymagana, a oczyszczanie asynchroniczne można wykonać bezpośrednio w <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> metodzie.

## <a name="implement-the-async-dispose-pattern"></a>Implementowanie wzorca usuwania asynchronicznego

Wszystkie niezapieczętowane klasy należy traktować jako potencjalną klasę bazową, ponieważ mogą one być dziedziczone. W przypadku zaimplementowania wzorca usuwania asynchronicznego dla dowolnej potencjalnej klasy podstawowej należy podać `protected virtual ValueTask DisposeAsyncCore()` metodę. Oto Przykładowa implementacja asynchronicznego wzorca Dispose, który używa <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> .

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

Poprzedni przykład używa <xref:System.Text.Json.Utf8JsonWriter> . Aby uzyskać więcej informacji o `System.Text.Json` programie, zobacz [Jak przeprowadzić migrację z Newtonsoft.Js, aby System.Text.Js](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).

## <a name="implement-both-dispose-and-async-dispose-patterns"></a>Implementuj wzorce usuwania operacji Dispose i Async

Może być konieczne zaimplementowanie obu <xref:System.IDisposable> <xref:System.IAsyncDisposable> interfejsów i, szczególnie gdy zakres klasy zawiera wystąpienia tych implementacji. Dzięki temu można prawidłowo kaskadowo wyczyścić wywołania. Oto przykładowa Klasa implementująca oba interfejsy i demonstrująca odpowiednie wskazówki dotyczące czyszczenia.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/dispose-and-disposeasync.cs":::

<xref:System.IDisposable.Dispose?displayProperty=nameWithType> <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> Implementacje i są prostym kodem niezwykłym. `Dispose(bool)`Metody i `DisposeAsyncCore()` zaczynają się od sprawdzenia `_disposed` , czy jest `true` , i zostaną uruchomione tylko wtedy, gdy `false` jest to.

W `Dispose(bool)` metodzie przeciążenia <xref:System.IDisposable> wystąpienie jest warunkowo usuwane, jeśli nie jest `null` . <xref:System.IAsyncDisposable>Wystąpienie jest rzutowane jako <xref:System.IDisposable> , a jeśli również nie zostało także `null` usunięte. Oba wystąpienia są następnie przypisywane do `null` .

Przy użyciu `DisposeAsyncCore()` metody jest stosowane takie samo podejście logiczne. Jeśli <xref:System.IAsyncDisposable> wystąpienie nie jest `null` , jego wywołanie `DisposeAsync().ConfigureAwait(false)` jest oczekiwane. Jeśli <xref:System.IDisposable> wystąpienie jest również implementacją programu <xref:System.IAsyncDisposable> , jest również usuwane asynchronicznie. Oba wystąpienia są następnie przypisywane do `null` .

## <a name="using-async-disposable"></a>Korzystanie z asynchronicznej operacji jednorazowej

Aby prawidłowo korzystać z obiektu, który implementuje <xref:System.IAsyncDisposable> interfejs, należy użyć słów kluczowych [await](../../csharp/language-reference/operators/await.md)i [using](../../csharp/language-reference/keywords/using-statement.md) . Rozważmy następujący przykład, w którym `ExampleAsyncDisposable` tworzona jest instancja klasy, a następnie zawinięte w `await using` instrukcji.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> Użyj <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> metody rozszerzenia <xref:System.IAsyncDisposable> interfejsu, aby skonfigurować sposób przyprowadzenia zadania do jego oryginalnego kontekstu lub harmonogramu. Aby uzyskać więcej informacji na temat `ConfigureAwait` , zobacz temat [ConfigureAwait — często zadawane pytania](https://devblogs.microsoft.com/dotnet/configureawait-faq/).

W sytuacjach, gdy użycie `ConfigureAwait` nie jest wymagane, `await using` instrukcja może być uproszczona w następujący sposób:

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

Ponadto można napisać, aby użyć niejawnego zakresu [deklaracji using](../../csharp/whats-new/csharp-8.md#using-declarations).

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a>Stos użycia

W sytuacjach, gdy tworzysz i używasz wielu obiektów, które implementują <xref:System.IAsyncDisposable> , możliwe jest, aby `using` instrukcje stosujące w warunkach errant mogły uniemożliwić wywoływanie <xref:System.IAsyncDisposable.DisposeAsync> . Aby zapobiec potencjalnym problemom, należy unikać tworzenia stosów, a zamiast tego postępować zgodnie z poniższym przykładowym wzorcem:

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a>Zobacz także

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
