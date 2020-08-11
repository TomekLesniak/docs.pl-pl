---
title: Tworzenie łańcuchów zadań przy użyciu zadań kontynuacji
description: Dowiedz się więcej o zadaniach łańcucha przy użyciu zadań kontynuacji w programie .NET. Zadanie kontynuacji to asynchroniczne zadanie, które jest wywoływane przez inne zadanie.
ms.date: 07/20/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, continuations
ms.assetid: 0b45e9a2-de28-46ce-8212-1817280ed42d
ms.openlocfilehash: d42d244e644bf3ee1f45b25a71d60bbb2ef8e590
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063838"
---
# <a name="chaining-tasks-using-continuation-tasks"></a>Tworzenie łańcuchów zadań przy użyciu zadań kontynuacji

W programowaniu asynchronicznym, jest to typowe dla jednej operacji asynchronicznej po zakończeniu, aby wywołać drugą operację. Kontynuacje umożliwiają decedent operacji na korzystanie z wyników pierwszej operacji. Tradycyjnie, kontynuacje zostały wykonane przy użyciu metod wywołania zwrotnego. W bibliotece zadań równoległych te same funkcje są udostępniane przez _zadania kontynuacji_. Zadanie kontynuacji (znane również jako kontynuacja) to asynchroniczne zadanie, które jest wywoływane przez inne zadanie, znane jako _poprzedzające_, po zakończeniu poprzedzającego.

Kontynuacje są stosunkowo łatwe w użyciu, ale są jednak zaawansowane i elastyczne. Możesz na przykład:

- Przekaż dane z Antecedent do kontynuacji.
- Określ dokładne warunki, w których kontynuacja zostanie wywołana lub nie zostanie wywołana.
- Anuluj kontynuację albo przed jej rozpoczęciem albo w trakcie jej działania.
- Podaj wskazówki dotyczące sposobu, w jaki kontynuacja powinna zostać zaplanowana.
- Wywoływanie wielu kontynuacji z tego samego poprzedzającego.
- Wywołanie jednej kontynuacji po ukończeniu wszystkich lub dowolnego jednego z wielu poprzedników.
- Łańcuch uzupełnia jeden po drugim do dowolnej dowolnej długości.
- Użyj kontynuacji, aby obsłużyć wyjątki generowane przez poprzedzające.

## <a name="about-continuations"></a>Informacje o kontynuacji

Kontynuacja to zadanie, które jest tworzone w <xref:System.Threading.Tasks.TaskStatus.WaitingForActivation> stanie. Jest uaktywniana automatycznie po ukończeniu zadania lub zadania poprzedzającego. Wywołanie <xref:System.Threading.Tasks.Task.Start%2A?displayProperty=nameWithType> kontynuacji w kodzie użytkownika zgłasza <xref:System.InvalidOperationException?displayProperty=nameWithType> wyjątek.

Kontynuacja jest sama <xref:System.Threading.Tasks.Task> i nie blokuje wątku, w którym jest uruchomiona. Wywołaj <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> metodę, aby zablokować do momentu zakończenia zadania kontynuacji.

## <a name="create-a-continuation-for-a-single-antecedent"></a>Tworzenie kontynuacji dla pojedynczego poprzedzającego

Należy utworzyć kontynuację, która jest wykonywana po zakończeniu poprzedzającego, wywołując <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> metodę. W poniższym przykładzie pokazano wzorzec podstawowy (dla jasności, obsługa wyjątków jest pomijana). Wykonuje zadanie poprzedzające, `taskA` która zwraca <xref:System.DayOfWeek> obiekt, który wskazuje nazwę bieżącego dnia tygodnia. Po ukończeniu poprzedzającego, zadanie kontynuacji, `continuation` ,,, jest przenoszone poprzedzające i wyświetla ciąg, który zawiera jego wynik.

> [!NOTE]
> Przykłady w języku C# w tym artykule używają `async` modyfikatora `Main` metody. Ta funkcja jest dostępna w języku C# 7,1 i nowszych. Poprzednie wersje generują [`CS5001`](../../csharp/misc/cs5001.md) podczas kompilowania tego przykładowego kodu. Należy ustawić wersję językową na C# 7,1 lub nowszą. Możesz dowiedzieć się, jak skonfigurować wersję języka w artykule dotyczącym [konfigurowania wersji językowej](../../csharp/language-reference/configure-language-version.md).

:::code language="csharp" source="snippets/cs/simple1.cs":::

