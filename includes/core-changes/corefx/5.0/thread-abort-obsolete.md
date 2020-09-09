---
ms.openlocfilehash: 85488de561a2298f2ff4009ec78b9a6e294053f3
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598163"
---
### <a name="threadabort-is-obsolete"></a>Wątek. Abort jest przestarzały

<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>Interfejsy API są przestarzałe. Projekty przeznaczone dla platformy .NET 5,0 lub nowszej będą napotykać ostrzeżenia w czasie kompilacji w przypadku wywołania tych metod. W przypadku pomijania ostrzeżeń <xref:System.PlatformNotSupportedException> zostanie ono zgłoszone w czasie wykonywania.

#### <a name="change-description"></a>Zmień opis

Wcześniej wywołania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> nie wygenerowały ostrzeżeń dotyczących czasu kompilacji, jednak Metoda zgłosiła <xref:System.PlatformNotSupportedException> w czasie wykonywania.

Począwszy od platformy .NET 5,0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> jest oznaczone jako przestarzałe jako ostrzeżenie. Wywołanie tej metody powoduje wygenerowanie ostrzeżenia kompilatora `SYSLIB0006` . Implementacja metody jest niezmieniona i nadal generuje <xref:System.PlatformNotSupportedException> .

#### <a name="reason-for-change"></a>Przyczyna zmiany

Uwzględniając, że <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> zawsze zgłasza <xref:System.PlatformNotSupportedException> wszystkie implementacje .NET, z wyjątkiem .NET Framework, <xref:System.ObsoleteAttribute> zostało dodane do metody w celu zwrócenia uwagi do miejsc, w których jest wywoływana.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC 1

#### <a name="recommended-action"></a>Zalecana akcja

- Użyj, <xref:System.Threading.CancellationToken> Aby przerwać przetwarzanie jednostki pracy zamiast wywoływania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> . Poniższy przykład ilustruje użycie <xref:System.Threading.CancellationToken> .

  ```csharp
  void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
  {
      if (QueryIsMoreWorkPending())
      {
          // If the CancellationToken is marked as "needs to cancel",
          // this will throw the appropriate exception.
          cancellationToken.ThrowIfCancellationRequested();

          WorkItem work = DequeueWorkItem();
          ProcessWorkItem(work);
      }
  }
  ```

  Aby uzyskać więcej informacji, zobacz [Anulowanie w zarządzanych wątkach](../../../../docs/standard/threading/cancellation-in-managed-threads.md).

- Aby pominąć ostrzeżenie w czasie kompilacji, Pomiń kod ostrzegawczy `SYSLIB0006` . Kod ostrzegawczy jest specyficzny dla <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> i pomijany, nie pomija innych ostrzeżeń obsoletion w kodzie. Zaleca się jednak, aby usunąć wywołania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> zamiast pomijania ostrzeżenia.

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  Możesz również pominąć ostrzeżenie w pliku projektu.

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

#### <a name="category"></a>Kategoria

- Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
