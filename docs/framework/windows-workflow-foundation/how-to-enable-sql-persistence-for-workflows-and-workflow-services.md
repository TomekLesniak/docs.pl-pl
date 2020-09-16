---
title: 'Instrukcje: Włączanie stanów trwałych programu SQL dla przepływów pracy i usług przepływu pracy'
ms.date: 03/30/2017
ms.assetid: ca7bf77f-3e5d-4b23-b17a-d0b60f46411d
ms.openlocfilehash: 5bcd37a654db35ba6e8af1b15d6c132a090b0579
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547756"
---
# <a name="how-to-enable-sql-persistence-for-workflows-and-workflow-services"></a>Instrukcje: Włączanie stanów trwałych programu SQL dla przepływów pracy i usług przepływu pracy

W tym temacie opisano sposób konfigurowania funkcji magazynu wystąpień przepływu pracy SQL w celu zapewnienia trwałości dla przepływów pracy i usług przepływu pracy w sposób programistyczny i przy użyciu pliku konfiguracji.

Sieć szkieletowa aplikacji systemu Windows Server upraszcza proces konfigurowania trwałości. Aby uzyskać więcej informacji, zobacz [Konfiguracja trwałości usługi App Fabric](/previous-versions/appfabric/ee790848(v=azure.10)).

Przed użyciem funkcji magazynu wystąpień przepływu pracy SQL Utwórz bazę danych używaną przez funkcję do utrwalania wystąpień przepływu pracy. [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]Program konfiguracji kopiuje pliki skryptów SQL skojarzonych z funkcją Magazyn wystąpień przepływu pracy SQL do folderu%windir%\Microsoft.NET\Framework\v4.xxx\SQL\EN. Uruchom te pliki skryptów dla bazy danych SQL Server 2005 lub SQL Server 2008, która ma być używana przez magazyn wystąpień programu SQL do utrwalania wystąpień przepływu pracy. Najpierw uruchom plik SqlWorkflowInstanceStoreSchema. SQL, a następnie uruchom plik SqlWorkflowInstanceStoreLogic. SQL.

> [!NOTE]
> Aby wyczyścić bazę danych trwałości w celu utworzenia nowej bazy danych, Uruchom skrypty w%WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN w następującej kolejności.
>
> 1. SqlWorkflowInstanceStoreSchema. SQL
> 2. SqlWorkflowInstanceStoreLogic. SQL

> [!IMPORTANT]
> Jeśli nie utworzysz bazy danych trwałości, funkcja magazynu wystąpień przepływu pracy SQL zgłasza wyjątek podobny do poniższego, gdy host próbuje utrwalać przepływy pracy.
>
> System. Data. SqlClient. SqlException: nie można znaleźć procedury składowanej "System. Activities. DurableInstancing. CreateLockOwner"

W poniższych sekcjach opisano sposób włączania trwałości dla przepływów pracy i usług przepływu pracy w programie SQL Server. Aby uzyskać więcej informacji na temat właściwości magazynu wystąpień przepływu pracy SQL, zobacz [właściwości magazynu wystąpień przepływu pracy SQL](properties-of-sql-workflow-instance-store.md).

## <a name="enabling-persistence-for-self-hosted-workflows-that-use-workflowapplication"></a>Włączanie trwałości dla samohostowanych przepływów pracy korzystających z funkcji WorkflowApplication

Można włączyć trwałość dla samodzielnych przepływów pracy, które wykorzystują program <xref:System.Activities.WorkflowApplication> programowo przy użyciu <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> modelu obiektów. Poniższa procedura zawiera kroki, które należy wykonać.

#### <a name="to-enable-persistence-for-self-hosted-workflows"></a>Aby włączyć trwałość dla samodzielnych przepływów pracy

1. Dodaj odwołanie do System.Activities.DurableInstancing.dll.

2. Dodaj następującą instrukcję w górnej części pliku źródłowego po istniejącej instrukcji "Using".

    ```csharp
    using System.Activities.DurableInstancing;
    ```

