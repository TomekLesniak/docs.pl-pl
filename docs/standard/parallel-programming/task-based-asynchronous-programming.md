---
title: Programowanie asynchroniczne oparte na zadaniach — .NET
description: Ten artykuł zawiera informacje na temat programowania asynchronicznego opartego na zadaniach za pośrednictwem biblioteki zadań równoległych (TPL) w programie .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallelism, task
ms.assetid: 458b5e69-5210-45e5-bc44-3888f86abd6f
ms.openlocfilehash: a1abe474628cd88e0c24f4152d83bd8ed7ad7950
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830028"
---
# <a name="task-based-asynchronous-programming"></a>Programowanie asynchroniczne oparte na zadaniach

Biblioteka zadań równoległych (TPL) jest oparta na koncepcji *zadania*, które reprezentuje operację asynchroniczną. Na kilka sposobów zadanie jest podobne do wątku lub <xref:System.Threading.ThreadPool> elementu pracy, ale na wyższym poziomie abstrakcji. Termin *równoległy zadania* odnosi się do co najmniej jednego niezależnego zadania uruchomionego współbieżnie. Zadania zapewniają dwie podstawowe korzyści:

- Efektywniejsze i bardziej skalowalne wykorzystanie zasobów systemowych.

     W tle zadania są umieszczane w kolejce do <xref:System.Threading.ThreadPool> , które zostały ulepszone przy użyciu algorytmów, które określają i dostosowują się do liczby wątków i umożliwiają Równoważenie obciążenia w celu zmaksymalizowania przepływności. Dzięki temu zadania są stosunkowo lekkie i można tworzyć wiele takich zadań, aby włączyć równoległość drobnoziarnistą.

- Większa kontrola programistyczna niż jest to możliwe za pomocą wątku lub elementu roboczego.

     Zadania i środowisko zbudowane wokół nich zawierają bogaty zestaw interfejsów API, które obsługują oczekiwanie, anulowanie, kontynuację, niezawodną obsługę wyjątków, szczegółowe informacje o stanie, planowanie niestandardowe i nie tylko.

Z obu powodów TPL jest preferowanym interfejsem API do pisania kodu wielowątkowego, asynchronicznego i równoległego w programie .NET.

## <a name="creating-and-running-tasks-implicitly"></a>Tworzenie i uruchamianie zadań w sposób niejawny

<xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType>Metoda zapewnia wygodny sposób uruchamiania dowolnej liczby dowolnych instrukcji jednocześnie. Po prostu Przekaż <xref:System.Action> delegata dla każdego elementu pracy. Wyrażenia lambda są najwygodniejszym sposobem na tworzenie tych delegatów. Wyrażenie lambda może wywołać metodę nazwaną lub zapewnić kod inline. W poniższym przykładzie pokazano podstawowe <xref:System.Threading.Tasks.Parallel.Invoke%2A> wywołanie, które tworzy i uruchamia dwa zadania, które są uruchamiane współbieżnie. Pierwsze zadanie jest reprezentowane przez wyrażenie lambda, które wywołuje metodę o nazwie `DoSomeWork` , a drugie zadanie jest reprezentowane przez wyrażenie lambda, które wywołuje metodę o nazwie `DoSomeOtherWork` .

> [!NOTE]
> Ta dokumentacja używa wyrażeń lambda do definiowania delegatów w TPL. Jeśli nie znasz wyrażeń lambda w języku C# lub Visual Basic, zobacz [lambda Expressions in PLINQ and TPL](lambda-expressions-in-plinq-and-tpl.md).

