---
title: Kontrola drzewa działań
ms.date: 03/30/2017
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
ms.openlocfilehash: 044dcbbe7f22b1026dbc4dc14ab87da4f5a9d0ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289155"
---
# <a name="activity-tree-inspection"></a>Kontrola drzewa działań

Inspekcja drzewa działań jest używana przez autorów aplikacji przepływu pracy do sprawdzania przepływów pracy hostowanych przez aplikację. Za pomocą programu <xref:System.Activities.WorkflowInspectionServices> przepływy pracy mogą być wyszukiwane w przypadku określonych działań podrzędnych, poszczególnych działań i ich właściwości można wyliczyć, a metadane środowiska uruchomieniowego działań mogą być buforowane w określonym czasie. Ten temat zawiera omówienie <xref:System.Activities.WorkflowInspectionServices> i sposób korzystania z niego w celu sprawdzenia drzewa aktywności.  
  
## <a name="using-workflowinspectionservices"></a>Korzystanie z WorkflowInspectionServices  

 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>Metoda służy do wyliczania wszystkich działań w określonym drzewie aktywności. <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> Zwraca wartość wyliczalną, która dotyka wszystkie działania w drzewie, w tym elementy podrzędne, programy obsługi delegatów, zmienne domyślne i wyrażenia argumentów. W poniższym przykładzie definicja przepływu pracy jest tworzona przy użyciu <xref:System.Activities.Statements.Sequence> <xref:System.Activities.Statements.While> wyrażeń,, <xref:System.Activities.Statements.ForEach%601> , <xref:System.Activities.Statements.WriteLine> i. Po utworzeniu definicji przepływu pracy jest wywoływana, a następnie `InspectActivity` wywoływana metoda.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 Aby wyliczyć działania, <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> jest wywoływana dla działania głównego i ponownie rekursywnie dla każdego zwróconego działania. W poniższym przykładzie <xref:System.Activities.Activity.DisplayName%2A> każde działanie i wyrażenie w drzewie aktywności są zapisywane w konsoli programu.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 Ten przykładowy kod zawiera następujące dane wyjściowe.  
  
 **Element listy 1**  
**Element listy 2** 
 **Element listy 3** 
 **Element listy 4** 
 **Element listy 5** 
 **Elementy dodane do kolekcji.** 
 **Sequence** **\<String> Lista ><literałów** sekwencji  
 **Czekać**  
 **AddToCollection\<String>**  
 **VariableValue<ICollection\<String>>**  
 **LambdaValue\<String>**  
 **Lista<LocationReferenceValue\<String>>**  
 **LambdaValue\<Boolean>**  
 **Lista<LocationReferenceValue\<String>>**  
 **Spowodował\<String>**  
 **VariableValue<interfejs IEnumerable\<String>>**  
 **WriteLine**  
 **DelegateArgumentValue\<String>**  
 **Sequence**  
 **WriteLine**  
 **Literał \<String>**  W celu pobrania określonego działania zamiast wyliczania wszystkich działań <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> jest używana. <xref:System.Activities.WorkflowInspectionServices.Resolve%2A>I <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> Wykonaj buforowanie metadanych, jeśli `WorkflowInspectionServices.CacheMetadata` nie została wcześniej wywołana. Jeśli został <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> wywołany <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> , jest oparty na istniejących metadanych. W związku z tym, jeśli zmiany drzewa zostały wprowadzone od czasu ostatniego wywołania do <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> , <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> mogą dać nieoczekiwane wyniki. Jeśli po wywołaniu zmiany zostały wprowadzone do przepływu pracy <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> , metadane mogą być przechowywane w pamięci podręcznej przez wywołanie <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> metody. Metadane pamięci podręcznej zostały omówione w następnej sekcji.  
  
### <a name="caching-metadata"></a>Buforowanie metadanych  

 Buforowanie metadanych dla działań kompiluje i sprawdza opis argumentów działania, zmiennych, działań podrzędnych i delegatów działań. Domyślnie metadane są buforowane przez środowisko uruchomieniowe, gdy działanie jest przygotowywane do wykonania. Jeśli autor hosta przepływu pracy chce w pamięci podręcznej metadane dla działania lub drzewa aktywności, na przykład aby skorzystać z całego kosztu z góry, <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> można go użyć do buforowania metadanych w żądanym czasie.
