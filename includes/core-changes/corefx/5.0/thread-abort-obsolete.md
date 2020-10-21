---
ms.openlocfilehash: ee67b32b093ebd42f8ac685b34b12f2f6833be86
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332934"
---
### <a name="threadabort-is-obsolete"></a><span data-ttu-id="d0cea-101">Wątek. Abort jest przestarzały</span><span class="sxs-lookup"><span data-stu-id="d0cea-101">Thread.Abort is obsolete</span></span>

<span data-ttu-id="d0cea-102"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>Interfejsy API są przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d0cea-102">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="d0cea-103">Projekty przeznaczone dla platformy .NET 5,0 lub nowszej będą napotykać ostrzeżenie w czasie kompilacji w `SYSLIB0006` przypadku wywołania tych metod.</span><span class="sxs-lookup"><span data-stu-id="d0cea-103">Projects that target .NET 5.0 or a later version will encounter compile-time warning `SYSLIB0006` if these methods are called.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d0cea-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="d0cea-104">Change description</span></span>

<span data-ttu-id="d0cea-105">Wcześniej wywołania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> nie wygenerowały ostrzeżeń dotyczących czasu kompilacji, jednak Metoda zgłosiła <xref:System.PlatformNotSupportedException> w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="d0cea-105">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="d0cea-106">Począwszy od platformy .NET 5,0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> jest oznaczone jako przestarzałe jako ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="d0cea-106">Starting in .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="d0cea-107">Wywołanie tej metody powoduje wygenerowanie ostrzeżenia kompilatora `SYSLIB0006` .</span><span class="sxs-lookup"><span data-stu-id="d0cea-107">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="d0cea-108">Implementacja metody jest niezmieniona i nadal generuje <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="d0cea-108">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d0cea-109">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="d0cea-109">Reason for change</span></span>

<span data-ttu-id="d0cea-110">Uwzględniając, że <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> zawsze zgłasza <xref:System.PlatformNotSupportedException> wszystkie implementacje .NET, z wyjątkiem .NET Framework, <xref:System.ObsoleteAttribute> zostało dodane do metody w celu zwrócenia uwagi do miejsc, w których jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="d0cea-110">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d0cea-111">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="d0cea-111">Version introduced</span></span>

<span data-ttu-id="d0cea-112">5,0 RC 1</span><span class="sxs-lookup"><span data-stu-id="d0cea-112">5.0 RC 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d0cea-113">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="d0cea-113">Recommended action</span></span>

- <span data-ttu-id="d0cea-114">Użyj, <xref:System.Threading.CancellationToken> Aby przerwać przetwarzanie jednostki pracy zamiast wywoływania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="d0cea-114">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d0cea-115">Poniższy przykład ilustruje użycie <xref:System.Threading.CancellationToken> .</span><span class="sxs-lookup"><span data-stu-id="d0cea-115">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

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

  <span data-ttu-id="d0cea-116">Aby uzyskać więcej informacji, zobacz [Anulowanie w zarządzanych wątkach](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="d0cea-116">For more information, see [Cancellation in managed threads](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="d0cea-117">Aby pominąć ostrzeżenie w czasie kompilacji, Pomiń kod ostrzegawczy `SYSLIB0006` .</span><span class="sxs-lookup"><span data-stu-id="d0cea-117">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="d0cea-118">Kod ostrzegawczy jest specyficzny dla <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> i pomijany, nie pomija innych ostrzeżeń obsoletion w kodzie.</span><span class="sxs-lookup"><span data-stu-id="d0cea-118">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="d0cea-119">Zaleca się jednak, aby usunąć wywołania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> zamiast pomijania ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="d0cea-119">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="d0cea-120">Możesz również pominąć ostrzeżenie w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="d0cea-120">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="d0cea-121">Kategoria</span><span class="sxs-lookup"><span data-stu-id="d0cea-121">Category</span></span>

- <span data-ttu-id="d0cea-122">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="d0cea-122">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d0cea-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d0cea-123">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