[!code-csharp[TPL#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#21)]
[!code-vb[TPL#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#21)]

> [!NOTE]
> Liczba <xref:System.Threading.Tasks.Task> wystąpień utworzonych w tle przez program <xref:System.Threading.Tasks.Parallel.Invoke%2A> nie musi być równa podanej liczbie delegatów. TPL może wykorzystywać różne optymalizacje, zwłaszcza z dużą liczbą obiektów delegowanych.

Aby uzyskać więcej informacji, zobacz [How to: use Parallel. Invoke w celu wykonywania operacji równoległych](how-to-use-parallel-invoke-to-execute-parallel-operations.md).

Aby uzyskać większą kontrolę nad wykonywaniem zadań lub w celu zwrócenia wartości z zadania, należy jawnie współpracować z <xref:System.Threading.Tasks.Task> obiektami.

## <a name="creating-and-running-tasks-explicitly"></a>Tworzenie i uruchamianie zadań w sposób jawny

Zadanie, które nie zwraca wartości, jest reprezentowane przez <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> klasę. Zadanie, które zwraca wartość, jest reprezentowane przez <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> klasę, która dziedziczy z <xref:System.Threading.Tasks.Task> . Obiekt zadania obsługuje szczegóły infrastruktury i zapewnia metody i właściwości, które są dostępne z wątku wywoływania przez cały okres istnienia zadania. Na przykład możesz uzyskać dostęp do <xref:System.Threading.Tasks.Task.Status%2A> właściwości zadania w dowolnym momencie, aby ustalić, czy uruchomiono, uruchomiono do ukończenia, zostało anulowane lub zgłosiło wyjątek. Stan jest reprezentowany przez <xref:System.Threading.Tasks.TaskStatus> Wyliczenie.

Tworząc zadanie, nadajesz mu delegata użytkownika hermetyzującego kod, który zadanie będzie wykonywało. Delegat może być wyrażony jako delegat nazwany, metoda anonimowa lub wyrażenie lambda. Wyrażenia lambda mogą zawierać wywołanie metody nazwanej, jak pokazano w następującym przykładzie. Należy zauważyć, że przykład zawiera wywołanie metody, <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> Aby upewnić się, że zadanie kończy wykonywanie przed zakończeniem działania aplikacji trybu konsoli.

[!code-csharp[TPL_TaskIntro#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/lambda1.cs#1)]
[!code-vb[TPL_TaskIntro#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/lambda1.vb#1)]

Można również użyć metod, <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> Aby utworzyć i uruchomić zadanie w ramach jednej operacji. Aby zarządzać zadaniem, <xref:System.Threading.Tasks.Task.Run%2A> metody używają domyślnego harmonogramu zadań, niezależnie od tego, który harmonogram zadań jest skojarzony z bieżącym wątkiem. <xref:System.Threading.Tasks.Task.Run%2A>Metody są preferowanym sposobem tworzenia i uruchamiania zadań, gdy nie jest wymagana większa kontrola nad tworzeniem i planowaniem zadania.

[!code-csharp[TPL_TaskIntro#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/run1.cs#2)]
[!code-vb[TPL_TaskIntro#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/run1.vb#2)]

Możesz również użyć metody, <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> Aby utworzyć i uruchomić zadanie w ramach jednej operacji. Użyj tej metody, gdy tworzenie i planowanie nie muszą być rozdzielone i potrzebujesz dodatkowych opcji tworzenia zadań lub korzystania z określonego harmonogramu, lub gdy potrzebujesz przekazać dodatkowy stan do zadania, które można pobrać za pomocą jego <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType> właściwości, jak pokazano w poniższym przykładzie.

[!code-csharp[TPL_TaskIntro#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/asyncstate.cs#23)]
[!code-vb[TPL_TaskIntro#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/asyncstate.vb#23)]

<xref:System.Threading.Tasks.Task> i <xref:System.Threading.Tasks.Task%601> każdy uwidacznia Właściwość statyczną <xref:System.Threading.Tasks.Task.Factory%2A> zwracającą wystąpienie domyślne <xref:System.Threading.Tasks.TaskFactory> , tak aby można było wywołać metodę jako `Task.Factory.StartNew()` . Ponadto, w poniższym przykładzie, ponieważ zadania są typu <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> , każda z nich ma właściwość publiczną <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> zawierającą wynik obliczenia. Zadania są wykonywane asynchroniczne i mogą być kończone w dowolnej kolejności. Jeśli do <xref:System.Threading.Tasks.Task%601.Result%2A> Właściwości uzyskuje się dostęp przed zakończeniem obliczeń, właściwość blokuje wątek wywołujący do momentu, gdy wartość jest dostępna.

[!code-csharp[TPL_TaskIntro#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/result1.cs#4)]
[!code-vb[TPL_TaskIntro#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/result1.vb#4)]

Aby uzyskać więcej informacji, zobacz [jak: zwrócić wartość z zadania](how-to-return-a-value-from-a-task.md).

Używając wyrażenia lambda do utworzenia delegata, masz dostęp do wszystkich zmiennych, które są widoczne w tym momencie w kodzie źródłowym. Jednak w niektórych przypadkach, zwłaszcza w pętlach, lambda nie przechwytuje zmiennej zgodnie z oczekiwaniami. Przechwytuje tylko wartość końcową, a nie wartość, która mutuje po każdej iteracji. Poniższy przykład ilustruje ten problem. Przekazuje licznik pętli do wyrażenia lambda, które tworzy wystąpienie `CustomData` obiektu i używa licznika pętli jako identyfikatora obiektu. Jak wynika z przykładu, każdy `CustomData` obiekt ma identyczny identyfikator.

[!code-csharp[TPL_TaskIntro#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/iteration1b.cs#22)]
[!code-vb[TPL_TaskIntro#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/iteration1b.vb#22)]

Możesz uzyskać dostęp do wartości w każdej iteracji poprzez zapewnienie obiektu stanu do zadania za pośrednictwem jej konstruktora. Poniższy przykład modyfikuje poprzedni przykład przy użyciu licznika pętli podczas tworzenia `CustomData` obiektu, który z kolei jest przenoszona do wyrażenia lambda.  Dane wyjściowe z przykładu pokazują, że każdy `CustomData` obiekt ma teraz unikatowy identyfikator oparty na wartości licznika pętli w momencie wystąpienia obiektu.

[!code-csharp[TPL_TaskIntro#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/iteration1a.cs#21)]
[!code-vb[TPL_TaskIntro#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/iteration1a.vb#21)]

Ten stan jest przekazaniem jako argument delegata zadania, a dostęp do niego można uzyskać z obiektu zadania przy użyciu <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType> właściwości.  Poniższy przykład jest modyfikacją poprzedniego. Używa właściwości, <xref:System.Threading.Tasks.Task.AsyncState%2A> Aby wyświetlić informacje o `CustomData` obiektach przekazaną do wyrażenia lambda.

[!code-csharp[TPL_TaskIntro#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/asyncstate.cs#23)]
[!code-vb[TPL_TaskIntro#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/asyncstate.vb#23)]

## <a name="task-id"></a>Identyfikator zadania

Każde zadanie otrzymuje identyfikator w postaci liczby całkowitej, który jednoznacznie identyfikuje go w domenie aplikacji i można uzyskać do niego dostęp przy użyciu <xref:System.Threading.Tasks.Task.Id%2A?displayProperty=nameWithType> właściwości. Identyfikator jest przydatny do wyświetlania informacji o zadaniach w oknach **równoległych stosów** i **zadań** debugera programu Visual Studio. Identyfikator jest tworzony z opóźnieniem, co oznacza, że nie jest on tworzony do momentu pojawienia się stosownego żądania. Dlatego zadanie może mieć inny identyfikator za każdym razem, gdy program jest uruchamiany. Aby uzyskać więcej informacji o sposobie wyświetlania identyfikatorów zadań w debugerze, zobacz [Korzystanie z okna zadania](/visualstudio/debugger/using-the-tasks-window) i [Korzystanie z okna stosów równoległych](/visualstudio/debugger/using-the-parallel-stacks-window).

## <a name="task-creation-options"></a>Opcje tworzenia zadań

Większość interfejsów API, które tworzą zadania, zapewnia przeciążenia, które akceptują <xref:System.Threading.Tasks.TaskCreationOptions> parametr. Określając co najmniej jedną z tych opcji, można poinformować harmonogram zadań, jak zaplanować zadanie w puli wątków. Opcje można łączyć przy użyciu operacji bitowego **lub** bitowej.

Poniższy przykład pokazuje zadanie, które zawiera <xref:System.Threading.Tasks.TaskCreationOptions.LongRunning> <xref:System.Threading.Tasks.TaskContinuationOptions.PreferFairness> Opcje i.

[!code-csharp[TPL_TaskIntro#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#03)]
[!code-vb[TPL_TaskIntro#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#03)]

## <a name="tasks-threads-and-culture"></a>Zadania, wątki i kultura

Każdy wątek ma skojarzoną kulturę i kulturę interfejsu użytkownika, które są <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> definiowane <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> odpowiednio przez właściwości i. Kultura wątku jest używana w takich operacjach jak formatowanie, analizowanie, sortowanie i Porównywanie ciągów. Kultura interfejsu użytkownika wątku jest używana podczas wyszukiwania zasobów.

O ile nie zostanie określona kultura domyślna dla wszystkich wątków w domenie aplikacji przy użyciu <xref:System.Globalization.CultureInfo.DefaultThreadCurrentCulture%2A?displayProperty=nameWithType> <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=nameWithType> właściwości i, kultura domyślna i kultura interfejsu użytkownika wątku są zdefiniowane przez kulturę systemu. Jeśli jawnie ustawisz kulturę wątku i uruchomisz nowy wątek, nowy wątek nie dziedziczy kultury wywołującego wątku; Zamiast tego, jego kultura jest domyślną kulturą systemu. Jednak w programowaniu opartym na zadaniach zadania korzystają z kultury wywołującej wątku, nawet jeśli zadanie jest uruchamiane asynchronicznie w innym wątku.

Poniższy przykład przedstawia prostą ilustrację. Zmienia bieżącą kulturę aplikacji na francuski (Francja) (lub, jeśli francuski (Francja) jest już bieżącą kulturą, na angielski (Stany Zjednoczone)). Następnie wywołuje delegata o nazwie `formatDelegate` , która zwraca niektóre liczby sformatowane jako wartości walutowe w nowej kulturze. Czy delegat jest wywoływany przez zadanie synchronicznie, czy asynchronicznie, zadanie używa kultury wywołującego wątku.

:::code language="csharp" source="snippets/cs/asyncculture1.cs" id="1":::

:::code language="vbnet" source="snippets/vb/asyncculture1.vb" id="1":::

> [!NOTE]
> W wersjach .NET Framework wcześniejszych niż .NET Framework 4,6 kultura zadania jest określana przez kulturę wątku, w którym jest *uruchomiona*, a nie kulturą *wątku wywołującego*. W przypadku zadań asynchronicznych oznacza to, że kultura używana przez zadanie może różnić się od kultury wywołującej wątku.

Aby uzyskać więcej informacji na temat zadań i kultur asynchronicznych, zobacz sekcję "operacje dotyczące kultur i asynchronicznych operacji" w <xref:System.Globalization.CultureInfo> temacie.

## <a name="creating-task-continuations"></a>Tworzenie kontynuacji zadań

<xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>Metody i <xref:System.Threading.Tasks.Task%601.ContinueWith%2A?displayProperty=nameWithType> umożliwiają określenie zadania do uruchomienia po zakończeniu *zadania poprzedzającego* . Delegat zadania kontynuacji jest przekazywane odwołaniem do zadania poprzedzającego, aby można było przejrzeć stan zadania poprzedzającego i, pobierając wartość <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> właściwości, może użyć danych wyjściowych poprzedzających jako dane wejściowe dla kontynuacji.

W poniższym przykładzie `getData` zadanie jest uruchamiane przez wywołanie <xref:System.Threading.Tasks.TaskFactory.StartNew%60%601%28System.Func%7B%60%600%7D%29?displayProperty=nameWithType> metody. `processData`Zadanie jest uruchamiane automatycznie po `getData` zakończeniu i `displayData` jest uruchamiane po `processData` zakończeniu. `getData` Tworzy tablicę liczb całkowitych, która jest dostępna dla `processData` zadania za pomocą `getData` <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> właściwości zadania. `processData`Zadanie przetwarza tę tablicę i zwraca wynik, którego typ jest wywnioskowany na podstawie zwracanego typu wyrażenia lambda przekazanego do <xref:System.Threading.Tasks.Task%601.ContinueWith%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%600%7D%2C%60%600%7D%29?displayProperty=nameWithType> metody. `displayData`Zadanie jest wykonywane automatycznie po `processData` zakończeniu, a <xref:System.Tuple%603> obiekt zwrócony przez `processData` wyrażenie lambda jest dostępny dla `displayData` zadania za pomocą `processData` <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> właściwości zadania. `displayData`Zadanie przyjmuje wynik `processData` zadania i tworzy wynik, którego typ jest wnioskowany w podobny sposób i który jest udostępniany dla programu we <xref:System.Threading.Tasks.Task%601.Result%2A> właściwości.

[!code-csharp[TPL_TaskIntro#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/continuations1.cs#5)]
[!code-vb[TPL_TaskIntro#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/continuations1.vb#5)]

Ponieważ <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> jest to metoda wystąpienia, można połączyć metody łańcuchowo zamiast tworzenia wystąpienia <xref:System.Threading.Tasks.Task%601> obiektu dla każdego zadania poprzedzającego. Poniższy przykład jest funkcjonalnie identyczny jak w poprzednim przykładzie, z tą różnicą, że łańcuchuje jednocześnie wywołania <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> metody. Należy zauważyć, że <xref:System.Threading.Tasks.Task%601> obiekt zwrócony przez łańcuch wywołań metod jest ostatnim zadaniem kontynuacji.

[!code-csharp[TPL_TaskIntro#24](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/continuations2.cs#24)]
[!code-vb[TPL_TaskIntro#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/continuations2.vb#24)]

<xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>Metody i <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> umożliwiają kontynuowanie wykonywania wielu zadań.

Aby uzyskać więcej informacji, zobacz Tworzenie [łańcucha zadań przy użyciu zadań kontynuacji](chaining-tasks-by-using-continuation-tasks.md).

## <a name="creating-detached-child-tasks"></a>Tworzenie odłączonych zadań podrzędnych

Gdy kod użytkownika, który jest uruchomiony w zadaniu, tworzy nowe zadanie i nie określa <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> opcji, nowe zadanie nie jest zsynchronizowane z zadaniem nadrzędnym w żaden specjalny sposób. Ten typ zadania niezsynchronizowanego jest nazywany *odłączonym zadaniem zagnieżdżonym* lub *odłączonym zadaniem podrzędnym*. Poniższy przykład przedstawia zadanie, które tworzy jedno odłączone zadanie podrzędne.

[!code-csharp[TPL_TaskIntro#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#07)]
[!code-vb[TPL_TaskIntro#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#07)]

Należy zauważyć, że zadanie nadrzędne nie czeka na zakończenie odłączonego zadania podrzędnego.

## <a name="creating-child-tasks"></a>Tworzenie zadań podrzędnych

Gdy kod użytkownika, który jest uruchomiony w zadaniu, tworzy zadanie z <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> opcją, nowe zadanie jest znane jako *dołączone zadanie podrzędne* zadania nadrzędnego. Można użyć opcji do wyznaczania <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> równoległości zadań strukturalnych, ponieważ zadanie nadrzędne niejawnie czeka na zakończenie wszystkich dołączonych zadań podrzędnych. Poniższy przykład przedstawia zadanie nadrzędne, które tworzy dziesięć dołączonych zadań podrzędnych. Należy zauważyć, że chociaż przykład wywołuje <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> metodę, aby czekać na zakończenie zadania nadrzędnego, nie musi jawnie czekać na ukończenie dołączonych zadań podrzędnych.

[!code-csharp[TPL_TaskIntro#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/child1.cs#8)]
[!code-vb[TPL_TaskIntro#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/child1.vb#8)]

Zadanie nadrzędne może użyć <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> opcji, aby uniemożliwić innym zadaniom dołączenie do zadania nadrzędnego. Aby uzyskać więcej informacji, zobacz [dołączone i odłączone zadania podrzędne](attached-and-detached-child-tasks.md).

## <a name="waiting-for-tasks-to-finish"></a>Oczekiwanie na zakończenie zadań

<xref:System.Threading.Tasks.Task?displayProperty=nameWithType>Typy i <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> zapewniają kilka przeciążeń <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> metod, które umożliwiają oczekiwanie na zakończenie zadania. Ponadto przeciążenia statycznych <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> i <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> metod umożliwiają oczekiwanie na zakończenie wszystkich lub wszystkich tablic zadań.

Zazwyczaj użytkownik czeka na zadanie z jednego z poniższych powodów:

- Główny wątek zależy od wyniku końcowego obliczonego przez zadanie.

- Trzeba obsługiwać wyjątki, które mogą być zgłoszone przez zadanie.

- Aplikacja może się zakończyć zanim wszystkie zadania zostaną ukończone. Na przykład aplikacje konsoli zakończą działanie zaraz po wykonaniu wszystkich synchronicznych kodów w `Main` (punkt wejścia aplikacji).

Poniższy przykład przedstawia podstawowy wzorzec, który nie wymaga obsługi wyjątków.

[!code-csharp[TPL_TaskIntro#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#06)]
[!code-vb[TPL_TaskIntro#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#06)]

Aby zapoznać się z przykładem, który pokazuje obsługę wyjątków, zobacz temat [Obsługa wyjątków](exception-handling-task-parallel-library.md).

Niektóre przeciążenia pozwalają określić limit czasu, a inne przyjmują dodatkowy <xref:System.Threading.CancellationToken> jako parametr wejściowy, aby można było anulować odczekanie lub w odpowiedzi na dane wejściowe użytkownika.

Podczas oczekiwania na zadanie, niejawnie poczekaj na wszystkie elementy podrzędne tego zadania, które zostały utworzone przy użyciu <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> opcji. <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> zwraca natychmiast, jeśli zadanie zostało już ukończone. Wszelkie wyjątki wywoływane przez zadanie zostaną zgłoszone przez <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> metodę, nawet jeśli <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> Metoda została wywołana po ukończeniu zadania.

## <a name="composing-tasks"></a>Tworzenie zadań

<xref:System.Threading.Tasks.Task>Klasy i <xref:System.Threading.Tasks.Task%601> udostępniają kilka metod, które mogą pomóc w tworzeniu wielu zadań do implementowania wspólnych wzorców i lepszego używania funkcji języka asynchronicznego, które są dostarczane przez C#, Visual Basic i F #. W tej sekcji opisano <xref:System.Threading.Tasks.Task.WhenAll%2A> <xref:System.Threading.Tasks.Task.WhenAny%2A> metody,, <xref:System.Threading.Tasks.Task.Delay%2A> i <xref:System.Threading.Tasks.Task.FromResult%2A> .

### <a name="taskwhenall"></a>Task.WhenAll

<xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>Metoda asynchronicznie czeka na <xref:System.Threading.Tasks.Task> zakończenie wielu <xref:System.Threading.Tasks.Task%601> obiektów lub. Zapewnia przeciążone wersje, które umożliwiają czekanie na niejednolite zestawy zadań. Na przykład możesz poczekać, aż wiele <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601> obiektów i obiekty mają być wykonane z jednego wywołania metody.

### <a name="taskwhenany"></a>Task.WhenAny

<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>Metoda asynchronicznie czeka na zakończenie jednego z <xref:System.Threading.Tasks.Task> wielu <xref:System.Threading.Tasks.Task%601> obiektów. Podobnie jak w <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> metodzie, ta metoda zapewnia przeciążone wersje, które umożliwiają oczekiwanie na niejednolite zestawy zadań. <xref:System.Threading.Tasks.Task.WhenAny%2A>Metoda jest szczególnie przydatna w następujących scenariuszach.

- Operacje nadmiarowe. Należy wziąć pod uwagę algorytm lub operację, które mogą być wykonywane na wiele sposobów. Możesz użyć <xref:System.Threading.Tasks.Task.WhenAny%2A> metody, aby wybrać operację, która zakończy się pierwsza, a następnie anulować pozostałe operacje.

- Operacje z przeplotem. Można uruchomić wiele operacji, które muszą zakończyć się i użyć <xref:System.Threading.Tasks.Task.WhenAny%2A> metody, aby przetwarzać wyniki po zakończeniu każdej operacji. Po zakończeniu jednej operacji można uruchomić jedno lub więcej dodatkowych zadań.

- Operacje ograniczane. Możesz użyć metody, <xref:System.Threading.Tasks.Task.WhenAny%2A> Aby zwiększyć poprzedni scenariusz, ograniczając liczbę współbieżnych operacji.

- Wygasłe operacje. Można użyć metody, <xref:System.Threading.Tasks.Task.WhenAny%2A> Aby wybrać jedno lub więcej zadań i zadanie, które zakończy się po określonym czasie, takie jak zadanie zwracane przez <xref:System.Threading.Tasks.Task.Delay%2A> metodę. <xref:System.Threading.Tasks.Task.Delay%2A>Metoda jest opisana w następnej sekcji.

### <a name="taskdelay"></a>Task.Delay

<xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>Metoda tworzy <xref:System.Threading.Tasks.Task> obiekt, który kończy się po określonym czasie. Możesz użyć tej metoda do tworzenia pętli, które od czasu do czasu pobierają dane, wprowadzają limity czasu, opóźniają obsługę danych wejściowych użytkownika przez wyznaczony czas i tak dalej.

### <a name="tasktfromresult"></a>Task(T).FromResult

Za pomocą <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> metody, można utworzyć <xref:System.Threading.Tasks.Task%601> obiekt, który przechowuje wstępnie obliczony wynik. Ta metoda jest przydatna w przypadku wykonywania operacji asynchronicznej, która zwraca <xref:System.Threading.Tasks.Task%601> obiekt, a wynik tego <xref:System.Threading.Tasks.Task%601> obiektu jest już obliczany. Przykład używany <xref:System.Threading.Tasks.Task.FromResult%2A> do pobierania wyników asynchronicznych operacji pobierania przechowywanych w pamięci podręcznej znajduje się w temacie [How to: Create precomputed Tasks](how-to-create-pre-computed-tasks.md).

## <a name="handling-exceptions-in-tasks"></a>Obsługa wyjątków w zadaniach

Gdy zadanie zgłasza jeden lub więcej wyjątków, wyjątki są opakowane w <xref:System.AggregateException> wyjątek. Ten wyjątek jest propagowany z powrotem do wątku, który jest przyłączony do zadania, czyli zazwyczaj jest to wątek, który oczekuje na zakończenie zadania lub wątek, który uzyskuje dostęp do <xref:System.Threading.Tasks.Task%601.Result%2A> właściwości. To zachowanie służy do wymuszania zasady .NET Framework, zgodnie z którą wszystkie nieobsłużone wyjątki powinny domyślnie przerywać proces. Kod wywołujący może obsłużyć wyjątki przy użyciu dowolnego z następujących elementów w `try` / `catch` bloku:

- <xref:System.Threading.Tasks.Task.Wait%2A>Metoda

- <xref:System.Threading.Tasks.Task.WaitAll%2A>Metoda

- <xref:System.Threading.Tasks.Task.WaitAny%2A>Metoda

- <xref:System.Threading.Tasks.Task%601.Result%2A>Właściwość

Wątek sprzęgający może również obsługiwać wyjątki, uzyskując dostęp do <xref:System.Threading.Tasks.Task.Exception%2A> właściwości, zanim zadanie zostanie pobrane jako elementy bezużyteczne. Dostęp do tej właściwości zapobiega temu, że nieobsługiwany wyjątek inicjuje zachowanie propagacji wyjątku, które przerywa proces wraz z finalizacją obiektu.

Aby uzyskać więcej informacji dotyczących wyjątków i zadań, zobacz temat [Obsługa wyjątków](exception-handling-task-parallel-library.md).

## <a name="canceling-tasks"></a>Anulowanie zadań

<xref:System.Threading.Tasks.Task>Klasa obsługuje wspólne anulowanie i jest w pełni zintegrowana z <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> <xref:System.Threading.CancellationToken?displayProperty=nameWithType> klasami i, które zostały wprowadzone w .NET Framework 4. Wiele konstruktorów w <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> klasie przyjmuje <xref:System.Threading.CancellationToken> obiekt jako parametr wejściowy. Wiele z <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> <xref:System.Threading.Tasks.Task.Run%2A> przeciążeń i zawiera również <xref:System.Threading.CancellationToken> parametr.

Można utworzyć token i wydać żądanie anulowania w późniejszym czasie, za pomocą <xref:System.Threading.CancellationTokenSource> klasy. Przekaż token do <xref:System.Threading.Tasks.Task> argumentu jako argument, a także odwołujący się do tego samego tokenu w delegatze użytkownika, który wykonuje odpowiedź na żądanie anulowania.

Aby uzyskać więcej informacji, zobacz [Anulowanie zadania](task-cancellation.md) i [instrukcje: Anulowanie zadania i jego elementów podrzędnych](how-to-cancel-a-task-and-its-children.md).

## <a name="the-taskfactory-class"></a>Klasa TaskFactory

<xref:System.Threading.Tasks.TaskFactory>Klasa zawiera metody statyczne, które hermetyzują niektóre typowe wzorce do tworzenia i uruchamiania zadań oraz zadań kontynuacji.

- Najbardziej typowym wzorcem jest <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> , który tworzy i uruchamia zadanie w jednej instrukcji.

- Podczas tworzenia zadań kontynuacji z wielu poprzedników należy użyć <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A> metody lub <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> metody lub ich odpowiedników w <xref:System.Threading.Tasks.Task%601> klasie. Aby uzyskać więcej informacji, zobacz Tworzenie [łańcucha zadań przy użyciu zadań kontynuacji](chaining-tasks-by-using-continuation-tasks.md).

- Aby hermetyzować asynchroniczny model programowania `BeginX` i `EndX` metody w <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601> wystąpieniu lub, użyj <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> metod. Aby uzyskać więcej informacji, zobacz [TPL i tradycyjny .NET Framework programowanie asynchroniczne](tpl-and-traditional-async-programming.md).

Domyślną <xref:System.Threading.Tasks.TaskFactory> można uzyskać dostęp do właściwości statycznej <xref:System.Threading.Tasks.Task> klasy lub <xref:System.Threading.Tasks.Task%601> klasy. Można również utworzyć wystąpienie <xref:System.Threading.Tasks.TaskFactory> bezpośrednio i określić różne opcje, które obejmują <xref:System.Threading.CancellationToken> , opcję, <xref:System.Threading.Tasks.TaskCreationOptions> <xref:System.Threading.Tasks.TaskContinuationOptions> opcję lub <xref:System.Threading.Tasks.TaskScheduler> . Wszelkie opcje są określane podczas tworzenia fabryki zadań do wszystkich zadań, które tworzy, chyba że <xref:System.Threading.Tasks.Task> jest tworzona przy użyciu <xref:System.Threading.Tasks.TaskCreationOptions> wyliczenia, w takim przypadku opcje zadania przesłaniają te fabryki zadań.

## <a name="tasks-without-delegates"></a>Zadania bez delegatów

W niektórych przypadkach można użyć <xref:System.Threading.Tasks.Task> do hermetyzacji pewnej operacji asynchronicznej wykonywanej przez składnik zewnętrzny zamiast własnego delegata użytkownika. Jeśli operacja jest oparta na wzorcu początku/końca modelu programowania asynchronicznego, można użyć <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> metod. Jeśli tak nie jest, można użyć <xref:System.Threading.Tasks.TaskCompletionSource%601> obiektu do zawinięcia operacji w zadaniu, a tym samym uzyskać niektóre korzyści wynikające z <xref:System.Threading.Tasks.Task> programowania, na przykład obsługę propagacji i kontynuacji wyjątków. Aby uzyskać więcej informacji, zobacz <xref:System.Threading.Tasks.TaskCompletionSource%601>.

## <a name="custom-schedulers"></a>Niestandardowe harmonogramy

Większość deweloperów aplikacji lub bibliotek nie określa, na którym procesorze jest wykonywane zadanie, jak synchronizuje swoją współpracę z innymi zadaniami lub jak jest zaplanowana w <xref:System.Threading.ThreadPool?displayProperty=nameWithType> . Wymagają one tylko, aby było wykonane jak najwydajniej na komputerze-hoście. Jeśli potrzebna większa kontrola nad szczegółami planowania, biblioteka zadań równoległych pozwala skonfigurować niektóre ustawienia w domyślnym harmonogramie zadań, a nawet pozwala podać niestandardowy harmonogram. Aby uzyskać więcej informacji, zobacz <xref:System.Threading.Tasks.TaskScheduler>.

## <a name="related-data-structures"></a>Powiązane struktury danych

TPL ma kilka nowych typów publicznych, które są przydatne w scenariuszach równoległych i sekwencyjnych. Obejmują one kilka bezpiecznych dla wątków, szybkie i skalowalne klasy kolekcji w <xref:System.Collections.Concurrent?displayProperty=nameWithType> przestrzeni nazw oraz kilka nowych typów synchronizacji, na przykład <xref:System.Threading.Semaphore?displayProperty=nameWithType> i <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> , które są bardziej wydajne niż ich poprzedniki dla konkretnych rodzajów obciążeń. Inne nowe typy w .NET Framework 4, na przykład <xref:System.Threading.Barrier?displayProperty=nameWithType> i <xref:System.Threading.SpinLock?displayProperty=nameWithType> , udostępniają funkcje, które nie były dostępne we wcześniejszych wersjach. Aby uzyskać więcej informacji, zobacz [struktury danych dla programowania równoległego](data-structures-for-parallel-programming.md).

## <a name="custom-task-types"></a>Niestandardowe typy zadań

Zalecamy, aby nie dziedziczyć z <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> ani <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> . Zamiast tego zalecamy użycie <xref:System.Threading.Tasks.Task.AsyncState%2A> właściwości w celu skojarzenia dodatkowych danych lub stanu z <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601> obiektem lub. Można również użyć metod rozszerzających, aby rozszerzać funkcjonalność <xref:System.Threading.Tasks.Task> klas i <xref:System.Threading.Tasks.Task%601> . Aby uzyskać więcej informacji na temat metod rozszerzających, zobacz [metody](../../csharp/programming-guide/classes-and-structs/extension-methods.md) rozszerzania i [metody rozszerzenia](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).

Jeśli musisz dziedziczyć z <xref:System.Threading.Tasks.Task> lub <xref:System.Threading.Tasks.Task%601> , nie można użyć <xref:System.Threading.Tasks.Task.Run%2A> , lub <xref:System.Threading.Tasks.TaskFactory?displayProperty=nameWithType> , <xref:System.Threading.Tasks.TaskFactory%601?displayProperty=nameWithType> lub <xref:System.Threading.Tasks.TaskCompletionSource%601?displayProperty=nameWithType> klasy do tworzenia wystąpień niestandardowego typu zadania, ponieważ te mechanizmy tworzą tylko <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601> obiekty i. Ponadto nie można używać mechanizmów kontynuacji zadania, które są dostarczane przez <xref:System.Threading.Tasks.Task> ,, <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.TaskFactory> i  <xref:System.Threading.Tasks.TaskFactory%601> do tworzenia wystąpień niestandardowego typu zadania, ponieważ te mechanizmy również tworzą tylko <xref:System.Threading.Tasks.Task>  <xref:System.Threading.Tasks.Task%601> obiekty i.

## <a name="related-topics"></a>Powiązane tematy

|Tytuł|Opis|
|-|-|
|[Tworzenie łańcuchów zadań przy użyciu zadań kontynuacji](chaining-tasks-by-using-continuation-tasks.md)|Opisuje, jak działa kontynuacja.|
|[Dołączone i odłączone zadania podrzędne](attached-and-detached-child-tasks.md)|Opisano różnicę między zadaniami podrzędnymi dołączonymi i odłączonymi.|
|[Anulowanie zadania](task-cancellation.md)|W tym artykule opisano obsługę anulowania, która jest wbudowana w <xref:System.Threading.Tasks.Task> obiekt.|
|[Obsługa wyjątków](exception-handling-task-parallel-library.md)|Opisuje sposób obsługi wyjątków w wątkach współbieżnych.|
|[Instrukcje: Wykonywanie operacji równoległych za pomocą elementu Parallel.Invoke](how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Opisuje sposób użycia programu <xref:System.Threading.Tasks.Parallel.Invoke%2A> .|
|[Instrukcje: Zwracanie wartości z zadania](how-to-return-a-value-from-a-task.md)|Zawiera opis sposobu zwracania wartości z zadań.|
|[Instrukcje: Anulowanie zadania i jego elementów podrzędnych](how-to-cancel-a-task-and-its-children.md)|Opisuje, jak anulować zadania.|
|[Instrukcje: Tworzenie wstępnie obliczonych zadań](how-to-create-pre-computed-tasks.md)|Opisuje, jak używać <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> metody do pobierania wyników asynchronicznych operacji pobierania przechowywanych w pamięci podręcznej.|
|[Instrukcje: Przenoszenie drzewa binarnego z zadaniami równoległymi](how-to-traverse-a-binary-tree-with-parallel-tasks.md)|Opisuje używanie zadań do przechodzenia w drzewie binarnym.|
|[Instrukcje: Odpakowywanie zadania zagnieżdżonego](how-to-unwrap-a-nested-task.md)|Pokazuje, jak używać <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> metody rozszerzenia.|
|[Równoległość danych](data-parallelism-task-parallel-library.md)|Opisuje sposób użycia <xref:System.Threading.Tasks.Parallel.For%2A> i <xref:System.Threading.Tasks.Parallel.ForEach%2A> do tworzenia pętli równoległych nad danymi.|
|[Programowanie równoległe](index.md)|Węzeł najwyższego poziomu dla .NET Framework programowania równoległego.|

## <a name="see-also"></a>Zobacz także

- [Programowanie równoległe](index.md)
- [Przykłady programowania równoległego przy użyciu programu .NET Core & .NET Standard](/samples/browse/?products=dotnet-core%2Cdotnet-standard&term=parallel)
