---
title: Przegląd elementów podstawowych synchronizacji
description: Informacje o elementach podstawowych synchronizacji wątków .NET służących do synchronizowania dostępu do współużytkowanego zasobu lub interakcji wątku kontroli
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization, threads
- threading [.NET],synchronizing threads
- managed threading
ms.assetid: b782bcb8-da6a-4c6a-805f-2eb46d504309
ms.openlocfilehash: d5ae0fe5813952742950582a4282cd1c6ab6a870
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188981"
---
# <a name="overview-of-synchronization-primitives"></a>Przegląd elementów podstawowych synchronizacji

Platforma .NET udostępnia szereg typów, których można użyć do synchronizowania dostępu do zasobu udostępnionego lub współdziałania wątku współrzędnych.

> [!IMPORTANT]
> Użyj tego samego wystąpienia pierwotnego synchronizacji, aby chronić dostęp do zasobu udostępnionego. W przypadku użycia innych wystąpień pierwotnych synchronizacji do ochrony tego samego zasobu należy obejść ochronę zapewnioną przez pierwotną synchronizację.

## <a name="waithandle-class-and-lightweight-synchronization-types"></a>Klasy WaitHandle i typy uproszczonych synchronizacji

Wiele prymitywów synchronizacji platformy .NET pochodzi od <xref:System.Threading.WaitHandle?displayProperty=nameWithType> klasy, która hermetyzuje natywny uchwyt synchronizacji systemu operacyjnego i używa mechanizmu sygnalizowania dla interakcji wątku. Te klasy obejmują:

- <xref:System.Threading.Mutex?displayProperty=nameWithType>, która przyznaje wyłączny dostęp do zasobu udostępnionego. Stan obiektu mutex jest sygnalizowane, jeśli żaden z nich nie należy do niego.
- <xref:System.Threading.Semaphore?displayProperty=nameWithType>, które ogranicza liczbę wątków, które mogą uzyskiwać dostęp do zasobów udostępnionych lub puli zasobów współbieżnie. Stan semafora jest ustawiany do sygnalizowania, gdy jego licznik jest większy od zera i nie jest sygnalizowane, gdy jego licznik ma wartość zero.
- <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>, która reprezentuje zdarzenie synchronizacji wątku i może być w stanie sygnalizowane lub Niesygnalizowane.
- <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>, który pochodzi z <xref:System.Threading.EventWaitHandle> i, po zasygnalizowaniu automatycznie resetuje do stanu niesygnalizowanego po zwolnieniu pojedynczego wątku oczekującego.
- <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>, który pochodzi z <xref:System.Threading.EventWaitHandle> i, po zasygnalizowaniu, pozostaje w stanie zasygnalizowania do momentu <xref:System.Threading.EventWaitHandle.Reset%2A> wywołania metody.

W .NET Framework, ponieważ <xref:System.Threading.WaitHandle> pochodzą z <xref:System.MarshalByRefObject?displayProperty=nameWithType> , te typy mogą służyć do synchronizowania działań wątków między granicami domeny aplikacji.

W .NET Framework, .NET Core i .NET 5 +, niektóre z tych typów mogą reprezentować nazwane uchwyty synchronizacji systemu, które są widoczne w całym systemie operacyjnym i mogą być używane do synchronizacji między procesami:

- <xref:System.Threading.Mutex>
- <xref:System.Threading.Semaphore> (w systemie Windows)
- <xref:System.Threading.EventWaitHandle> (w systemie Windows)

Aby uzyskać więcej informacji, zobacz <xref:System.Threading.WaitHandle> Informacje o interfejsie API.

Typy uproszczonych synchronizacji nie polegają na podstawowych uchwytach systemu operacyjnego i zwykle zapewniają lepszą wydajność. Nie można ich jednak używać do synchronizacji między procesami. Użyj tych typów do synchronizacji wątków w ramach jednej aplikacji.

Niektóre z tych typów są alternatywą dla typów pochodnych <xref:System.Threading.WaitHandle> . Na przykład <xref:System.Threading.SemaphoreSlim> jest lekkim alternatywą dla <xref:System.Threading.Semaphore> .

## <a name="synchronization-of-access-to-a-shared-resource"></a>Synchronizacja dostępu do zasobu udostępnionego

Platforma .NET udostępnia wiele elementów pierwotnych synchronizacji w celu kontrolowania dostępu do zasobu udostępnionego w wielu wątkach.

### <a name="monitor-class"></a>klasa monitora