3. Konstrukcja a <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> i przypisz ją do obiektu, <xref:System.Activities.WorkflowApplication.InstanceStore%2A> <xref:System.Activities.WorkflowApplication> tak jak pokazano w poniższym przykładzie kodu.

    ```csharp
    SqlWorkflowInstanceStore store =
        new SqlWorkflowInstanceStore("Server=.\\SQLEXPRESS;Initial Catalog=Persistence;Integrated Security=SSPI");

    WorkflowApplication wfApp =
        new WorkflowApplication(new Workflow1());

    wfApp.InstanceStore = store;
    ```

   > [!NOTE]
   > W zależności od wersji SQL Server Nazwa serwera parametrów połączenia może się różnić.

4. Wywołaj <xref:System.Activities.WorkflowApplication.Persist%2A> metodę dla <xref:System.Activities.WorkflowApplication> obiektu, aby zachować przepływ pracy, lub <xref:System.Activities.WorkflowApplication.Unload%2A> metodę, aby zachować i zwolnić przepływ pracy. Można także obsłużyć <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> zdarzenie wywoływane przez <xref:System.Activities.WorkflowApplication> obiekt i zwrócić odpowiedni ( <xref:System.Activities.PersistableIdleAction.Persist> lub <xref:System.Activities.PersistableIdleAction.Unload> ) element członkowski <xref:System.Activities.PersistableIdleAction> .

   ```csharp
   wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
   {
       return PersistableIdleAction.Persist;
   };
   ```

> [!NOTE]
> Aby uzyskać instrukcje krok po kroku, zobacz artykuł [jak utworzyć i uruchomić długotrwały przepływ pracy](how-to-create-and-run-a-long-running-workflow.md) w [samouczku wprowadzenie](getting-started-tutorial.md) .

## <a name="enabling-persistence-for-self-hosted-workflow-services-that-use-the-workflowservicehost"></a>Włączanie trwałości dla samodzielnych usług przepływu pracy korzystających z obiektu WorkflowServiceHost

Można włączyć trwałość dla samodzielnych usług przepływu pracy, które wykorzystują program <xref:System.ServiceModel.WorkflowServiceHost> programowo przy użyciu <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> klasy lub <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> klasy.

### <a name="using-the-sqlworkflowinstancestorebehavior-class"></a>Korzystanie z klasy SqlWorkflowInstanceStoreBehavior

Poniższa procedura zawiera kroki umożliwiające użycie <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> klasy w celu zapewnienia trwałości dla samodzielnych usług przepływu pracy.

#### <a name="to-enable-persistence-using-sqlworkflowinstancestorebehavior"></a>Aby włączyć trwałość przy użyciu SqlWorkflowInstanceStoreBehavior

1. Dodaj odwołanie do System.ServiceModel.dll.

2. Dodaj następującą instrukcję w górnej części pliku źródłowego po istniejącej instrukcji "Using".

    ```csharp
    using System.ServiceModel.Activities.Description;
    ```

3. Utwórz wystąpienie `WorkflowServiceHost` i Dodaj punkty końcowe dla usługi przepływu pracy.

    ```csharp
    WorkflowServiceHost host = new WorkflowServiceHost(new CountingWorkflow(), new Uri(hostBaseAddress));
    host.AddServiceEndpoint("ICountingWorkflow", new BasicHttpBinding(), "");
    ```

4. Konstruowanie `SqlWorkflowInstanceStoreBehavior` obiektu i Ustawianie właściwości obiektu Behavior.

    ```csharp
    SqlWorkflowInstanceStoreBehavior instanceStoreBehavior = new SqlWorkflowInstanceStoreBehavior(connectionString);
    instanceStoreBehavior.HostLockRenewalPeriod = new TimeSpan(0, 0, 5);
    instanceStoreBehavior.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;
    instanceStoreBehavior.InstanceLockedExceptionAction = InstanceLockedExceptionAction.AggressiveRetry;
    instanceStoreBehavior.InstanceEncodingOption = InstanceEncodingOption.GZip;
    instanceStoreBehavior.RunnableInstancesDetectionPeriod = new TimeSpan("00:00:02");
    host.Description.Behaviors.Add(instanceStoreBehavior);
    ```

5. Otwórz hosta usługi przepływu pracy.

    ```csharp
    host.Open();
    ```

### <a name="using-the-durableinstancingoptions-property"></a>Używanie właściwości DurableInstancingOptions