[!code-vb[TPL_Continuations#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/simple1.vb#1)]

## <a name="create-a-continuation-for-multiple-antecedents"></a>Tworzenie kontynuacji dla wielu poprzedzających

Możesz również utworzyć kontynuację, która będzie uruchamiana po zakończeniu dowolnej lub wszystkich grup zadań. Aby wykonać kontynuację po zakończeniu wszystkich zadań poprzedzających, należy wywołać metodę static ( `Shared` in Visual Basic) <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> lub <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> metodę wystąpienia. Aby wykonać kontynuację, gdy którekolwiek z zadań poprzedzających zostało zakończone, należy wywołać metodę static ( `Shared` in Visual Basic) <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> lub metodę wystąpienia <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A?displayProperty=nameWithType> .

Wywołania <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> i <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> przeciążenia nie blokują wątku wywołującego. Jednak zazwyczaj wywołują wszystkie metody, ale <xref:System.Threading.Tasks.Task.WhenAll%28System.Collections.Generic.IEnumerable%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> i, <xref:System.Threading.Tasks.Task.WhenAll%28System.Threading.Tasks.Task%5B%5D%29?displayProperty=nameWithType> Aby pobrać zwracaną <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> Właściwość, która blokuje wątek wywołujący.

Poniższy przykład wywołuje <xref:System.Threading.Tasks.Task.WhenAll%28System.Collections.Generic.IEnumerable%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> metodę w celu utworzenia zadania kontynuacji, które odzwierciedla wyniki jego 10 poprzedzających zadań. Każde zadanie poprzedzające ma wartość indeksu, która należy do zakresu od 1 do 10. Jeśli poprzedzające pomyślne zakończenie (ich <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> Właściwość to <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType> ), <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> Właściwość kontynuacji jest tablicą <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> wartości zwracanych przez każde poprzedzające. Przykład dodaje je do obliczenia sumy kwadratów dla wszystkich liczb z zakresu od 1 do 10.

:::code language="csharp" source="snippets/cs/whenall1.cs":::

[!code-vb[TPL_Continuations#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/whenall1.vb#5)]

## <a name="continuation-options"></a>Opcje kontynuacji

Podczas tworzenia kontynuacji pojedynczego zadania można użyć <xref:System.Threading.Tasks.Task.ContinueWith%2A> przeciążenia, które przyjmuje <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> wartość wyliczenia, aby określić warunki, pod którymi rozpocznie się kontynuacja. Na przykład można określić, że kontynuacja ma być uruchamiana tylko wtedy, gdy poprzednik zostanie zakończony pomyślnie, lub tylko wtedy, gdy zostanie zakończony w stanie awarii. Jeśli warunek nie ma wartości true, gdy poprzedzający jest gotowy do wywołania kontynuacji, kontynuacja przechodzi bezpośrednio do <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> stanu, a następnie nie można jej uruchomić.

Szereg metod kontynuacji wielu zadań, takich jak przeciążenia <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> metody, również zawierają <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> parametr. Jednak tylko podzbiór wszystkich <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> elementów członkowskich wyliczenia jest prawidłowy. Można określić <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> wartości, które mają odpowiedniki w <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=nameWithType> wyliczeniu, takie jak <xref:System.Threading.Tasks.TaskContinuationOptions.AttachedToParent?displayProperty=nameWithType> , <xref:System.Threading.Tasks.TaskContinuationOptions.LongRunning?displayProperty=nameWithType> , i <xref:System.Threading.Tasks.TaskContinuationOptions.PreferFairness?displayProperty=nameWithType> . W przypadku określenia dowolnej `NotOn` `OnlyOn` opcji lub z kontynuacją wielozadania <xref:System.ArgumentOutOfRangeException> zostanie zgłoszony wyjątek w czasie wykonywania.

Więcej informacji o opcjach kontynuacji zadania znajduje się w <xref:System.Threading.Tasks.TaskContinuationOptions> temacie.

## <a name="pass-data-to-a-continuation"></a>Przekazywanie danych do kontynuacji

<xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>Metoda przekazuje odwołanie do delegata użytkownika kontynuacji jako argument. Jeśli antecedent jest <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> obiektem, a zadanie zostało uruchomione, dopóki nie zostało ukończone, kontynuacja może uzyskać dostęp do <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> właściwości zadania.

<xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>Właściwość blokuje się do momentu ukończenia zadania. Jeśli jednak zadanie zostało anulowane lub wystąpił błąd, próba uzyskania dostępu do <xref:System.Threading.Tasks.Task%601.Result%2A> właściwości zgłasza <xref:System.AggregateException> wyjątek. Można uniknąć tego problemu, korzystając z <xref:System.Threading.Tasks.TaskContinuationOptions.OnlyOnRanToCompletion> opcji, jak pokazano w poniższym przykładzie.

:::code language="csharp" source="snippets/cs/result1.cs":::

[!code-vb[TPL_Continuations#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/result1.vb#2)]

Jeśli chcesz, aby kontynuacja była uruchamiana, nawet jeśli poprzednik nie został uruchomiony w celu pomyślnego ukończenia, należy zabezpieczyć wyjątek. Jednym z metod jest przetestowanie <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> Właściwości poprzedzającego i próba uzyskania dostępu do właściwości tylko <xref:System.Threading.Tasks.Task%601.Result%2A> wtedy, gdy stanem jest nie <xref:System.Threading.Tasks.TaskStatus.Faulted> lub <xref:System.Threading.Tasks.TaskStatus.Canceled> . Można również przeanalizować <xref:System.Threading.Tasks.Task.Exception%2A> Właściwość poprzedzającą. Aby uzyskać więcej informacji, zobacz [Obsługa wyjątków](exception-handling-task-parallel-library.md). Poniższy przykład modyfikuje poprzedni przykład, aby uzyskać dostęp do <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> Właściwości antecedent tylko wtedy, gdy jego stan to <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType> .

:::code language="csharp" source="snippets/cs/result2.cs":::

[!code-vb[TPL_Continuations#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/result2.vb#7)]

## <a name="cancel-a-continuation"></a>Anuluj kontynuację

<xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType>Właściwość kontynuacji jest ustawiana na <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> w następujących sytuacjach:

- Zgłasza <xref:System.OperationCanceledException> wyjątek w odpowiedzi na żądanie anulowania. Podobnie jak w przypadku każdego zadania, jeśli wyjątek zawiera ten sam token, który został przekazano do kontynuacji, jest traktowany jako potwierdzenie anulowania spółdzielni.
- Kontynuacja jest przenoszona, <xref:System.Threading.CancellationToken?displayProperty=nameWithType> której <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> Właściwość jest `true` . W takim przypadku kontynuacja nie zostanie uruchomiona i przechodzi do <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> stanu.
- Kontynuacja nigdy nie działa, ponieważ warunek ustawiony przez jego <xref:System.Threading.Tasks.TaskContinuationOptions> argument nie został spełniony. Na przykład jeśli poprzednika przejdzie do <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> stanu, jego kontynuacja, która została przeniesiona, <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnFaulted?displayProperty=nameWithType> nie zostanie uruchomiona, ale przejdzie do <xref:System.Threading.Tasks.TaskStatus.Canceled> stanu.

Jeśli zadanie i jego kontynuacja reprezentują dwie części tej samej operacji logicznej, można przekazać ten sam token anulowania do obu zadań, jak pokazano w poniższym przykładzie. Składa się z poprzedzającego, który generuje listę liczb całkowitych, które są podzielne przez 33, które przechodzi do kontynuacji. Kontynuacja z kolei wyświetla listę. Zarówno poprzednik, jak i kontynuacja są regularnie wstrzymywane w przypadku losowych interwałów. Ponadto <xref:System.Threading.Timer?displayProperty=nameWithType> obiekt jest używany do wykonywania `Elapsed` metody po pięciu sekundowym przedziale czasu. Ten przykład wywołuje <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> metodę, która powoduje wywoływanie metody przez aktualnie wykonywane zadanie <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A?displayProperty=nameWithType> . Określa, czy <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> Metoda jest wywoływana, gdy jest wykonywane poprzedzające lub kontynuacja, zależy od czasu trwania losowo generowanych przerw. Jeśli poprzednik zostanie anulowany, kontynuacja nie zostanie uruchomiona. Jeśli poprzedzające nie zostało anulowane, token nadal może być używany do anulowania kontynuacji.

:::code language="csharp" source="snippets/cs/cancellation1.cs":::

[!code-vb[TPL_Continuations#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/cancellation1.vb#3)]

Można również uniemożliwić kontynuowanie wykonywania, jeśli jego poprzednik zostanie anulowany bez podawania kontynuacji tokenu anulowania przez określenie <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnCanceled?displayProperty=nameWithType> opcji podczas tworzenia kontynuacji. Poniżej przedstawiono prosty przykład.

:::code language="csharp" source="snippets/cs/cancellation2.cs":::

[!code-vb[TPL_Continuations#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/cancellation2.vb#8)]

Gdy kontynuacja przechodzi do <xref:System.Threading.Tasks.TaskStatus.Canceled> stanu, może to mieć wpływ na kontynuacje, które są następujące, w zależności od <xref:System.Threading.Tasks.TaskContinuationOptions> tego, który został określony dla tych kontynuacji.

Kontynuacje, które zostały zlikwidowane, nie zostaną uruchomione.

## <a name="continuations-and-child-tasks"></a>Kontynuacje i zadania podrzędne

Kontynuacja nie działa do momentu ukończenia poprzedzających i wszystkich dołączonych zadań podrzędnych. Kontynuacja nie czeka na zakończenie odłączonych zadań podrzędnych. Poniższe dwa przykłady ilustrują zadania podrzędne, które są dołączone do i odłączane od poprzedzającego, który tworzy kontynuację. W poniższym przykładzie kontynuacja jest uruchamiana tylko po wykonaniu wszystkich zadań podrzędnych, a wielokrotne uruchomienie tego przykładu da identyczne dane wyjściowe. W przykładzie jest uruchamiany poprzedzający przez wywołanie <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> metody, ponieważ domyślnie <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> Metoda tworzy zadanie nadrzędne, którego domyślna opcja tworzenia zadań to <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> .

:::code language="csharp" source="snippets/cs/attached1.cs":::

[!code-vb[TPL_Continuations#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/attached1.vb#9)]

Jeśli zadania podrzędne są odłączone od poprzedzającego, jednak kontynuacja jest uruchamiana zaraz po zakończonym poprzedniku, niezależnie od stanu zadań podrzędnych. W związku z tym wiele przebiegów poniższego przykładu może generować zmienne dane wyjściowe, które są zależne od tego, jak harmonogram zadań obsłużył każde zadanie podrzędne.

:::code language="csharp" source="snippets/cs/detached1.cs":::

[!code-vb[TPL_Continuations#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/detached1.vb#10)]

Końcowy stan zadania poprzedzającego zależy od końcowego stanu wszystkich dołączonych zadań podrzędnych. Stan odłączonych zadań podrzędnych nie ma wpływu na element nadrzędny. Aby uzyskać więcej informacji, zobacz [dołączone i odłączone zadania podrzędne](attached-and-detached-child-tasks.md).

## <a name="associate-state-with-continuations"></a>Skojarz stan z kontynuacjami

Możliwe jest skojarzenie dowolnego stanu z kontynuacją zadania. <xref:System.Threading.Tasks.Task.ContinueWith%2A>Metoda zapewnia przeciążone wersje, które będą miały <xref:System.Object> wartość reprezentującą stan kontynuacji. Możesz później uzyskać dostęp do tego obiektu stanu przy użyciu <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType> właściwości. Ten obiekt stanu jest `null` nieprawidłowy, jeśli nie podasz wartości.

Stan kontynuacji jest przydatny podczas konwertowania istniejącego kodu, który używa [modelu programowania asynchronicznego (APM)](../asynchronous-programming-patterns/asynchronous-programming-model-apm.md) do korzystania z TPL. W programie APM zazwyczaj jest używany stan obiektu w metodzie **BEGIN**_Method_ i później uzyskuje się dostęp do tego stanu przy użyciu <xref:System.IAsyncResult.AsyncState%2A?displayProperty=nameWithType> właściwości. Za pomocą <xref:System.Threading.Tasks.Task.ContinueWith%2A> metody, można zachować ten stan podczas konwertowania kodu, który używa APM do użycia TPL.

Stan kontynuacji może być również przydatny podczas pracy z <xref:System.Threading.Tasks.Task> obiektami w debugerze programu Visual Studio. Na przykład w oknie **zadania równoległe** w kolumnie **zadanie** jest wyświetlany ciąg reprezentujący obiekt stanu dla każdego zadania. Aby uzyskać więcej informacji o oknie **zadań równoległych** , zobacz [Korzystanie z okna zadań](/visualstudio/debugger/using-the-tasks-window).

Poniższy przykład pokazuje, jak używać stanu kontynuacji. Tworzy łańcuch zadań kontynuacji. Każde zadanie zawiera bieżący czas, <xref:System.DateTime> obiekt, dla `state` parametru <xref:System.Threading.Tasks.Task.ContinueWith%2A> metody. Każdy <xref:System.DateTime> obiekt reprezentuje godzinę utworzenia zadania kontynuacji. Każde zadanie powstaje jako wynik drugi <xref:System.DateTime> obiekt, który reprezentuje godzinę zakończenia zadania. Po zakończeniu wszystkich zadań ten przykład wyświetla czas utworzenia i godzinę zakończenia każdego zadania kontynuacji.

:::code language="csharp" source="snippets/cs/continuationstate.cs":::

[!code-vb[TPL_ContinuationState#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuationstate/vb/continuationstate.vb#1)]

## <a name="continuations-that-return-task-types"></a>Kontynuacje zwracające typy zadań

Czasami może być konieczne przetworzenie łańcucha kontynuacji zwracającej <xref:System.Threading.Tasks.Task> Typ. Są one określane jako zadania zagnieżdżone i są wspólne. Gdy zadanie nadrzędne wywołuje <xref:System.Threading.Tasks.Task%601.ContinueWith%2A?displayProperty=nameWithType> i dostarcza zadanie `continuationFunction` , które zwraca wywołanie, <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> Aby utworzyć zadanie proxy reprezentujące asynchroniczne operacje `<Task<Task<T>>>` lub `Task(Of Task(Of T))` (Visual Basic).

Poniższy przykład pokazuje, jak używać kontynuacji, które zawijają dodatkowe funkcje zwracające zadania. Każdą kontynuację można rozpakowany, uwidaczniając wewnętrzne zadanie, które zostało opakowane.

:::code language="csharp" source="snippets/cs/unwrap.cs":::
:::code language="vb" source="snippets/vb/unwrap.vb":::

Aby uzyskać więcej informacji na temat korzystania z programu <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> , zobacz [How to: unnesting a zagnieżdżone zadanie](how-to-unwrap-a-nested-task.md).

## <a name="handle-exceptions-thrown-from-continuations"></a>Obsługa wyjątków zgłoszonych przez kontynuacje

Relację kontynuacji poprzedzającej nie jest relacją nadrzędny-podrzędny. Wyjątki zgłoszone przez kontynuacje nie są propagowane do poprzedzającego. W związku z tym, obsługa wyjątków zgłaszanych przez kontynuacje w miarę obsłużenia ich w innych zadaniach w następujący sposób:

- <xref:System.Threading.Tasks.Task.Wait%2A> <xref:System.Threading.Tasks.Task.WaitAll%2A> <xref:System.Threading.Tasks.Task.WaitAny%2A> Aby poczekać na kontynuację, można użyć metody,, lub lub jej ogólnego odpowiednika. Możesz poczekać na poprzedzające i jego kontynuacje w tej samej `try` instrukcji, jak pokazano w poniższym przykładzie.

:::code language="csharp" source="snippets/cs/exception1.cs":::

[!code-vb[TPL_Continuations#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception1.vb#6)]

- Możesz użyć drugiej kontynuacji, aby obserwować <xref:System.Threading.Tasks.Task.Exception%2A> Właściwość pierwszej kontynuacji. W poniższym przykładzie zadanie próbuje odczytać z nieistniejącego pliku. Kontynuacja następnie wyświetla informacje o wyjątku w zadaniu poprzedzającym.

:::code language="csharp" source="snippets/cs/exception2.cs" id="example":::

[!code-vb[TPL_Continuations#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception2.vb#4)]

Ponieważ został uruchomiony z <xref:System.Threading.Tasks.TaskContinuationOptions.OnlyOnFaulted?displayProperty=nameWithType> opcją, kontynuacja jest wykonywana tylko wtedy, gdy wystąpi wyjątek w poprzedniku, i w związku z tym może założyć, że <xref:System.Threading.Tasks.Task.Exception%2A> Właściwość antecedent nie jest `null` . Jeśli kontynuacja jest wykonywana niezależnie od tego, czy wyjątek jest zgłaszany w przypadku poprzedzającego, należy sprawdzić, czy <xref:System.Threading.Tasks.Task.Exception%2A> Właściwość antecedent nie jest `null` wcześniejsza niż próba obsługi wyjątku, jak pokazano w poniższym fragmencie kodu.

:::code language="csharp" source="snippets/cs/exception2.cs" id="exception":::

[!code-vb[TPL_Continuations#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception2.vb#11)]

Aby uzyskać więcej informacji, zobacz [Obsługa wyjątków](exception-handling-task-parallel-library.md).

- Jeśli kontynuacja jest dołączonym zadaniem podrzędnym, które zostało utworzone przy użyciu <xref:System.Threading.Tasks.TaskContinuationOptions.AttachedToParent?displayProperty=nameWithType> opcji, jego wyjątki będą propagowane przez element nadrzędny z powrotem do wątku wywołującego, podobnie jak w przypadku dowolnego innego dołączonego elementu podrzędnego. Aby uzyskać więcej informacji, zobacz [dołączone i odłączone zadania podrzędne](attached-and-detached-child-tasks.md).

## <a name="see-also"></a>Zobacz także

- [Biblioteka zadań równoległych (TPL)](task-parallel-library-tpl.md)
