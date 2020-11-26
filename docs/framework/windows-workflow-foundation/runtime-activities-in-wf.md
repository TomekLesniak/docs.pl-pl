---
title: Działania środowiska uruchomieniowego w programie WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: b0472c669d69d9397843a004bee1bb2c15e139c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245707"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="154ba-102">Działania środowiska uruchomieniowego w programie WF</span><span class="sxs-lookup"><span data-stu-id="154ba-102">Runtime Activities in WF</span></span>

[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="154ba-103">zapewnia kilka działań dostarczonych przez system do uzyskiwania dostępu do funkcji środowiska uruchomieniowego przepływu pracy, takich jak trwałość i zakończenie.</span><span class="sxs-lookup"><span data-stu-id="154ba-103">provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="154ba-104">Działanie</span><span class="sxs-lookup"><span data-stu-id="154ba-104">Activity</span></span>|<span data-ttu-id="154ba-105">Opis</span><span class="sxs-lookup"><span data-stu-id="154ba-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="154ba-106">Jawnie żądania są utrwalane przez przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="154ba-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="154ba-107">Kończy uruchomione wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="154ba-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="154ba-108">Działanie kontenera, które uniemożliwia utrwalanie działań podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="154ba-108">A container activity that prevents child activities from persisting.</span></span>|
