---
description: Dokumentacja Async-C#
title: Dokumentacja Async-C#
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 5a70389c9c423300fad03123cfc4738dfe10e481
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118523"
---
# <a name="async-c-reference"></a>async (odwołanie w C#)

Użyj `async` modyfikatora, aby określić, że metoda, [wyrażenie lambda](../operators/lambda-expressions.md)lub [Metoda anonimowa](../operators/delegate-operator.md) jest asynchroniczna. Jeśli używasz tego modyfikatora w metodzie lub wyrażeniu, jest on nazywany *metodą Async*. W poniższym przykładzie zdefiniowano metodę asynchroniczną o nazwie `ExampleMethodAsync` :

```csharp
public async Task<int> ExampleMethodAsync()
{
    //...
}
```

Jeśli dopiero zaczynasz programowanie asynchroniczne lub nie wiesz, w jaki sposób Metoda async używa [ `await` operatora](../operators/await.md) , aby potencjalnie długo pracować bez blokowania wątku wywołującego, zapoznaj się z tematem wprowadzenie do [programowania asynchronicznego przy użyciu Async i await](../../programming-guide/concepts/async/index.md). Poniższy kod znajduje się w metodzie asynchronicznej i wywołuje <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> metodę:

```csharp
string contents = await httpClient.GetStringAsync(requestUrl);
```

Metoda async jest uruchamiana synchronicznie do momentu, aż osiągnie swoje pierwsze `await` wyrażenie, w którym momencie Metoda jest wstrzymana do momentu ukończenia zadania. W międzyczasie sterowanie jest przekazywane do obiektu wywołującego metody, tak jak pokazano w przykładzie w następnej sekcji.

Jeśli metoda `async` modyfikowana przez słowo kluczowe nie zawiera `await` wyrażenia lub instrukcji, metoda jest wykonywana synchronicznie. Ostrzeżenie kompilatora ostrzega użytkownika o wszelkich metodach asynchronicznych, które nie zawierają `await` instrukcji, ponieważ taka sytuacja może wskazywać na błąd. Zobacz [Ostrzeżenie kompilatora (poziom 1) CS4014](../compiler-messages/cs4014.md).

 `async`Słowo kluczowe jest kontekstowe, ponieważ jest słowem kluczowym tylko wtedy, gdy modyfikuje metodę, wyrażenie lambda lub metodę anonimową. W innych kontekstach jest interpretowane jako identyfikator.

## <a name="example"></a>Przykład
Poniższy przykład pokazuje strukturę i przepływ kontroli między obsługą zdarzeń asynchronicznych, `StartButton_Click` i metodę asynchroniczną `ExampleMethodAsync` . Wynikiem metody asynchronicznej jest liczba znaków strony sieci Web. Kod jest odpowiedni dla aplikacji Windows Presentation Foundation (WPF) lub aplikacji ze sklepu Windows, którą tworzysz w programie Visual Studio; Zobacz komentarze do kodu dotyczące konfigurowania aplikacji.

Ten kod można uruchomić w programie Visual Studio jako aplikacja Windows Presentation Foundation (WPF) lub aplikacja ze sklepu Windows. Potrzebujesz formantu Button o nazwie `StartButton` i kontrolki TextBox o nazwie `ResultsTextBox` . Pamiętaj, aby ustawić nazwy i obsługę, tak aby wyglądały następująco:

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"
        Click="StartButton_Click" Name="StartButton"/>
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>
```

Aby uruchomić kod jako aplikację WPF:

- Wklej ten kod do `MainWindow` klasy w MainWindow.XAML.cs.
- Dodaj odwołanie do systemu .NET. http.
- Dodaj `using` dyrektywę dla systemu .NET. http.

Aby uruchomić kod jako aplikację ze sklepu Windows:

- Wklej ten kod do `MainPage` klasy w MainPage.XAML.cs.
- Dodaj dyrektywy using dla systemu .NET. http i system. Threading. Tasks.

[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]

> [!IMPORTANT]
> Aby uzyskać więcej informacji o zadaniach i kodzie, który jest wykonywany podczas oczekiwania na zadanie, zobacz [programowanie asynchroniczne z Async i await](../../programming-guide/concepts/async/index.md). Aby zapoznać się z pełnymi przykładami konsoli, które używają podobnych elementów, zobacz [Przetwarzanie asynchronicznych zadań po ich zakończeniu (C#)](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).

## <a name="return-types"></a>Typy zwracane
Metoda asynchroniczna może mieć następujące zwracane typy:

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- [typ void](../builtin-types/void.md). `async void` metody są generalnie odradzane dla kodu innego niż programy obsługi zdarzeń, ponieważ obiekty wywołujące nie mogą `await` być tymi metodami i muszą implementować inny mechanizm, aby zgłosić pomyślne zakończenie lub błędy.
- Począwszy od języka C# 7,0, dowolnego typu, który ma dostępną `GetAwaiter` metodę. `System.Threading.Tasks.ValueTask<TResult>`Typ to taka implementacja. Jest on dostępny przez dodanie pakietu NuGet `System.Threading.Tasks.Extensions` .

Metoda async nie może deklarować żadnych parametrów [in](./in-parameter-modifier.md), [ref](./ref.md) ani [out](./out-parameter-modifier.md) ani nie może mieć [wartości zwracanej przez odwołanie](../../programming-guide/classes-and-structs/ref-returns.md), ale może wywoływać metody, które mają takie parametry.

Należy określić `Task<TResult>` jako zwracany typ metody asynchronicznej, jeśli instrukcja [Return](./return.md) metody określa argument operacji typu `TResult` . Należy użyć, `Task` Jeśli podczas kończenia metody nie zostanie zwrócona wartość znacząca. Oznacza to, że wywołanie metody zwraca `Task` , ale po `Task` zakończeniu, dowolne `await` wyrażenie, które oczekuje na `Task` wartości `void` .

`void`Typ zwracany jest używany głównie do definiowania programów obsługi zdarzeń, które wymagają tego typu zwracanego. Obiekt wywołujący `void` metodę asynchroniczną zwracającą wartość, której nie może oczekiwać i nie może przechwytywać wyjątków zgłaszanych przez metodę.

Począwszy od języka C# 7,0, zwracany jest inny typ, zazwyczaj typ wartości, który ma `GetAwaiter` metodę, aby zminimalizować alokacje pamięci w sekcjach o kluczowym znaczeniu dla wydajności.

Aby uzyskać więcej informacji i przykładów, zobacz [asynchroniczne typy zwracane](../../programming-guide/concepts/async/async-return-types.md).

## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [await](../operators/await.md)
- [Programowanie asynchroniczne przy użyciu elementów async i await](../../programming-guide/concepts/async/index.md)
- [Przetwarzanie zadań asynchronicznych po ich zakończeniu](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)
