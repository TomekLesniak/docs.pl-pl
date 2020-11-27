---
title: Wstrzymywanie i wznawianie przepływu pracy
ms.date: 03/30/2017
ms.assetid: 11f38339-79c7-4295-b610-24a7223bbf6d
ms.openlocfilehash: e8d1806c6d2c8e72b4e3a8b18bff669fcd0e0538
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268543"
---
# <a name="pausing-and-resuming-a-workflow"></a><span data-ttu-id="7a09e-102">Wstrzymywanie i wznawianie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="7a09e-102">Pausing and Resuming a Workflow</span></span>

<span data-ttu-id="7a09e-103">Przepływy pracy zostaną wstrzymane i wznowione w odpowiedzi na zakładki i zablokowane działania, takie jak <xref:System.Activities.Statements.Delay> , ale przepływ pracy można również jawnie wstrzymywać, zwalniać i wznawiać przy użyciu trwałości.</span><span class="sxs-lookup"><span data-stu-id="7a09e-103">Workflows will pause and resume in response to bookmarks and blocking activities such as <xref:System.Activities.Statements.Delay>, but a workflow can also be explicitly paused, unloaded, and resumed by using persistence.</span></span>  
  
## <a name="pausing-a-workflow"></a><span data-ttu-id="7a09e-104">Wstrzymywanie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="7a09e-104">Pausing a Workflow</span></span>  

 <span data-ttu-id="7a09e-105">Aby wstrzymać przepływ pracy, użyj <xref:System.Activities.WorkflowApplication.Unload%2A> .</span><span class="sxs-lookup"><span data-stu-id="7a09e-105">To pause a workflow, use <xref:System.Activities.WorkflowApplication.Unload%2A>.</span></span>  <span data-ttu-id="7a09e-106">Ta metoda żąda, aby przepływ pracy trwał i został zwolniony, a <xref:System.TimeoutException> Jeśli przepływ pracy nie zostanie zwolniony w ciągu 30 sekund.</span><span class="sxs-lookup"><span data-stu-id="7a09e-106">This method requests that the workflow persist and unload, and will throw a <xref:System.TimeoutException> if the workflow does not unload in 30 seconds.</span></span>  
  
```csharp  
try  
{  
    // attempt to unload will fail if the workflow is idle within a NoPersistZone  
    application.Unload(TimeSpan.FromSeconds(5));  
}  
catch (TimeoutException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
## <a name="resuming-a-workflow"></a><span data-ttu-id="7a09e-107">Wznawianie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="7a09e-107">Resuming a Workflow</span></span>  

 <span data-ttu-id="7a09e-108">Aby wznowić poprzednio wstrzymany i niezaładowany przepływ pracy, użyj <xref:System.Activities.WorkflowApplication.Load%2A> .</span><span class="sxs-lookup"><span data-stu-id="7a09e-108">To resume a previously paused and unloaded workflow, use <xref:System.Activities.WorkflowApplication.Load%2A>.</span></span> <span data-ttu-id="7a09e-109">Ta metoda ładuje przepływ pracy z magazynu trwałości do pamięci.</span><span class="sxs-lookup"><span data-stu-id="7a09e-109">This method loads a workflow from a persistence store into memory.</span></span>  
  
```csharp  
WorkflowApplication application = new WorkflowApplication(activity);  
application.InstanceStore = instanceStore;  
application.Load(id);  
```  
  
## <a name="example"></a><span data-ttu-id="7a09e-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="7a09e-110">Example</span></span>  

 <span data-ttu-id="7a09e-111">Poniższy przykład kodu demonstruje, jak wstrzymywać i wznawiać przepływ pracy przy użyciu trwałości.</span><span class="sxs-lookup"><span data-stu-id="7a09e-111">The following code sample demonstrates how to pause and resume a workflow by using persistence.</span></span>  
  
```csharp  
static string bkName = "bkName";  
static void Main(string[] args)
{  
    StartAndUnloadInstance();  
}  
  
static void StartAndUnloadInstance()
{  
    AutoResetEvent waitHandler = new AutoResetEvent(false);  
    WorkflowApplication wfApp = new WorkflowApplication(GetDelayedWF());  
    SqlWorkflowInstanceStore instanceStore = SetupSqlpersistenceStore();  
    wfApp.InstanceStore = instanceStore;  
    wfApp.Extensions.Add(SetupMyFileTrackingParticipant);  
    wfApp.PersistableIdle = (e) => {          ///persists application state and remove it from memory
    return PersistableIdleAction.Unload;  
    };  
    wfApp.Unloaded = (e) => {  
        waitHandler.Set();  
    };  
    Guid id = wfApp.Id;  
    wfApp.Run();  
    waitHandler.WaitOne();  
    LoadAndCompleteInstance(id);  
}  
  
static void LoadAndCompleteInstance(Guid id)
{
    Console.WriteLine("Press <enter> to load the persisted workflow");  
    Console.ReadLine();  
    AutoResetEvent waitHandler = new AutoResetEvent(false);  
    WorkflowApplication wfApp = new WorkflowApplication(GetDelayedWF());  
    wfApp.InstanceStore =  
        new SqlWorkflowInstanceStore(ConfigurationManager.AppSettings["SqlWF4PersistenceConnectionString"].ToString());  
    wfApp.Completed = (workflowApplicationCompletedEventArgs) => {  
        Console.WriteLine("\nWorkflowApplication has Completed in the {0} state.",  
            workflowApplicationCompletedEventArgs.CompletionState);  
    };  
    wfApp.Unloaded = (workflowApplicationEventArgs) => {  
        Console.WriteLine("WorkflowApplication has Unloaded\n");  
        waitHandler.Set();  
    };  
    wfApp.Load(id);  
    wfApp.Run();  
    waitHandler.WaitOne();  
}  
  
public static Activity GetDelayedWF()
{  
    return new Sequence {  
        Activities ={  
            new WriteLine{Text="Workflow Started"},  
            new Delay{Duration=TimeSpan.FromSeconds(10)},  
            new WriteLine{Text="Workflow Ended"}  
        }  
    };  
}  
  
private static SqlWorkflowInstanceStore SetupSqlpersistenceStore()
{
     string connectionString = ConfigurationManager.AppSettings["SqlWF4PersistenceConnectionString"].ToString();  
    SqlWorkflowInstanceStore sqlWFInstanceStore = new SqlWorkflowInstanceStore(connectionString);  
    sqlWFInstanceStore.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;  
    InstanceHandle handle = sqlWFInstanceStore.CreateInstanceHandle();  
    InstanceView view = sqlWFInstanceStore.Execute(handle, new CreateWorkflowOwnerCommand(), TimeSpan.FromSeconds(5));  
    handle.Free();  
    sqlWFInstanceStore.DefaultInstanceOwner = view.InstanceOwner;  
    return sqlWFInstanceStore;  
}  
```
