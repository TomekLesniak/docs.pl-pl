---
title: 'Istotna zmiana: Thread. Abort jest przestarzały'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których interfejsy API wątku. Abort są przestarzałe.
ms.date: 11/01/2020
ms.openlocfilehash: 6d7dfce8fda393bfd88c9b4cf0c59d53942cee25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761384"
---
# <a name="threadabort-is-obsolete"></a><span data-ttu-id="36954-103">Wątek. Abort jest przestarzały</span><span class="sxs-lookup"><span data-stu-id="36954-103">Thread.Abort is obsolete</span></span>

<span data-ttu-id="36954-104"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>Interfejsy API są przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="36954-104">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="36954-105">Projekty przeznaczone dla platformy .NET 5,0 lub nowszej będą napotykać ostrzeżenie w czasie kompilacji w `SYSLIB0006` przypadku wywołania tych metod.</span><span class="sxs-lookup"><span data-stu-id="36954-105">Projects that target .NET 5.0 or a later version will encounter compile-time warning `SYSLIB0006` if these methods are called.</span></span>

## <a name="change-description"></a><span data-ttu-id="36954-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="36954-106">Change description</span></span>

<span data-ttu-id="36954-107">Wcześniej wywołania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> nie wygenerowały ostrzeżeń dotyczących czasu kompilacji, jednak Metoda zgłosiła <xref:System.PlatformNotSupportedException> w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="36954-107">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="36954-108">Począwszy od platformy .NET 5,0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> jest oznaczone jako przestarzałe jako ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="36954-108">Starting in .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="36954-109">Wywołanie tej metody powoduje wygenerowanie ostrzeżenia kompilatora `SYSLIB0006` .</span><span class="sxs-lookup"><span data-stu-id="36954-109">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="36954-110">Implementacja metody jest niezmieniona i nadal generuje <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="36954-110">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="36954-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="36954-111">Reason for change</span></span>

<span data-ttu-id="36954-112">Uwzględniając, że <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> zawsze zgłasza <xref:System.PlatformNotSupportedException> wszystkie implementacje .NET, z wyjątkiem .NET Framework, <xref:System.ObsoleteAttribute> zostało dodane do metody w celu zwrócenia uwagi do miejsc, w których jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="36954-112">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="36954-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="36954-113">Version introduced</span></span>

<span data-ttu-id="36954-114">5,0</span><span class="sxs-lookup"><span data-stu-id="36954-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="36954-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="36954-115">Recommended action</span></span>

- <span data-ttu-id="36954-116">Użyj, <xref:System.Threading.CancellationToken> Aby przerwać przetwarzanie jednostki pracy zamiast wywoływania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36954-116">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="36954-117">Poniższy przykład ilustruje użycie <xref:System.Threading.CancellationToken> .</span><span class="sxs-lookup"><span data-stu-id="36954-117">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

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

  <span data-ttu-id="36954-118">Aby uzyskać więcej informacji, zobacz [Anulowanie w zarządzanych wątkach](../../../../standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="36954-118">For more information, see [Cancellation in managed threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="36954-119">Aby pominąć ostrzeżenie w czasie kompilacji, Pomiń kod ostrzegawczy `SYSLIB0006` .</span><span class="sxs-lookup"><span data-stu-id="36954-119">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="36954-120">Kod ostrzegawczy jest specyficzny dla <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> i pomijany, nie pomija innych ostrzeżeń obsoletion w kodzie.</span><span class="sxs-lookup"><span data-stu-id="36954-120">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="36954-121">Zaleca się jednak, aby usunąć wywołania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> zamiast pomijania ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="36954-121">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="36954-122">Możesz również pominąć ostrzeżenie w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="36954-122">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

## <a name="affected-apis"></a><span data-ttu-id="36954-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="36954-123">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