<xref:System.Threading.Monitor?displayProperty=nameWithType>Klasa przyznaje wzajemnie wyłączny dostęp do zasobu udostępnionego, przejmując lub zwalniając blokadę obiektu, który identyfikuje zasób. Gdy blokada jest utrzymywana, wątek, który przechowuje blokadę, może ponownie uzyskać i zwolnić blokadę. Każdy inny wątek ma zablokowany dostęp do blokady, a <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> Metoda czeka na zwolnienie blokady. <xref:System.Threading.Monitor.Enter%2A>Metoda uzyskuje wydaną blokadę. Można również użyć metody, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> Aby określić czas, w którym wątek próbuje uzyskać blokadę. Ponieważ <xref:System.Threading.Monitor> Klasa ma koligację wątku, wątek, który nabył blokadę, musi zwolnić blokadę, wywołując <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> metodę.

Interakcje wątków, które uzyskują blokadę na tym samym obiekcie, można skoordynować przy <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> użyciu <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> metod, i <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> .

Aby uzyskać więcej informacji, zobacz <xref:System.Threading.Monitor> Informacje o interfejsie API.

> [!NOTE]
> Użyj instrukcji [Lock](../../csharp/language-reference/keywords/lock-statement.md) w języku C# i instrukcji [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) w Visual Basic, aby synchronizować dostęp do zasobu udostępnionego, zamiast bezpośrednio korzystać z <xref:System.Threading.Monitor> klasy. Te instrukcje są implementowane przy użyciu <xref:System.Threading.Monitor.Enter%2A> <xref:System.Threading.Monitor.Exit%2A> metod i bloku, `try…finally` Aby upewnić się, że uzyskana blokada jest zawsze wydawana.

### <a name="mutex-class"></a>Mutex — Klasa

<xref:System.Threading.Mutex?displayProperty=nameWithType>Klasa, taka jak <xref:System.Threading.Monitor> , udziela wyłącznego dostępu do zasobu udostępnionego. Użyj jednego z przeciążeń metody [mutex. WaitOne](<xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>) , aby zażądać własności obiektu mutex. Podobnie jak <xref:System.Threading.Monitor> , <xref:System.Threading.Mutex> ma koligację wątku, a wątek, który uzyskał element mutex, musi zwolnić go przez wywołanie <xref:System.Threading.Mutex.ReleaseMutex%2A?displayProperty=nameWithType> metody.

W przeciwieństwie do <xref:System.Threading.Monitor> , <xref:System.Threading.Mutex> Klasa może być używana do synchronizacji między procesami. W tym celu należy użyć nazwanego obiektu mutex, który jest widoczny w całym systemie operacyjnym. Aby utworzyć nazwane wystąpienie muteksa, należy użyć [konstruktora obiektu mutex](<xref:System.Threading.Mutex.%23ctor%2A>) , który określa nazwę. Możesz również wywołać metodę, <xref:System.Threading.Mutex.OpenExisting%2A?displayProperty=nameWithType> Aby otworzyć istniejący, nazwany element mutex systemu.
  
Aby uzyskać więcej informacji, zobacz artykuł dotyczący [muteksów](mutexes.md) i <xref:System.Threading.Mutex> Informacje o interfejsie API.

### <a name="spinlock-structure"></a>Struktury spinlock, struktura

<xref:System.Threading.SpinLock?displayProperty=nameWithType>Struktura, na przykład <xref:System.Threading.Monitor> , przyznaje wyłączny dostęp do zasobu udostępnionego na podstawie dostępności blokady. Gdy program <xref:System.Threading.SpinLock> próbuje uzyskać blokadę, która jest niedostępna, czeka w pętli, powtarzając sprawdzanie do momentu udostępnienia blokady.

Aby uzyskać więcej informacji na temat korzyści i wad korzystania z blokady pokrętła, zobacz artykuł [struktury spinlock](spinlock.md) i <xref:System.Threading.SpinLock> Informacje o interfejsie API.

### <a name="readerwriterlockslim-class"></a>Klasa ReaderWriterLockSlim

<xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType>Klasa przyznaje wyłączny dostęp do zasobu udostępnionego do zapisu i umożliwia wielu wątkom dostęp do zasobu jednocześnie w celu odczytu. Za pomocą programu można <xref:System.Threading.ReaderWriterLockSlim> synchronizować dostęp do udostępnionej struktury danych, która obsługuje operacje odczytu z bezpiecznymi wątkami, ale wymaga wyłącznego dostępu do wykonywania operacji zapisu. Gdy wątek żąda wyłącznego dostępu (na przykład przez wywołanie <xref:System.Threading.ReaderWriterLockSlim.EnterWriteLock%2A?displayProperty=nameWithType> metody), kolejne żądania czytnika i składnika zapisywania są blokowane, dopóki wszyscy istniejący czytelnicy nie zamknie blokady, a moduł zapisujący przeszedł i zakończył blokadę.
  
