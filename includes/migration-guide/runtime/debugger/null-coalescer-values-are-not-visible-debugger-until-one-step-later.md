---
ms.openlocfilehash: af8de731ee93d0bfb01042d894f5730570dcdd78
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497848"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="6f891-101">Wartości parametrów łączenia wartości null nie są widoczne w debugerze, dopóki nie zostanie później jeden krok</span><span class="sxs-lookup"><span data-stu-id="6f891-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="6f891-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="6f891-102">Details</span></span>

<span data-ttu-id="6f891-103">Usterka w .NET Framework 4,5 powoduje, że wartości ustawione za pośrednictwem operacji łączenia zerowego nie będą widoczne w debugerze natychmiast po wykonaniu operacji przypisania w przypadku uruchamiania w wersji 64-bitowej struktury.</span><span class="sxs-lookup"><span data-stu-id="6f891-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6f891-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="6f891-104">Suggestion</span></span>

<span data-ttu-id="6f891-105">Przechodzenie po jednym dodatkowym czasie w debugerze spowoduje, że wartość lokalna/pole zostanie prawidłowo zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="6f891-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="6f891-106">Ten problem został również rozwiązany w .NET Framework 4,6; uaktualnienie do tej wersji środowiska powinno rozwiązać problem.</span><span class="sxs-lookup"><span data-stu-id="6f891-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="6f891-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="6f891-107">Name</span></span>    | <span data-ttu-id="6f891-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="6f891-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6f891-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="6f891-109">Scope</span></span>   |<span data-ttu-id="6f891-110">Edge</span><span class="sxs-lookup"><span data-stu-id="6f891-110">Edge</span></span>|
|<span data-ttu-id="6f891-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="6f891-111">Version</span></span>|<span data-ttu-id="6f891-112">4.5</span><span class="sxs-lookup"><span data-stu-id="6f891-112">4.5</span></span>|
|<span data-ttu-id="6f891-113">Typ</span><span class="sxs-lookup"><span data-stu-id="6f891-113">Type</span></span>|<span data-ttu-id="6f891-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="6f891-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6f891-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="6f891-115">Affected APIs</span></span>

<span data-ttu-id="6f891-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="6f891-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
