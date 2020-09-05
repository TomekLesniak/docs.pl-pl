---
ms.openlocfilehash: a806107456a65a4919592da9535a2617f677cfe0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496474"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a><span data-ttu-id="0ac01-101">Funkcja WPF DispatcherSynchronizationContext. setcopy zwraca teraz nową kopię zamiast bieżącego wystąpienia</span><span class="sxs-lookup"><span data-stu-id="0ac01-101">WPF DispatcherSynchronizationContext.CreateCopy now returns a new copy instead of the current instance</span></span>

#### <a name="details"></a><span data-ttu-id="0ac01-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="0ac01-102">Details</span></span>

<span data-ttu-id="0ac01-103">W .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> zwrócił odwołanie do bieżącego wystąpienia, głównie jako Optymalizacja wydajności.</span><span class="sxs-lookup"><span data-stu-id="0ac01-103">In the .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> returned a reference to the current instance, primarily as a performance optimization.</span></span> <span data-ttu-id="0ac01-104">W .NET Framework 4,5 zwraca nowe wystąpienie, które umożliwia po raz pierwszy zawrzeć te same odwołania wskazujące wykonywany wątek znajduje się w poprawnym kontekście synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="0ac01-104">In the .NET Framework 4.5, it returns a new instance which makes it possible for the first time to conclude that equal references indicate the executing thread is in the correct synchronization context.</span></span>  <span data-ttu-id="0ac01-105">Jest mało prawdopodobne, że kod, który sprawdza tożsamość tych odwołań, będzie dotyczył, ale ze względu na zmianę, kod, który wywołuje, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> powinien być testowany w ramach migracji do .NET Framework 4,5 lub nowszego.</span><span class="sxs-lookup"><span data-stu-id="0ac01-105">It is unlikely that code that checks the identity of these references will be affected, but because of the change, code that calls <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> should be tested as part of migration to the .NET Framework 4.5 or newer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0ac01-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="0ac01-106">Suggestion</span></span>

<span data-ttu-id="0ac01-107">Należy pamiętać, że <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> program zwróci teraz nowy <xref:System.Threading.SynchronizationContext?displayProperty=fullName> obiekt.</span><span class="sxs-lookup"><span data-stu-id="0ac01-107">Be aware that <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> will now return a new <xref:System.Threading.SynchronizationContext?displayProperty=fullName> object.</span></span> <span data-ttu-id="0ac01-108">Wcześniej kod, który używał równoważności odwołań, wygenerował w ten sposób, nie sprawdza, czy znajdował się w odpowiednim kontekście, ale jest zbudowany w oparciu o .NET Framework 4,5 lub nowszy.</span><span class="sxs-lookup"><span data-stu-id="0ac01-108">Previously, code that used equivalence of references generated this way was not actually checking whether it was in the proper context, but does when built against .NET Framework 4.5 or later.</span></span>  <span data-ttu-id="0ac01-109">Chociaż mało prawdopodobne, aby powodować problemy, wykonywanie odpowiednich ścieżek kodu powinno być wystarczające, aby określić, czy stanowi to problem.</span><span class="sxs-lookup"><span data-stu-id="0ac01-109">While unlikely to cause issues, exercising the affected code paths should be enough to determine if this poses any problem.</span></span>

| <span data-ttu-id="0ac01-110">Nazwa</span><span class="sxs-lookup"><span data-stu-id="0ac01-110">Name</span></span>    | <span data-ttu-id="0ac01-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="0ac01-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0ac01-112">Zakres</span><span class="sxs-lookup"><span data-stu-id="0ac01-112">Scope</span></span>   |<span data-ttu-id="0ac01-113">Mały</span><span class="sxs-lookup"><span data-stu-id="0ac01-113">Minor</span></span>|
|<span data-ttu-id="0ac01-114">Wersja</span><span class="sxs-lookup"><span data-stu-id="0ac01-114">Version</span></span>|<span data-ttu-id="0ac01-115">4.5</span><span class="sxs-lookup"><span data-stu-id="0ac01-115">4.5</span></span>|
|<span data-ttu-id="0ac01-116">Typ</span><span class="sxs-lookup"><span data-stu-id="0ac01-116">Type</span></span>|<span data-ttu-id="0ac01-117">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="0ac01-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0ac01-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="0ac01-118">Affected APIs</span></span>

- <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy`

-->
