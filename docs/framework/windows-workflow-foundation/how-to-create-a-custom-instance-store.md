---
title: 'Instrukcje: Tworzenie niestandardowego magazynu wystąpień'
ms.date: 03/30/2017
ms.assetid: 593c4e9d-8a49-4e12-8257-cee5e6b4c075
ms.openlocfilehash: cacee7d95a543525ba031de0cc0636d05fc72fc8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945642"
---
# <a name="how-to-create-a-custom-instance-store"></a>Instrukcje: Tworzenie niestandardowego magazynu wystąpień

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] zawiera <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, Magazyn wystąpienia, który używa programu SQL Server do utrwalenia danych przepływu pracy. Jeśli aplikacja jest wymagany do utrwalenia danych przepływu pracy na innym urządzeniu, takie jak system plików, lub innej bazy danych można zaimplementować magazyn wystąpienia niestandardowego. Magazyn niestandardowy wystąpienie tworzy się przez rozszerzenie abstrakcyjnej <xref:System.Runtime.DurableInstancing.InstanceStore> klasy i implementowanie metod, które są wymagane do wykonania. Aby uzyskać pełną implementację magazynu niestandardowego wystąpienia, zobacz [firmowych proces zakupu](./samples/corporate-purchase-process.md) próbki.

## <a name="implementing-the-begintrycommand-method"></a>Implementacja metody BeginTryCommand

<xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> Są wysyłane do magazynu wystąpienia przez aparat trwałości. Typ `command` parametr wskazuje, które polecenie jest wykonywane, ten parametr może być następujących typów:

- <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: Aparat trwałości wysyła to polecenie Magazyn wystąpienia, gdy przepływ pracy jest utrwalony na nośnika magazynowania. Dane trwałość przepływu pracy są dostarczane do metody w <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> członkiem `command` parametru.

- <xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: Aparat trwałości wysyła polecenie Magazyn wystąpienia, gdy przepływ pracy to zostać załadowane z nośnika magazynowania. Identyfikator wystąpienia przepływu pracy do załadowania znajduje się do metody w `instanceId` parametru <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> właściwość `context` parametru.

- <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: Wysyła aparatu trwałości, to polecenie, aby wystąpienie przechowywania, kiedy <xref:System.ServiceModel.Activities.WorkflowServiceHost> musi być zarejestrowana jako właściciel blokady. Identyfikator wystąpienia bieżącego przepływu pracy, należy przekazać do przy użyciu magazynu wystąpienia <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> metody `context` parametru.

     Poniższy fragment kodu demonstruje sposób implementacji polecenie CreateWorkflowOwner, aby przypisać właściciela jawne blokady.

    ```csharp
    XName WFInstanceScopeName = XName.Get(scopeName, "<namespace>");
    ...
    CreateWorkflowOwnerCommand createCommand = new CreateWorkflowOwnerCommand()
    {
        InstanceOwnerMetadata =
        {
            { WorkflowHostTypeName, new InstanceValue(WFInstanceScopeName) },
        }
    };
    InstanceHandle ownerHandle = store.CreateInstanceHandle();
    store.DefaultInstanceOwner = store.Execute(
                                   ownerHandle,
                                   createCommand,
                                   TimeSpan.FromSeconds(30)).InstanceOwner;
    childInstance.AddInitialInstanceValues(new Dictionary<XName, object>() { { WorkflowHostTypeName, WFInstanceScopeName } });
    ```

- <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: Aparat trwałości wysyła polecenie Magazyn wystąpienia, gdy właściciel blokady Identyfikatora wystąpienia, mogą być usunięte z magazynu wystąpienia. Podobnie jak w przypadku <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, identyfikator właściciela blokady powinien być udostępniany przez aplikację.

     Poniższy fragment kodu pokazuje, jak zwolnić blokadę przy użyciu <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>.

    ```csharp
    static void FreeHandleAndDeleteOwner(InstanceStore store, InstanceHandle handle)
    {
        handle.Free();
        handle = store.CreateInstanceHandle(store.DefaultInstanceOwner);
        try
        {
            // We need this sleep so that we dont prematurely delete the owner, we need time to update the database.
            Thread.Sleep(10000);
            store.Execute(handle, new DeleteWorkflowOwnerCommand(), TimeSpan.FromSeconds(10));
        }
        catch (InstancePersistenceCommandException ex) { Log.Inform(ex.Message); }
        catch (InstanceOwnerException ex) { Log.Inform(ex.Message); }
        catch (OperationCanceledException ex) { Log.Inform(ex.Message); }
        catch (Exception ex) { Log.Inform(ex.Message); }
        finally
        {
            handle.Free();
            store.DefaultInstanceOwner = null;
        }
    }
    ```

     Powyższej metody powinna być wywoływana w bloku Try/Catch, po uruchomieniu wystąpienia podrzędne.

    ```csharp
    try
    {
        childInstance.Run();
    }
    catch (Exception)
    {
        throw ;
    }
    finally
    {
        FreeHandleAndDeleteOwner(store, ownerHandle);
    }
    ```

