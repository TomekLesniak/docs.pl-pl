---
title: Asynchroniczne typy zwracane (C#)
description: Dowiedz się więcej na temat typów zwracanych, które metody asynchroniczne mogą znajdować się w języku C# z przykładami kodu dla każdego typu i dodatkowych zasobów.
ms.date: 08/19/2020
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
ms.openlocfilehash: 71e560ed8ee0cae14da396e5ea2f3ab29611ebab
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811499"
---
# <a name="async-return-types-c"></a>Asynchroniczne typy zwracane (C#)

Metody asynchroniczne mogą mieć następujące typy zwracane:

- <xref:System.Threading.Tasks.Task>dla metody asynchronicznej, która wykonuje operację, ale nie zwraca żadnej wartości.
- <xref:System.Threading.Tasks.Task%601>dla metody asynchronicznej, która zwraca wartość.
- `void`dla programu obsługi zdarzeń.
- Począwszy od języka C# 7,0, dowolnego typu, który ma dostępną `GetAwaiter` metodę. Obiekt zwrócony przez `GetAwaiter` metodę musi implementować <xref:System.Runtime.CompilerServices.ICriticalNotifyCompletion?displayProperty=nameWithType> interfejs.
- Począwszy od języka C# 8,0, <xref:System.Collections.Generic.IAsyncEnumerable%601> dla metody asynchronicznej zwracającej *strumień asynchroniczny*.

Aby uzyskać więcej informacji na temat metod asynchronicznych, zobacz [programowanie asynchroniczne z Async i Await (C#)](./index.md).

Istnieje także kilka innych typów, które są specyficzne dla obciążeń systemu Windows:

- <xref:System.Windows.Threading.DispatcherOperation>w przypadku operacji asynchronicznych ograniczonych do systemu Windows.
- <xref:Windows.Foundation.IAsyncAction>w przypadku akcji asynchronicznych w platformy UWP, które nie zwracają wartości.
- <xref:Windows.Foundation.IAsyncActionWithProgress%601>w przypadku akcji asynchronicznych w platformy UWP, które zgłaszają postęp, ale nie zwracają wartości.
- <xref:Windows.Foundation.IAsyncOperation%601>dla operacji asynchronicznych w platformy UWP, które zwracają wartość.
- <xref:Windows.Foundation.IAsyncOperationWithProgress%602>w przypadku operacji asynchronicznych w platformy UWP, które raportują postęp i zwracają wartość.

## <a name="task-return-type"></a>Typ zwracany zadania

Metody asynchroniczne, które nie zawierają `return` instrukcji lub zawierające `return` instrukcję, która nie zwraca operandu, zwykle mają typ zwracany <xref:System.Threading.Tasks.Task> . Takie metody zwracają, `void` Jeśli są uruchamiane synchronicznie. Jeśli używasz <xref:System.Threading.Tasks.Task> typu zwracanego dla metody asynchronicznej, Metoda wywołująca może użyć operatora, `await` Aby zawiesić zakończenie obiektu wywołującego do momentu zakończenia wywołanej metody asynchronicznej.

W poniższym przykładzie `WaitAndApologizeAsync` Metoda nie zawiera `return` instrukcji, dlatego metoda zwraca <xref:System.Threading.Tasks.Task> obiekt. Zwracanie elementu `Task` umożliwia `WaitAndApologizeAsync` oczekiwanie. <xref:System.Threading.Tasks.Task>Typ nie zawiera właściwości, `Result` ponieważ nie ma wartości zwracanej.

:::code language="csharp" source="snippets/async-return-types/async-returns2.cs" id="TaskReturn":::

`WaitAndApologizeAsync` oczekuje się przy użyciu instrukcji Await zamiast wyrażenia await, podobnie jak instrukcja wywołująca synchronicznej metody zwracającej wartość void. W tym przypadku aplikacja operatora await nie tworzy wartości. Aby wyjaśnić warunki i wyrażenie, zapoznaj się z poniższą tabelą:

| Rodzaj oczekiwania | Przykład                                      | Typ                                   |
|------------|----------------------------------------------|----------------------------------------|
| Instrukcja  | `await SomeTaskMethodAsync()`                | <xref:System.Threading.Tasks.Task>     |
| Wyrażenie | `T result = await SomeTaskMethodAsync<T>();` | <xref:System.Threading.Tasks.Task%601> |

Możesz oddzielić wywołanie `WaitAndApologizeAsync` od aplikacji operatora await, jak pokazano w poniższym kodzie. Należy jednak pamiętać, że element `Task` nie ma `Result` właściwości i że żadna wartość nie jest generowana, gdy operator await jest stosowany do `Task` .

Poniższy kod oddziela wywoływanie `WaitAndApologizeAsync` metody od oczekiwania na zadanie, które zwraca metoda.

:::code language="csharp" source="snippets/async-return-types/async-returns2a.cs" id="AwaitTask":::

## <a name="tasktresult-return-type"></a>\<TResult\>Typ zwracany zadania

<xref:System.Threading.Tasks.Task%601>Zwracany typ jest używany dla metody asynchronicznej, która zawiera instrukcję [Return](../../../language-reference/keywords/return.md) , w której operand jest `TResult` .

W poniższym przykładzie `GetLeisureHoursAsync` Metoda zawiera `return` instrukcję, która zwraca liczbę całkowitą. W związku z tym Deklaracja metody musi określać zwracany typ `Task<int>` . <xref:System.Threading.Tasks.Task.FromResult%2A>Metoda async jest symbolem zastępczym dla operacji, która zwraca <xref:System.DateTime.DayOfWeek> .

:::code language="csharp" source="snippets/async-return-types/async-returns1.cs" id="LeisureHours":::

Gdy `GetLeisureHoursAsync` jest wywoływana z w wyrażeniu await w `ShowTodaysInfo` metodzie, wyrażenie await Pobiera wartość całkowitą (wartość `leisureHours` ), która jest przechowywana w zadaniu zwróconym przez `GetLeisureHours` metodę. Aby uzyskać więcej informacji na temat wyrażeń await, zobacz [await](../../../language-reference/operators/await.md).

Można lepiej zrozumieć, jak `await` Pobiera wynik z a `Task<T>` przez oddzielenie wywołania `GetLeisureHoursAsync` z aplikacji `await` , jak pokazano w poniższym kodzie. Wywołanie metody `GetLeisureHoursAsync` , która nie jest bezpośrednio oczekiwane, zwraca `Task<int>` , jak oczekiwano od deklaracji metody. Zadanie jest przypisane do `getLeisureHoursTask` zmiennej w przykładzie. Ponieważ `getLeisureHoursTask` jest <xref:System.Threading.Tasks.Task%601> , zawiera <xref:System.Threading.Tasks.Task%601.Result> Właściwość typu `TResult` . W tym przypadku `TResult` reprezentuje typ Integer. Gdy `await` jest stosowany do `getLeisureHoursTask` , wyrażenie await oblicza zawartość <xref:System.Threading.Tasks.Task%601.Result%2A> właściwości `getLeisureHoursTask` . Wartość jest przypisana do `ret` zmiennej.

> [!IMPORTANT]
> <xref:System.Threading.Tasks.Task%601.Result%2A>Właściwość jest właściwością blokującą. Jeśli spróbujesz uzyskać dostęp do niego przed ukończeniem zadania, wątek, który jest obecnie aktywny, jest blokowany do momentu zakończenia zadania, a wartość jest dostępna. W większości przypadków należy uzyskać dostęp do wartości przy użyciu `await` zamiast bezpośrednio uzyskać dostęp do właściwości.
>
> W poprzednim przykładzie pobrano wartość <xref:System.Threading.Tasks.Task%601.Result%2A> właściwości w celu zablokowania głównego wątku, tak aby `Main` Metoda mogła wydrukować `message` do konsoli programu przed zainstalowaniem aplikacji.

:::code language="csharp" source="snippets/async-return-types/async-returns1a.cs" id="StoreTask":::

## <a name="void-return-type"></a>Typ zwracany void

`void`Typ zwracany jest używany w asynchronicznych obsłudze zdarzeń, które wymagają `void` typu zwracanego. W przypadku metod innych niż programy obsługi zdarzeń, które nie zwracają wartości, należy zwrócić <xref:System.Threading.Tasks.Task> zamiast tego, ponieważ Metoda async, która zwraca `void` nie można oczekiwać. Każdy obiekt wywołujący taką metodę musi kontynuować działanie bez oczekiwania na zakończenie wywołanej metody asynchronicznej. Obiekt wywołujący musi być niezależny od wszelkich wartości lub wyjątków generowanych przez metodę asynchroniczną.

Obiekt wywołujący metodę asynchroniczną zwracającą wartość void nie może przechwytywać wyjątków zgłoszonych z metody, a takie Nieobsłużone wyjątki mogą spowodować niepowodzenie działania aplikacji. Jeśli metoda zwracająca <xref:System.Threading.Tasks.Task> lub <xref:System.Threading.Tasks.Task%601> zgłasza wyjątek, wyjątek jest przechowywany w zwracanym zadaniu. Wyjątek jest zgłaszany ponownie po oczekiwaniu na zadanie. W związku z tym upewnij się, że jakakolwiek Metoda asynchroniczna, która może generować wyjątek, ma typ zwracany <xref:System.Threading.Tasks.Task> lub <xref:System.Threading.Tasks.Task%601> i że wywołania metody są oczekiwane.

Aby uzyskać więcej informacji o sposobie przechwytywania wyjątków w metodach asynchronicznych, zobacz sekcję [wyjątki w metodach asynchronicznych](../../../language-reference/keywords/try-catch.md#exceptions-in-async-methods) artykułu [try-catch](../../../language-reference/keywords/try-catch.md) .

W poniższym przykładzie pokazano zachowanie programu obsługi zdarzeń asynchronicznych. W przykładowym kodzie, procedura obsługi zdarzeń asynchronicznych musi pozwolić, aby główny wątek był znany po zakończeniu. Następnie wątek główny może poczekać na zakończenie obsługi zdarzeń asynchronicznych przed zamknięciem programu.

:::code language="csharp" source="snippets/async-return-types/async-returns3.cs":::

## <a name="generalized-async-return-types-and-valuetasktresult"></a>Uogólnione asynchroniczne typy zwracane i ValueTask\<TResult\>

Począwszy od języka C# 7,0, Metoda asynchroniczna może zwracać dowolny typ, który ma dostępną `GetAwaiter` metodę.

Ponieważ <xref:System.Threading.Tasks.Task> i <xref:System.Threading.Tasks.Task%601> są typami odwołań, alokacja pamięci w ścieżkach o krytycznym znaczeniu dla wydajności, szczególnie gdy przydziały występują w ścisłych pętlach, mogą mieć negatywny wpływ na wydajność. Obsługa uogólnionych typów zwracanych oznacza, że można zwrócić typ wartości lekkiej zamiast typu referencyjnego, aby uniknąć dodatkowych alokacji pamięci.

Platforma .NET udostępnia <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> strukturę jako lekkie implementacje ogólnej wartości zwracanego zadania. Aby użyć tego <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> typu, należy dodać `System.Threading.Tasks.Extensions` pakiet NuGet do projektu. Poniższy przykład używa struktury, <xref:System.Threading.Tasks.ValueTask%601> Aby pobrać wartość dwóch przerzutów z kością.

:::code language="csharp" source="snippets/async-return-types/async-valuetask.cs":::

## <a name="async-streams-with-iasyncenumerablet"></a>Strumienie asynchroniczne z IAsyncEnumerable\<T\>

Począwszy od języka C# 8,0, Metoda asynchroniczna może zwracać *strumień asynchroniczny*reprezentowany przez <xref:System.Collections.Generic.IAsyncEnumerable%601> . Strumień asynchroniczny umożliwia Wyliczenie elementów odczytanych ze strumienia, gdy elementy są generowane w fragmentach z powtarzalnymi wywołaniami asynchronicznymi. Poniższy przykład przedstawia metodę asynchroniczną generującą strumień asynchroniczny:

:::code language="csharp" source="snippets/async-return-types/AsyncStreams.cs" id="GenerateAsyncStream":::

Poprzedni przykład odczytuje wiersze z ciągu asynchronicznie. Po odczytaniu każdego wiersza kod wylicza każdy wyraz w ciągu. Obiekty wywołujące spowodują Wyliczenie każdego wyrazu przy użyciu `await foreach` instrukcji. Metoda oczekuje, gdy musi asynchronicznie odczytać następny wiersz z ciągu źródłowego.

## <a name="see-also"></a>Zobacz też

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Przetwarzaj zadania asynchroniczne po ich zakończeniu](start-multiple-async-tasks-and-process-them-as-they-complete.md)
- [Programowanie asynchroniczne z Async i Await (C#)](index.md)
- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
