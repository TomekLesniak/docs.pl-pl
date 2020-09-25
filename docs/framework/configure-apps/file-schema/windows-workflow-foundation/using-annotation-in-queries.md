---
title: Używanie adnotacji w zapytaniach
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 3dd5d19cc303314386ae62ba67f7eec978f6d80b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185369"
---
# <a name="using-annotation-in-queries"></a>Używanie adnotacji w zapytaniach

Adnotacje umożliwiają arbitralnie tag śledzenia rekordów o wartości, które mogą być skonfigurowane po czas kompilacji. Na przykład może być konieczne kilka rekordów śledzenia w kilku przepływach pracy, które mają być otagowane przy użyciu "serwer poczty" = = "wiadomość serwer1". To ułatwia znalezienie wszystkich rekordów z tym znacznikiem podczas wykonywania zapytania rekordów śledzenia później.  
  
## <a name="adding-annotations"></a>Dodawanie adnotacji  

 Adnotację można dodać do zapytania śledzenia, jak pokazano w poniższym przykładzie.  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
> [!NOTE]
> Te elementy zapytania śledzenia może służyć do tworzenia profilu śledzenia. Można utworzyć profil śledzenia w konfiguracji lub przy użyciu kodu.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [Kontrola i śledzenie przepływu pracy](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profile śledzenia](../../../windows-workflow-foundation/tracking-profiles.md)
