---
ms.openlocfilehash: 61d5885c19e39b138090c1a98fa26348724893c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496858"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="43683-101">Przepływ pracy teraz zgłasza oryginalny wyjątek zamiast NullReferenceException w niektórych przypadkach</span><span class="sxs-lookup"><span data-stu-id="43683-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="43683-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="43683-102">Details</span></span>

<span data-ttu-id="43683-103">W .NET Framework 4.6.2 i starszych wersjach, gdy metoda Execute działania przepływu pracy zgłasza wyjątek z <code>null</code> wartością <xref:System.Exception.Message> właściwości, środowisko uruchomieniowe przepływu pracy system. Activities generuje <xref:System.NullReferenceException?displayProperty=fullName> , maskowanie oryginalnego wyjątku. W .NET Framework 4,7 został zgłoszony poprzednio zamaskowany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="43683-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="43683-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="43683-104">Suggestion</span></span>

<span data-ttu-id="43683-105">Jeśli Twój kod opiera się na obsłudze <xref:System.NullReferenceException?displayProperty=fullName> , zmień go, aby przechwytywać wyjątki, które mogą zostać zgłoszone przez działania niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="43683-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="43683-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="43683-106">Name</span></span>    | <span data-ttu-id="43683-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="43683-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="43683-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="43683-108">Scope</span></span>   |<span data-ttu-id="43683-109">Mały</span><span class="sxs-lookup"><span data-stu-id="43683-109">Minor</span></span>|
|<span data-ttu-id="43683-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="43683-110">Version</span></span>|<span data-ttu-id="43683-111">4,7</span><span class="sxs-lookup"><span data-stu-id="43683-111">4.7</span></span>|
|<span data-ttu-id="43683-112">Typ</span><span class="sxs-lookup"><span data-stu-id="43683-112">Type</span></span>|<span data-ttu-id="43683-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="43683-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="43683-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="43683-114">Affected APIs</span></span>

- <xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)`
- `M:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)`
- ``M:System.Activities.AsyncCodeActivity`1.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)``
- `M:System.Activities.WorkflowInvoker.Invoke`

-->
