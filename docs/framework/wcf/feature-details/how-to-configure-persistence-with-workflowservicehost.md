---
title: 'Instrukcje: konfigurowanie trwałości za pomocą elementu WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 93397923154d780ed3b714bf0bb95c15bc71bbfb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556313"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="79051-102">Instrukcje: konfigurowanie trwałości za pomocą elementu WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="79051-102">How to: Configure Persistence with WorkflowServiceHost</span></span>
<span data-ttu-id="79051-103">W tym temacie opisano sposób konfigurowania funkcji magazynu wystąpień przepływu pracy SQL w celu włączenia trwałości dla przepływów pracy hostowanych w programie przy <xref:System.ServiceModel.Activities.WorkflowServiceHost> użyciu pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="79051-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="79051-104">Przed użyciem funkcji magazynu wystąpień przepływu pracy SQL należy utworzyć bazę danych SQL, która jest używana do utrwalania wystąpień przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="79051-104">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="79051-105">Aby uzyskać więcej informacji, zobacz [How to: Enable SQL trwałości dla przepływów pracy i usług przepływu pracy](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="79051-105">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="79051-106">Aby skonfigurować magazyn wystąpień przepływu pracy SQL w konfiguracji</span><span class="sxs-lookup"><span data-stu-id="79051-106">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1. <span data-ttu-id="79051-107">Właściwości magazynu wystąpień przepływu pracy SQL można skonfigurować przy użyciu <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> zachowania usługi, które umożliwia zmianę ustawień za pomocą konfiguracji XML.</span><span class="sxs-lookup"><span data-stu-id="79051-107">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="79051-108">Poniższy przykład konfiguracji pokazuje, jak skonfigurować magazyn wystąpień przepływu pracy SQL przy użyciu `sqlWorkflowInstanceStore` elementu <> zachowanie w pliku konfiguracyjnym.</span><span class="sxs-lookup"><span data-stu-id="79051-108">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"
                 runnableInstancesDetectionPeriod="00:00:05">  
            </sqlWorkflowInstanceStore>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     <span data-ttu-id="79051-109">Aby uzyskać więcej informacji o sposobie konfigurowania magazynu wystąpień przepływu pracy SQL, zobacz [How to: Enable SQL trwałości dla przepływów pracy i usług przepływu pracy](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="79051-109">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="79051-110">Aby uzyskać więcej informacji na temat poszczególnych ustawień dla `sqlWorkflowInstanceStore` elementu zachowanie <>, zobacz [Magazyn wystąpień usługi SQL Workflow](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="79051-110">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="79051-111">Sieć szkieletowa aplikacji systemu Windows Server udostępnia swój własny magazyn trwałości.</span><span class="sxs-lookup"><span data-stu-id="79051-111">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="79051-112">Aby uzyskać więcej informacji, zobacz [trwałość sieci szkieletowej aplikacji systemu Windows Server](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="79051-112">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="79051-113">Poprzedni przykład konfiguracji używa uproszczonej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="79051-113">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="79051-114">Aby uzyskać więcej informacji, zobacz [Uproszczona konfiguracja](../simplified-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="79051-114">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="79051-115">Aby skonfigurować magazyn wystąpień przepływu pracy SQL w kodzie</span><span class="sxs-lookup"><span data-stu-id="79051-115">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1. <span data-ttu-id="79051-116">Właściwości magazynu wystąpień przepływu pracy SQL można skonfigurować przy użyciu <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> zachowania usługi, które umożliwia zmianę ustawień za pomocą kodu.</span><span class="sxs-lookup"><span data-stu-id="79051-116">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="79051-117">Poniższy przykład pokazuje, jak skonfigurować magazyn wystąpień przepływu pracy SQL przy użyciu <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> elementu Behavior w kodzie</span><span class="sxs-lookup"><span data-stu-id="79051-117">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     <span data-ttu-id="79051-118">Aby uzyskać więcej informacji o sposobie konfigurowania magazynu wystąpień przepływu pracy SQL, zobacz [How to: Enable SQL trwałości dla przepływów pracy i usług przepływu pracy](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="79051-118">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="79051-119">Aby uzyskać więcej informacji na temat poszczególnych ustawień dla <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> elementu Behavior, zobacz [Magazyn wystąpień usługi SQL Workflow](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="79051-119">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="79051-120">Sieć szkieletowa aplikacji systemu Windows Server udostępnia swój własny magazyn trwałości.</span><span class="sxs-lookup"><span data-stu-id="79051-120">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="79051-121">Aby uzyskać więcej informacji, zobacz [trwałość sieci szkieletowej aplikacji systemu Windows Server](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="79051-121">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="79051-122">Poprzedni przykład konfiguracji używa uproszczonej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="79051-122">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="79051-123">Aby uzyskać więcej informacji, zobacz [Uproszczona konfiguracja](../simplified-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="79051-123">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="79051-124">Przykład sposobu konfiguracji usługi trwałości można znaleźć w temacie [jak: włączyć trwałość dla przepływów pracy i usług przepływu pracy](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="79051-124">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79051-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="79051-125">See also</span></span>

- [<span data-ttu-id="79051-126">Usługi przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="79051-126">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="79051-127">Trwałość przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="79051-127">Workflow Persistence</span></span>](../../windows-workflow-foundation/workflow-persistence.md)
- <span data-ttu-id="79051-128">[Trwałość sieci szkieletowej aplikacji systemu Windows Server](/previous-versions/appfabric/ee677272(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="79051-128">[Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10))</span></span>
