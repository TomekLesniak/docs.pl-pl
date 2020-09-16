---
ms.openlocfilehash: 1f85b1ce95ca07329aff77af4ec894622e0818d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606616"
---
### <a name="workflow-30-types-are-obsolete"></a><span data-ttu-id="e2f9b-101">Typy przepływów pracy w wersji 3.0 są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="e2f9b-101">WorkFlow 3.0 types are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="e2f9b-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="e2f9b-102">Details</span></span>

<span data-ttu-id="e2f9b-103">Interfejsy API programu Windows Workflow Foundation (WWF) 3.0 (te z przestrzeni nazw System.Workflow) są obecnie przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-103">Windows Workflow Foundation (WWF) 3.0 APIs (those from the System.Workflow namespace) are now obsolete.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e2f9b-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="e2f9b-104">Suggestion</span></span>

<span data-ttu-id="e2f9b-105">Zamiast nich należy używać nowych interfejsów API programu WWF 4.0 (w System.Activities).</span><span class="sxs-lookup"><span data-stu-id="e2f9b-105">New WWF 4.0 APIs (in System.Activities) should be used instead.</span></span> <span data-ttu-id="e2f9b-106">Przykład korzystania z nowych interfejsów API można znaleźć [tutaj](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), a dalsze wskazówki są dostępne [tutaj](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span><span class="sxs-lookup"><span data-stu-id="e2f9b-106">An example of using the new APIs can be found [here](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) and further guidance is available [here](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span></span> <span data-ttu-id="e2f9b-107">Ponieważ interfejsy API WWF 3.0 są nadal obsługiwane, alternatywnym rozwiązaniem może być używanie ich i pominięcie ostrzeżenia podczas kompilacji lub użycie starszego kompilatora.</span><span class="sxs-lookup"><span data-stu-id="e2f9b-107">Alternatively, since the WWF 3.0 APIs are still supported, they may be used and the build-time warning avoided either by suppressing it or by using an older compiler.</span></span>

| <span data-ttu-id="e2f9b-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="e2f9b-108">Name</span></span>    | <span data-ttu-id="e2f9b-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="e2f9b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e2f9b-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="e2f9b-110">Scope</span></span>   | <span data-ttu-id="e2f9b-111">Duży</span><span class="sxs-lookup"><span data-stu-id="e2f9b-111">Major</span></span>       |
| <span data-ttu-id="e2f9b-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="e2f9b-112">Version</span></span> | <span data-ttu-id="e2f9b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="e2f9b-113">4.5</span></span>         |
| <span data-ttu-id="e2f9b-114">Typ</span><span class="sxs-lookup"><span data-stu-id="e2f9b-114">Type</span></span>    | <span data-ttu-id="e2f9b-115">Przekierowanie</span><span class="sxs-lookup"><span data-stu-id="e2f9b-115">Retargeting</span></span> |
