---
title: Magazyn wystąpień przepływu pracy SQL
ms.date: 03/30/2017
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
ms.openlocfilehash: 38cf83ebb8417009c6aa205aa29cd633d1232f0a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540235"
---
# <a name="sql-workflow-instance-store"></a>Magazyn wystąpień przepływu pracy SQL
Program jest [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] dostarczany z magazynem wystąpień przepływu pracy SQL, który umożliwia przepływom pracy utrwalanie informacji o stanie przepływu pracy w bazie danych SQL Server 2005 lub SQL Server 2008. Ta funkcja jest zaimplementowana głównie w postaci <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> klasy, która pochodzi z klasy abstrakcyjnej <xref:System.Runtime.DurableInstancing.InstanceStore> struktury trwałości. Funkcja magazynu wystąpień przepływu pracy SQL stanowi dostawcę trwałości SQL, który jest konkretną implementacją interfejsu API trwałości, którego host używa do wysyłania poleceń trwałości do magazynu.  
  
 Magazyn wystąpień przepływu pracy SQL obsługuje zarówno samoobsługowe, jak i usługi przepływu pracy, które korzystają <xref:System.Activities.WorkflowApplication> <xref:System.ServiceModel.WorkflowServiceHost> z usług lub, jak również usługi hostowane w programie <xref:System.ServiceModel.WorkflowServiceHost> . Funkcję magazynu wystąpień przepływu pracy SQL można skonfigurować programowo dla usług samoobsługowych przy użyciu modelu obiektów uwidocznionego przez funkcję. Tę funkcję można skonfigurować dla usług hostowanych <xref:System.ServiceModel.WorkflowServiceHost> programowo przy użyciu modelu obiektów, a także przy użyciu pliku konfiguracyjnego XML.  
  
 Funkcja magazynu wystąpień przepływu pracy SQL (Klasa**obiekt SqlWorkflowInstanceStore** ) nie implementuje <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> i w związku z tym nie oferuje trwałości w przypadku trwałych usług WCF innych niż przepływ pracy. Nie jest to również zaimplementowane <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> i dlatego nie oferuje obsługi trwałości dla przepływów pracy 3. x. Funkcja obsługuje trwałość tylko dla przepływów pracy WF 4,0 (i nowszych) oraz usług Workflow Services. Ta funkcja nie obsługuje również żadnych baz danych innych niż SQL Server 2005 i SQL Server 2008.  
  
 W tematach w tej sekcji opisano właściwości i funkcje magazynu wystąpień przepływu pracy SQL i przedstawiono szczegółowe informacje na temat konfigurowania sklepu.  
  
 Sieć szkieletowa aplikacji systemu Windows Server zapewnia własne magazyny wystąpień i narzędzia upraszczające konfigurację i użycie magazynu wystąpień. Aby uzyskać więcej informacji, zobacz [Magazyn wystąpień aplikacji Windows Server App Fabric](/previous-versions/appfabric/ff383417(v=azure.10)). Aby uzyskać więcej informacji na temat usługi App Fabric SQL Server trwałości, zobacz [baza danych usługi App fabric SQL Server trwałości](/previous-versions/appfabric/ee790819(v=azure.10))  
  
## <a name="in-this-section"></a>W tej sekcji  
  
- [Właściwości magazynu wystąpień przepływu pracy SQL](properties-of-sql-workflow-instance-store.md)  
  
- [Instrukcje: Włączanie stanów trwałych programu SQL dla przepływów pracy i usług przepływu pracy](how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
- [Aktywacja wystąpienia](instance-activation.md)  
  
- [Obsługa zapytań](support-for-queries.md)  
  
- [Rozszerzalność magazynu](store-extensibility.md)  
  
- [Bezpieczeństwo](security.md)  
  
- [Baza danych stanów trwałych programu SQL Server](sql-server-persistence-database.md)  
  
## <a name="see-also"></a>Zobacz także

- [Próbki trwałości](/previous-versions/dotnet/netframework-4.0/dd699769(v=vs.100))
