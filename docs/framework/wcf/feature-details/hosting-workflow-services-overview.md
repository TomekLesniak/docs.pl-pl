---
title: Przegląd hostowania usług przepływu pracy
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: 150cb98ab3cef8231489219a16709344cbd19bd5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242971"
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="9b124-102">Przegląd hostowania usług przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="9b124-102">Hosting Workflow Services Overview</span></span>

<span data-ttu-id="9b124-103">Usługi przepływu pracy muszą być hostowane do wykonania.</span><span class="sxs-lookup"><span data-stu-id="9b124-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="9b124-104"><xref:System.ServiceModel.WorkflowServiceHost>Jest hostem przepływu pracy, który obsługuje wiele wystąpień, konfiguracji i komunikatów WCF (chociaż przepływy pracy nie są wymagane do obsługi komunikatów, aby można było je obsługiwać).</span><span class="sxs-lookup"><span data-stu-id="9b124-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="9b124-105">Integruje się ona również z zachowaniem trwałości, śledzenia i kontroli wystąpienia za pomocą zestawu zachowań usługi.</span><span class="sxs-lookup"><span data-stu-id="9b124-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="9b124-106">Podobnie jak w przypadku platformy WCF <xref:System.ServiceModel.ServiceHost> , <xref:System.ServiceModel.WorkflowServiceHost> może być samodzielny w dowolnej zarządzanej aplikacji .NET lub hostowanej w sieci Web (jako plik. xamlx) w usługach IIS/was.</span><span class="sxs-lookup"><span data-stu-id="9b124-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="9b124-107">W tematach w tej sekcji opisano sposób hostowania usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="9b124-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9b124-108">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="9b124-108">In This Section</span></span>  

 [<span data-ttu-id="9b124-109">Hostowanie usług przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="9b124-109">Hosting Workflow Services</span></span>](hosting-workflow-services.md)  
 <span data-ttu-id="9b124-110">Opisuje hostowanie usług przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="9b124-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="9b124-111">Elementy wewnętrzne hosta usługi przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="9b124-111">Workflow Service Host Internals</span></span>](workflow-service-host-internals.md)  
 <span data-ttu-id="9b124-112">Opisuje sposób <xref:System.ServiceModel.WorkflowServiceHost> przetwarzania komunikatów przychodzących.</span><span class="sxs-lookup"><span data-stu-id="9b124-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="9b124-113">Rozszerzalność hosta usługi przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="9b124-113">Workflow Service Host Extensibility</span></span>](workflow-service-host-extensibility.md)  
 <span data-ttu-id="9b124-114">Opisuje sposób rozszerania funkcji hosta usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="9b124-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="9b124-115">Punkt końcowy kontroli przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="9b124-115">Workflow Control Endpoint</span></span>](workflow-control-endpoint.md)  
 <span data-ttu-id="9b124-116">Opisuje sposób definiowania punktu końcowego, który umożliwia tworzenie wystąpień przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="9b124-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>
  
 [<span data-ttu-id="9b124-117">Instrukcje: hostowanie usługi przepływu pracy przy użyciu rozwiązania AppFabric w systemie Windows Server</span><span class="sxs-lookup"><span data-stu-id="9b124-117">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="9b124-118">Demonstruje sposób hostowania istniejącej usługi przepływu pracy w sieci szkieletowej aplikacji systemu Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9b124-118">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="9b124-119">Konfigurowanie elementu WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="9b124-119">Configuring WorkflowServiceHost</span></span>](configuring-workflowservicehost.md)  
 <span data-ttu-id="9b124-120">Opisuje sposób kontrolowania zachowania trwałości, śledzenia, bezczynności i nieobsłużonego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="9b124-120">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9b124-121">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="9b124-121">Reference</span></span>  

 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="9b124-122">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="9b124-122">Related Sections</span></span>  

 [<span data-ttu-id="9b124-123">Usługi przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="9b124-123">Workflow Services</span></span>](workflow-services.md)