- <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: Aparat trwałości wysyła polecenie Magazyn wystąpienia, gdy wystąpienie przepływu pracy jest ładowany za pomocą klucza wystąpienia przepływu pracy. Identyfikator klucza wystąpienia można określić za pomocą <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> parametru polecenia.

- <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: Aparat trwałości wysyła polecenie Magazyn wystąpienia można pobrać parametry aktywacji dla utrwalonych przepływów pracy, aby można było utworzyć hosta przepływu pracy, które następnie mogą ładować przepływów pracy. To polecenie jest wysyłane przez aparat w odpowiedzi na wywoływanie wystąpienia magazynu <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> do hosta, gdy klient zlokalizuje wystąpienie, które można aktywować. Magazyn wystąpień powinna sondowania w celu określenia, czy przepływy pracy, które można aktywować.

- <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: Aparat trwałości wysyła polecenie Magazyn wystąpienia można załadować wystąpienia przepływu pracy możliwy do uruchomienia. To polecenie jest wysyłane przez aparat w odpowiedzi na wywoływanie wystąpienia magazynu <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> do hosta, gdy klient zlokalizuje wystąpienie, które mogą być uruchamiane. Magazyn wystąpień, należy wykonać sondowanie dla przepływów pracy, które mogą być uruchamiane. Poniższy fragment kodu pokazuje sondowania magazyn wystąpienia dla przepływów pracy, które można uruchamiać lub aktywowane.

    ```csharp
    public void PollForEvents()
    {
        InstanceOwner[] storeOwners = this.GetInstanceOwners();

        foreach (InstanceOwner owner in storeOwners)
        {
            foreach (InstancePersistenceEvent ppEvent in this.GetEvents(owner))
            {
                if (ppEvent.Equals(HasRunnableWorkflowEvent.Value))
                {
                    bool hasRunnable = GetRunnableEvents(this.StoreId, owner.InstanceOwnerId, isActivatable);
                    if (hasRunnable)
                    {
                        this.SignalEvent(ppEvent, owner);
                    }
                    else
                    {
                        this.ResetEvent(ppEvent, owner);
                    }
                }
                else if(ppEvent.Equals(HasActivatableWorkflowEvent.Value))
                {
                   bool hasActivatable = GetActivatableEvents(this.StoreId, owner.InstanceOwnerId);
                   if (hasActivatable)
                    {
                        this.SignalEvent(ppEvent, owner);
                    }
                    else
                    {
                        this.ResetEvent(ppEvent, owner);
                    }
                }
            }
        }
    }
    ```

     W powyższym fragmencie kodu magazyn wystąpienia zapytań dostępnych zdarzeń i sprawdza, czy każdy z nich do określenia, czy jest <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> zdarzeń. Jeśli nie zostanie znalezione, <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> jest wywoływana, aby wysłać polecenie Magazyn wystąpienia hosta. Poniższy fragment kodu przedstawia implementację programu obsługi dla tego polecenia.

    ```csharp
    If (command is TryLoadRunnableWorkflowCommand)
    {
        Owner owner;
        CheckOwner(context, command.Name, out owner);
        // Checking instance.Owner is like an InstanceLockQueryResult.
        context.QueriedInstanceStore(new InstanceLockQueryResult(context.InstanceView.InstanceId, context.InstanceView.InstanceOwner.InstanceOwnerId));

        XName ownerService = null;
        InstanceValue value;
        Instance runnableInstance = default(Instance);
        bool foundRunnableInstance = false;

        value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, owner.Data);
        if (value != null && value.Value is XName)
        {
            ownerService = (XName)value.Value;
        }

        foreach (KeyValuePair<Guid, Instance> instance in MemoryStore.instances)
        {
            if (instance.Value.Owner != Guid.Empty || instance.Value.Completed)
            {
                continue;
            }

            if (ownerService != null)
            {
                value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, instance.Value.Metadata);
                if (value == null || ((XName)value.Value) != ownerService)
                {
                    continue;
                }
            }

            value = QueryPropertyBag(WorkflowServiceNamespace.SuspendReason, instance.Value.Metadata);
            if (value != null && value.Value != null && value.Value is string)
            {
                continue;
            }

            value = QueryPropertyBag(WorkflowNamespace.Status, instance.Value.Data);
            if (value != null && value.Value is string && ((string)value.Value) == "Executing")
            {
                runnableInstance = instance.Value;
                foundRunnableInstance = true;
            }

            if (!foundRunnableInstance)
            {
                value = QueryPropertyBag(XNamespace.Get("urn:schemas-microsoft-com:System.Activities/4.0/properties").GetName("TimerExpirationTime"), instance.Value.Data);
                if (value != null && value.Value is DateTime && ((DateTime)value.Value) <= DateTime.UtcNow)
                {
                    runnableInstance = instance.Value;
                    foundRunnableInstance = true;
                }
            }

            if (foundRunnableInstance)
            {
                runnableInstance.LockVersion++;
                runnableInstance.Owner = context.InstanceView.InstanceOwner.InstanceOwnerId;
                MemoryStore.instances[instance.Key] = runnableInstance;
                context.BindInstance(instance.Key);
                context.BindAcquiredLock(runnableInstance.LockVersion);

                Dictionary<Guid, IDictionary<XName, InstanceValue>> associatedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();
                Dictionary<Guid, IDictionary<XName, InstanceValue>> completedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();
                foreach (KeyValuePair<Guid, Key> keyEntry in MemoryStore.keys)
                {
                if (keyEntry.Value.Instance == context.InstanceView.InstanceId)
                {
                    if (keyEntry.Value.Completed)
                    {
                        completedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));
                    }
                    else
                    {
                        associatedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));
                    }
                }
            }

            context.LoadedInstance(InstanceState.Initialized, DeserializePropertyBag(runnableInstance.Data), DeserializePropertyBag(runnableInstance.Metadata), associatedKeys, completedKeys);
            break;
        }
    }
    ```

    W powyższym fragmencie kodu magazyn wystąpienia wyszukuje wystąpień możliwych do uruchomienia. Jeśli wystąpienie zostanie znaleziony, jest powiązany z kontekstu wykonywania i załadowany.