Aby uzyskać więcej informacji, zobacz <xref:System.Threading.ReaderWriterLockSlim> Informacje o interfejsie API.

### <a name="semaphore-and-semaphoreslim-classes"></a>Semafory i klasy SemaphoreSlim

<xref:System.Threading.Semaphore?displayProperty=nameWithType>Klasy i <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> ograniczają liczbę wątków, które mogą uzyskiwać dostęp do zasobów udostępnionych lub puli zasobów współbieżnie. Dodatkowe wątki, które żądają zasobu, oczekują do momentu zwolnienia przez wątek semafora. Ponieważ semafor nie ma koligacji wątku, wątek może uzyskać semafor, a inny może go zwolnić.

<xref:System.Threading.SemaphoreSlim> jest lekkim alternatywą <xref:System.Threading.Semaphore> dla i może być używany tylko do synchronizacji w ramach pojedynczej granicy procesu.

W systemie Windows można użyć <xref:System.Threading.Semaphore> do synchronizacji między procesami. W tym celu należy utworzyć <xref:System.Threading.Semaphore> wystąpienie, które reprezentuje nazwany semafor systemowy przy użyciu jednego z [konstruktorów semaforów](<xref:System.Threading.Semaphore.%23ctor%2A>) , który określa nazwę lub <xref:System.Threading.Semaphore.OpenExisting%2A?displayProperty=nameWithType> metodę. <xref:System.Threading.SemaphoreSlim> nie obsługuje nazwanych semaforów systemowych.

Aby uzyskać więcej informacji, zobacz artykuł [Semafor i SemaphoreSlim](semaphore-and-semaphoreslim.md) oraz <xref:System.Threading.Semaphore> <xref:System.Threading.SemaphoreSlim> Dokumentacja interfejsu API lub.

## <a name="thread-interaction-or-signaling"></a>Interakcja wątku lub sygnalizowanie

Interakcja wątku (lub sygnalizacja wątku) oznacza, że wątek musi oczekiwać na powiadomienie lub sygnał z co najmniej jednego wątku, aby można było wykonać operację. Na przykład jeśli wątek A wywołuje <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> metodę wątku b, wątek a jest blokowany do momentu zakończenia wątku b. Elementy pierwotne synchronizacji opisane w poprzedniej sekcji zapewniają inny mechanizm sygnalizowania: przez zwolnienie blokady wątek powiadamia inny wątek, który może wykonać, przez uzyskanie blokady.

W tej sekcji opisano dodatkowe konstrukcje sygnalizujące zapewniane przez platformę .NET.

### <a name="eventwaithandle-autoresetevent-manualresetevent-and-manualreseteventslim-classes"></a>Klasy EventWaitHandle, AutoResetEvent, ManualResetEvent i ManualResetEventSlim

<xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>Klasa reprezentuje zdarzenie synchronizacji wątku.

Zdarzenie synchronizacji może być w stanie "Niesygnalizowane" lub "sygnalizowanie". Gdy stan zdarzenia jest Niesygnalizowane, wątek, który wywołuje Przeciążenie zdarzenia, <xref:System.Threading.WaitHandle.WaitOne%2A?> jest blokowany do momentu zasygnalizowania zdarzenia. <xref:System.Threading.EventWaitHandle.Set%2A?displayProperty=nameWithType>Metoda ustawia stan zdarzenia do sygnalizowania.

Zachowanie <xref:System.Threading.EventWaitHandle> , które zostało zasygnalizowane, zależy od jego trybu resetowania:

- <xref:System.Threading.EventWaitHandle>Utworzony z <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> flagą resetuje się automatycznie po zwolnieniu pojedynczego oczekującego wątku. Jest to wartość, która jest taka sama jak w przypadku jednego wątku, za każdym razem, gdy jest ono sygnalizowane. <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>Klasa, która pochodzi od <xref:System.Threading.EventWaitHandle> , reprezentuje takie zachowanie.
- Element <xref:System.Threading.EventWaitHandle> utworzony przy użyciu <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType> flagi pozostaje zasygnalizowani do momentu <xref:System.Threading.EventWaitHandle.Reset%2A> wywołania metody. Jest on podobny do bramy, która jest zamykana do momentu, gdy zostanie zamknięty, dopóki ktoś jej nie zamknie. <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>Klasa, która pochodzi od <xref:System.Threading.EventWaitHandle> , reprezentuje takie zachowanie. <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>Klasa jest lekkim alternatywą dla <xref:System.Threading.ManualResetEvent> .

