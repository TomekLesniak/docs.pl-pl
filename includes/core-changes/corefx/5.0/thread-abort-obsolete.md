---
ms.openlocfilehash: 85488de561a2298f2ff4009ec78b9a6e294053f3
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598163"
---
### <a name="threadabort-is-obsolete"></a><span data-ttu-id="f6fcb-101">Wątek. Abort jest przestarzały</span><span class="sxs-lookup"><span data-stu-id="f6fcb-101">Thread.Abort is obsolete</span></span>

<span data-ttu-id="f6fcb-102"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>Interfejsy API są przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="f6fcb-102">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="f6fcb-103">Projekty przeznaczone dla platformy .NET 5,0 lub nowszej będą napotykać ostrzeżenia w czasie kompilacji w przypadku wywołania tych metod.</span><span class="sxs-lookup"><span data-stu-id="f6fcb-103">Projects that target .NET 5.0 or a later version will encounter compile-time warnings if these methods are called.</span></span> <span data-ttu-id="f6fcb-104">W przypadku pomijania ostrzeżeń <xref:System.PlatformNotSupportedException> zostanie ono zgłoszone w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="f6fcb-104">If you suppress the warnings, a <xref:System.PlatformNotSupportedException> will be thrown at run time.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f6fcb-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="f6fcb-105">Change description</span></span>

<span data-ttu-id="f6fcb-106">Wcześniej wywołania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> nie wygenerowały ostrzeżeń dotyczących czasu kompilacji, jednak Metoda zgłosiła <xref:System.PlatformNotSupportedException> w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="f6fcb-106">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="f6fcb-107">Począwszy od platformy .NET 5,0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> jest oznaczone jako przestarzałe jako ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="f6fcb-107">Starting in .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="f6fcb-108">Wywołanie tej metody powoduje wygenerowanie ostrzeżenia kompilatora `SYSLIB0006` .</span><span class="sxs-lookup"><span data-stu-id="f6fcb-108">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="f6fcb-109">Implementacja metody jest niezmieniona i nadal generuje <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="f6fcb-109">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f6fcb-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="f6fcb-110">Reason for change</span></span>

<span data-ttu-id="f6fcb-111">Uwzględniając, że <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> zawsze zgłasza <xref:System.PlatformNotSupportedException> wszystkie implementacje .NET, z wyjątkiem .NET Framework, <xref:System.ObsoleteAttribute> zostało dodane do metody w celu zwrócenia uwagi do miejsc, w których jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="f6fcb-111">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f6fcb-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="f6fcb-112">Version introduced</span></span>

<span data-ttu-id="f6fcb-113">5,0 RC 1</span><span class="sxs-lookup"><span data-stu-id="f6fcb-113">5.0 RC 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f6fcb-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="f6fcb-114">Recommended action</span></span>

- <span data-ttu-id="f6fcb-115">Użyj, <xref:System.Threading.CancellationToken> Aby przerwać przetwarzanie jednostki pracy zamiast wywoływania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f6fcb-115">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f6fcb-116">Poniższy przykład ilustruje użycie <xref:System.Threading.CancellationToken> .</span><span class="sxs-lookup"><span data-stu-id="f6fcb-116">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

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

  <span data-ttu-id="f6fcb-117">Aby uzyskać więcej informacji, zobacz [Anulowanie w zarządzanych wątkach](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="f6fcb-117">For more information, see [Cancellation in managed threads](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="f6fcb-118">Aby pominąć ostrzeżenie w czasie kompilacji, Pomiń kod ostrzegawczy `SYSLIB0006` .</span><span class="sxs-lookup"><span data-stu-id="f6fcb-118">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="f6fcb-119">Kod ostrzegawczy jest specyficzny dla <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> i pomijany, nie pomija innych ostrzeżeń obsoletion w kodzie.</span><span class="sxs-lookup"><span data-stu-id="f6fcb-119">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="f6fcb-120">Zaleca się jednak, aby usunąć wywołania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> zamiast pomijania ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="f6fcb-120">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="f6fcb-121">Możesz również pominąć ostrzeżenie w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="f6fcb-121">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="f6fcb-122">Kategoria</span><span class="sxs-lookup"><span data-stu-id="f6fcb-122">Category</span></span>

- <span data-ttu-id="f6fcb-123">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="f6fcb-123">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f6fcb-124">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f6fcb-124">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