## <a name="using-a-custom-instance-store"></a>Za pomocą magazynu niestandardowego wystąpienia

Aby zaimplementować magazynu niestandardowego wystąpienia, przypisz wystąpienie magazynu wystąpienia do <xref:System.Activities.WorkflowApplication.InstanceStore%2A>i zaimplementować <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> metody. Zobacz [jak: Tworzenie i uruchamianie długiego uruchamiania przepływu pracy](how-to-create-and-run-a-long-running-workflow.md) samouczek dotyczący szczegółowych informacji.

## <a name="a-sample-instance-store"></a>Magazyn wystąpień próbki

Poniższy przykładowy kod jest pełne wystąpienie Implementacja magazynu, z [firmowych proces zakupu](./samples/corporate-purchase-process.md) próbki. Ten magazyn wystąpienia są utrwalane danych przepływu pracy do pliku za pomocą języka XML.

```csharp
using System;
using System.Activities.DurableInstancing;
using System.Collections.Generic;
using System.IO;
using System.Runtime.DurableInstancing;
using System.Runtime.Serialization;
using System.ServiceModel.Persistence;
using System.Xml;
using System.Xml.Linq;

namespace Microsoft.Samples.WF.PurchaseProcess
{

    public class XmlWorkflowInstanceStore : InstanceStore
    {
        Guid ownerInstanceID;

        public XmlWorkflowInstanceStore() : this(Guid.NewGuid())
        {

        }

        public XmlWorkflowInstanceStore(Guid id)
        {
            ownerInstanceID = id;
        }

        //Synchronous version of the Begin/EndTryCommand functions
        protected override bool TryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout)
        {
            return EndTryCommand(BeginTryCommand(context, command, timeout, null, null));
        }

        //The persistence engine will send a variety of commands to the configured InstanceStore,
        //such as CreateWorkflowOwnerCommand, SaveWorkflowCommand, and LoadWorkflowCommand.
        //This method is where we will handle those commands
        protected override IAsyncResult BeginTryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout, AsyncCallback callback, object state)
        {
            IDictionary<XName, InstanceValue> data = null;

            //The CreateWorkflowOwner command instructs the instance store to create a new instance owner bound to the instanace handle
            if (command is CreateWorkflowOwnerCommand)
            {
                context.BindInstanceOwner(ownerInstanceID, Guid.NewGuid());
            }
            //The SaveWorkflow command instructs the instance store to modify the instance bound to the instance handle or an instance key
            else if (command is SaveWorkflowCommand)
            {
                SaveWorkflowCommand saveCommand = (SaveWorkflowCommand)command;
                data = saveCommand.InstanceData;

                Save(data);
            }
            //The LoadWorkflow command instructs the instance store to lock and load the instance bound to the identifier in the instance handle
            else if (command is LoadWorkflowCommand)
            {
                string fileName = IOHelper.GetFileName(this.ownerInstanceID);

                try
                {
                    using (FileStream inputStream = new FileStream(fileName, FileMode.Open))
                    {
                        data = LoadInstanceDataFromFile(inputStream);
                        //load the data into the persistence Context
                        context.LoadedInstance(InstanceState.Initialized, data, null, null, null);
                    }
                }
                catch (Exception exception)
                {
                    throw new PersistenceException(exception.Message);
                }
            }

            return new CompletedAsyncResult<bool>(true, callback, state);
        }

        protected override bool EndTryCommand(IAsyncResult result)
        {
            return CompletedAsyncResult<bool>.End(result);
        }

        //Reads data from xml file and creates a dictionary based off of that.
        IDictionary<XName, InstanceValue> LoadInstanceDataFromFile(Stream inputStream)
        {
            IDictionary<XName, InstanceValue> data = new Dictionary<XName, InstanceValue>();

            NetDataContractSerializer s = new NetDataContractSerializer();

            XmlReader rdr = XmlReader.Create(inputStream);
            XmlDocument doc = new XmlDocument();
            doc.Load(rdr);

            XmlNodeList instances = doc.GetElementsByTagName("InstanceValue");
            foreach (XmlElement instanceElement in instances)
            {
                XmlElement keyElement = (XmlElement)instanceElement.SelectSingleNode("descendant::key");
                XName key = (XName)DeserializeObject(s, keyElement);

                XmlElement valueElement = (XmlElement)instanceElement.SelectSingleNode("descendant::value");
                object value = DeserializeObject(s, valueElement);
                InstanceValue instVal = new InstanceValue(value);

                data.Add(key, instVal);
            }

            return data;
        }

        object DeserializeObject(NetDataContractSerializer serializer, XmlElement element)
        {
            object deserializedObject = null;

            MemoryStream stm = new MemoryStream();
            XmlDictionaryWriter wtr = XmlDictionaryWriter.CreateTextWriter(stm);
            element.WriteContentTo(wtr);
            wtr.Flush();
            stm.Position = 0;

            deserializedObject = serializer.Deserialize(stm);

            return deserializedObject;
        }

        //Saves the persistence data to an xml file.
        void Save(IDictionary<XName, InstanceValue> instanceData)
        {
            string fileName = IOHelper.GetFileName(this.ownerInstanceID);
            XmlDocument doc = new XmlDocument();
            doc.LoadXml("<InstanceValues/>");

            foreach (KeyValuePair<XName,InstanceValue> valPair in instanceData)
            {
                XmlElement newInstance = doc.CreateElement("InstanceValue");

                XmlElement newKey = SerializeObject("key", valPair.Key, doc);
                newInstance.AppendChild(newKey);

                XmlElement newValue = SerializeObject("value", valPair.Value.Value, doc);
                newInstance.AppendChild(newValue);

                doc.DocumentElement.AppendChild(newInstance);
            }
            doc.Save(fileName);
       }

        XmlElement SerializeObject(string elementName, object o, XmlDocument doc)
        {
            NetDataContractSerializer s = new NetDataContractSerializer();
            XmlElement newElement = doc.CreateElement(elementName);
            MemoryStream stm = new MemoryStream();

            s.Serialize(stm, o);
            stm.Position = 0;
            StreamReader rdr = new StreamReader(stm);
            newElement.InnerXml = rdr.ReadToEnd();

            return newElement;
        }
    }
}
```