Gdy `SqlWorkflowInstanceStoreBehavior` jest stosowany, `DurableInstancingOptions.InstanceStore` na `WorkflowServiceHost` jest ustawiony na `SqlWorkflowInstanceStore` obiekt utworzony przy użyciu wartości konfiguracyjnych. Można to zrobić programowo, aby ustawić <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> Właściwość `WorkflowServiceHost` bez użycia `SqlWorkflowInstanceStoreBehavior` klasy, jak pokazano w poniższym przykładzie kodu.

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```

## <a name="enabling-persistence-for-was-hosted-workflow-services-that-use-the-workflowservicehost-using-a-configuration-file"></a>Włączanie trwałości dla hostowanych usług przepływu pracy, które używają obiektu WorkflowServiceHost przy użyciu pliku konfiguracji

Możesz włączyć trwałość dla usługi przepływu pracy obsługiwanej przez samodzielny lub usługi aktywacji procesów systemu Windows (WAS) przy użyciu pliku konfiguracji. Hostowana usługa przepływu pracy używa obiektu WorkflowServiceHost jako samoobsługowego usługi przepływu pracy.

`SqlWorkflowInstanceStoreBehavior`Zachowanie usługi, które umożliwia wygodną zmianę właściwości [magazynu wystąpienia przepływu pracy SQL](sql-workflow-instance-store.md) za pomocą konfiguracji XML. W przypadku usług hostowanych przepływów pracy Użyj pliku Web.config. Poniższy przykład konfiguracji pokazuje, jak skonfigurować magazyn wystąpień przepływu pracy SQL przy użyciu `sqlWorkflowInstanceStore` elementu Behavior w pliku konfiguracji.

```xml
<serviceBehaviors>
    <behavior name="">
        <sqlWorkflowInstanceStore
                    connectionString="Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"
                    instanceEncodingOption="GZip | None"
                    instanceCompletionAction="DeleteAll | DeleteNothing"
                    instanceLockedExceptionAction="NoRetry | BasicRetry |AggressiveRetry"
                    hostLockRenewalPeriod="00:00:30"
                    runnableInstancesDetectionPeriod="00:00:05" />

    </behavior>
</serviceBehaviors>
```

Jeśli nie ustawisz wartości `connectionString` `connectionStringName` właściwości lub, magazyn wystąpień przepływu pracy SQL używa domyślnie nazwanych parametrów połączenia `DefaultSqlWorkflowInstanceStoreConnectionString` .

Gdy `SqlWorkflowInstanceStoreBehavior` jest stosowany, `DurableInstancingOptions.InstanceStore` na `WorkflowServiceHost` jest ustawiony na `SqlWorkflowInstanceStore` obiekt utworzony przy użyciu wartości konfiguracyjnych. Można to zrobić programowo, aby użyć polecenia `SqlWorkflowInstanceStore` with `WorkflowServiceHost` bez użycia elementu zachowania usługi.

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```

> [!IMPORTANT]
> Zaleca się, aby nie przechowywać poufnych informacji, takich jak nazwy użytkowników i hasła w pliku Web.config. Jeśli przechowujesz poufne informacje w pliku Web.config, należy zabezpieczyć dostęp do pliku Web.config za pomocą list Access Control systemu plików (ACL). Ponadto można zabezpieczyć wartości konfiguracyjne w pliku konfiguracji, jak wspomniano w temacie [szyfrowanie informacji o konfiguracji za pomocą konfiguracji chronionej](/previous-versions/aspnet/53tyfkaw(v=vs.100)).

### <a name="machineconfig-elements-related-to-the-sql-workflow-instance-store-feature"></a>Machine.config elementów związanych z funkcją magazynu wystąpień przepływu pracy SQL

[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]Instalacja dodaje następujące elementy związane z funkcją Magazyn wystąpień przepływu pracy SQL do pliku Machine.config:

- Dodaje następujący element rozszerzenia zachowania do pliku Machine.config, aby można było użyć \<sqlWorkflowInstanceStore> elementu zachowanie usługi w pliku konfiguracji w celu skonfigurowania trwałości usług.

    ```xml
    <configuration>
        <system.serviceModel>
            <extensions>
                <behaviorExtensions>
                    <add name="sqlWorkflowInstanceStore" type="System.Activities.DurableInstancing.SqlWorkflowInstanceStoreElement, System.Activities.DurableInstancing, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
                </behaviorExtensions>
            </extensions>
        </system.serviceModel>
    </configuration>
    ```
