---
title: <services> dla <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 219a05b1-f573-45c9-849b-e86bc373b62f
ms.openlocfilehash: 0bd2219e7d23376d9cf91262eec3942903be6da1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556476"
---
# <a name="services-of-workflowruntime"></a><span data-ttu-id="ff546-102">\<services> dla \<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="ff546-102">\<services> of \<workflowRuntime></span></span>
<span data-ttu-id="ff546-103">Reprezentuje kolekcję usług, które zostaną dodane do <xref:System.Workflow.Runtime.WorkflowRuntime> aparatu.</span><span class="sxs-lookup"><span data-stu-id="ff546-103">Represents a collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="ff546-104">Elementy są typu <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> .</span><span class="sxs-lookup"><span data-stu-id="ff546-104">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="ff546-105">Usługi określone w kolekcji zostaną zainicjowane przez aparat środowiska uruchomieniowego przepływu pracy i dodawane do swoich usług, gdy <xref:System.Workflow.Runtime.WorkflowRuntime> zostanie wywołany odpowiedni Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ff546-105">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="ff546-106">W związku z tym usługi określone w kolekcji muszą przestrzegać pewnych zasad dotyczących podpisów ich konstruktorów.</span><span class="sxs-lookup"><span data-stu-id="ff546-106">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="ff546-107">Aby uzyskać więcej informacji, zobacz <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="ff546-107">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff546-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ff546-108">See also</span></span>

- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="ff546-109">[Pliki konfiguracji przepływu pracy](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ff546-109">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
