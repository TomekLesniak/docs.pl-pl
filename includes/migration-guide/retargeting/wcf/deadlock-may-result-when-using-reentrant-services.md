---
ms.openlocfilehash: f61cf21f9f30662cc8e383bb3aeb5c642f1665b8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497936"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a><span data-ttu-id="30c1c-101">Zakleszczenie może wynikać z używania usług współużytkowanych</span><span class="sxs-lookup"><span data-stu-id="30c1c-101">Deadlock may result when using Reentrant services</span></span>

#### <a name="details"></a><span data-ttu-id="30c1c-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="30c1c-102">Details</span></span>

<span data-ttu-id="30c1c-103">Zakleszczenie może skutkować usługą współużytkowaną, która ogranicza wystąpienia usługi do jednego wątku wykonywania w danym momencie.</span><span class="sxs-lookup"><span data-stu-id="30c1c-103">A deadlock may result in a Reentrant service, which restricts instances of the service to one thread of execution at a time.</span></span> <span data-ttu-id="30c1c-104">Usługi podatne na wystąpienie tego problemu będą miały następujące <xref:System.ServiceModel.ServiceBehaviorAttribute> kody:</span><span class="sxs-lookup"><span data-stu-id="30c1c-104">Services prone to encounter this problem will have the following <xref:System.ServiceModel.ServiceBehaviorAttribute> in their code:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a><span data-ttu-id="30c1c-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="30c1c-105">Suggestion</span></span>

<span data-ttu-id="30c1c-106">Aby rozwiązać ten problem, można wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="30c1c-106">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="30c1c-107">Ustaw tryb współbieżności usługi na <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> lub <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="30c1c-107">Set the service's concurrency mode to <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> or <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType>.</span></span> <span data-ttu-id="30c1c-108">Przykład:</span><span class="sxs-lookup"><span data-stu-id="30c1c-108">For example:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- <span data-ttu-id="30c1c-109">Zainstaluj najnowszą aktualizację do .NET Framework 4.6.2 lub Uaktualnij do nowszej wersji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="30c1c-109">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="30c1c-110">Spowoduje to wyłączenie przepływu <xref:System.Threading.ExecutionContext> w programie <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="30c1c-110">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span></span> <span data-ttu-id="30c1c-111">To zachowanie można skonfigurować. jest to równoznaczne z dodaniem do pliku konfiguracji następującego ustawienia aplikacji:</span><span class="sxs-lookup"><span data-stu-id="30c1c-111">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

<span data-ttu-id="30c1c-112">Wartość `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` nie powinna być nigdy ustawiona na `false` dla usług współużytkowanych.</span><span class="sxs-lookup"><span data-stu-id="30c1c-112">The value of `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` should never be set to `false` for Reentrant services.</span></span>

| <span data-ttu-id="30c1c-113">Nazwa</span><span class="sxs-lookup"><span data-stu-id="30c1c-113">Name</span></span>    | <span data-ttu-id="30c1c-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="30c1c-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="30c1c-115">Zakres</span><span class="sxs-lookup"><span data-stu-id="30c1c-115">Scope</span></span>   | <span data-ttu-id="30c1c-116">Mały</span><span class="sxs-lookup"><span data-stu-id="30c1c-116">Minor</span></span>       |
| <span data-ttu-id="30c1c-117">Wersja</span><span class="sxs-lookup"><span data-stu-id="30c1c-117">Version</span></span> | <span data-ttu-id="30c1c-118">4.6.2</span><span class="sxs-lookup"><span data-stu-id="30c1c-118">4.6.2</span></span>       |
| <span data-ttu-id="30c1c-119">Typ</span><span class="sxs-lookup"><span data-stu-id="30c1c-119">Type</span></span>    | <span data-ttu-id="30c1c-120">Przekierowanie</span><span class="sxs-lookup"><span data-stu-id="30c1c-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="30c1c-121">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="30c1c-121">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
