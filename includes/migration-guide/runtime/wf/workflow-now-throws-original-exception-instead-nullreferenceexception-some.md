---
ms.openlocfilehash: 61d5885c19e39b138090c1a98fa26348724893c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496858"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a>Przepływ pracy teraz zgłasza oryginalny wyjątek zamiast NullReferenceException w niektórych przypadkach

#### <a name="details"></a>Szczegóły

W .NET Framework 4.6.2 i starszych wersjach, gdy metoda Execute działania przepływu pracy zgłasza wyjątek z <code>null</code> wartością <xref:System.Exception.Message> właściwości, środowisko uruchomieniowe przepływu pracy system. Activities generuje <xref:System.NullReferenceException?displayProperty=fullName> , maskowanie oryginalnego wyjątku. W .NET Framework 4,7 został zgłoszony poprzednio zamaskowany wyjątek.

#### <a name="suggestion"></a>Sugestia

Jeśli Twój kod opiera się na obsłudze <xref:System.NullReferenceException?displayProperty=fullName> , zmień go, aby przechwytywać wyjątki, które mogą zostać zgłoszone przez działania niestandardowe.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4,7|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

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