W systemie Windows można użyć <xref:System.Threading.EventWaitHandle> do synchronizacji między procesami. W tym celu należy utworzyć <xref:System.Threading.EventWaitHandle> wystąpienie, które reprezentuje nazwane zdarzenie synchronizacji systemu przy użyciu jednego z [konstruktorów EventWaitHandle](<xref:System.Threading.EventWaitHandle.%23ctor%2A>) , który określa nazwę lub <xref:System.Threading.EventWaitHandle.OpenExisting%2A?displayProperty=nameWithType> metodę.

Aby uzyskać więcej informacji, zobacz artykuł [EventWaitHandle](eventwaithandle.md) . Aby uzyskać odwołanie do interfejsu API, zobacz <xref:System.Threading.EventWaitHandle> ,, <xref:System.Threading.AutoResetEvent> <xref:System.Threading.ManualResetEvent> , i <xref:System.Threading.ManualResetEventSlim> .

### <a name="countdownevent-class"></a>Klasa CountdownEvent

<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>Klasa reprezentuje zdarzenie, które zostaje ustawione, gdy jego licznik ma wartość zero. Chociaż <xref:System.Threading.CountdownEvent.CurrentCount?displayProperty=nameWithType> jest większa od zera, wątek, który wywołuje, <xref:System.Threading.CountdownEvent.Wait%2A?displayProperty=nameWithType> jest zablokowany. Wywołaj <xref:System.Threading.CountdownEvent.Signal%2A?displayProperty=nameWithType> , aby zmniejszyć liczbę zdarzeń.

W przeciwieństwie do <xref:System.Threading.ManualResetEvent> lub <xref:System.Threading.ManualResetEventSlim> , którego można użyć do odblokowania wielu wątków z sygnałem z jednego wątku, można użyć, <xref:System.Threading.CountdownEvent> Aby odblokować jeden lub więcej wątków z sygnałami z wielu wątków.

Aby uzyskać więcej informacji, zobacz artykuł [CountdownEvent](countdownevent.md) i <xref:System.Threading.CountdownEvent> Informacje o interfejsie API.

### <a name="barrier-class"></a>Klasa barier

<xref:System.Threading.Barrier?displayProperty=nameWithType>Klasa reprezentuje barierę wykonania wątku. Wątek, który wywołuje <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> metodę sygnalizuje, że osiągnął barierę i czeka, aż inne wątki uczestników osiągnie barierę. Gdy wszystkie wątki uczestników osiągają barierę, stają się one i są resetowane i mogą być używane ponownie.

Można użyć, <xref:System.Threading.Barrier> gdy co najmniej jeden wątek wymaga wyników innych wątków przed przejściem do kolejnej fazy obliczeń.

Aby uzyskać więcej informacji, zobacz artykuł dotyczący [bariery](barrier.md) i <xref:System.Threading.Barrier> Informacje o interfejsie API.

## <a name="interlocked-class"></a>Interlocked — Klasa

<xref:System.Threading.Interlocked?displayProperty=nameWithType>Klasa zawiera metody statyczne, które wykonują proste operacje niepodzielne na zmiennej. Te operacje niepodzielne obejmują dodawanie, zwiększanie i zmniejszanie, wymianę i wymianę warunkową, które są zależne od porównania, i operacji odczytu z 64-bitową wartością całkowitą.

Aby uzyskać więcej informacji, zobacz <xref:System.Threading.Interlocked> Informacje o interfejsie API.

## <a name="spinwait-structure"></a>Metody SpinWait, struktura

<xref:System.Threading.SpinWait?displayProperty=nameWithType>Struktura zapewnia obsługę czekania na grzbiet. Można go użyć, gdy wątek musi oczekiwać na zasygnalizowanie zdarzenia lub spełnienia warunku, ale gdy rzeczywisty czas oczekiwania będzie krótszy niż czas oczekiwania wymagany przy użyciu dojścia oczekiwania lub przez inny blok wątku. Za pomocą <xref:System.Threading.SpinWait> , można określić krótki okres czasu, który ma być obracany podczas oczekiwania, a następnie przekazać (na przykład przez oczekiwanie lub uśpiony) tylko wtedy, gdy warunek nie został spełniony w określonym czasie.

Aby uzyskać więcej informacji, zobacz artykuł [metody SpinWait](spinwait.md) i <xref:System.Threading.SpinWait> Informacje o interfejsie API.

## <a name="see-also"></a>Zobacz też

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Kolekcje bezpieczne wątkowo](../collections/thread-safe/index.md)
- [Wątkowość obiektów i funkcji](threading-objects-and-features.md)
