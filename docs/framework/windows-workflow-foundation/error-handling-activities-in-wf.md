---
title: Obsługa błędów w działaniach w WF
ms.date: 03/30/2017
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
ms.openlocfilehash: 332e16b4c399341151761a4bce2d47198779ad64
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280315"
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="f20c5-102">Obsługa błędów w działaniach w WF</span><span class="sxs-lookup"><span data-stu-id="f20c5-102">Error Handling Activities in WF</span></span>

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="f20c5-103">zapewnia kilka działań dostarczonych przez system do implementowania obsługi błędów i odzyskiwania.</span><span class="sxs-lookup"><span data-stu-id="f20c5-103">provides several system-provided activities for implementing error handling and recovery.</span></span> <span data-ttu-id="f20c5-104">Aby uzyskać więcej informacji, zobacz [wyjątki](exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="f20c5-104">For more information, see [Exceptions](exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="f20c5-105">Działania obsługi błędów</span><span class="sxs-lookup"><span data-stu-id="f20c5-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="f20c5-106">Ponownie generuje ostatni wyjątek zgłoszony z `TryCatch` działania.</span><span class="sxs-lookup"><span data-stu-id="f20c5-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="f20c5-107">Zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="f20c5-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="f20c5-108">Implementuje obsługę wyjątków.</span><span class="sxs-lookup"><span data-stu-id="f20c5-108">Implements exception handling.</span></span>|
