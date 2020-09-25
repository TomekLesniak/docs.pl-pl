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
# <a name="using-annotation-in-queries"></a><span data-ttu-id="7feeb-102">Używanie adnotacji w zapytaniach</span><span class="sxs-lookup"><span data-stu-id="7feeb-102">Using Annotation in Queries</span></span>

<span data-ttu-id="7feeb-103">Adnotacje umożliwiają arbitralnie tag śledzenia rekordów o wartości, które mogą być skonfigurowane po czas kompilacji.</span><span class="sxs-lookup"><span data-stu-id="7feeb-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="7feeb-104">Na przykład może być konieczne kilka rekordów śledzenia w kilku przepływach pracy, które mają być otagowane przy użyciu "serwer poczty" = = "wiadomość serwer1".</span><span class="sxs-lookup"><span data-stu-id="7feeb-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="7feeb-105">To ułatwia znalezienie wszystkich rekordów z tym znacznikiem podczas wykonywania zapytania rekordów śledzenia później.</span><span class="sxs-lookup"><span data-stu-id="7feeb-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="7feeb-106">Dodawanie adnotacji</span><span class="sxs-lookup"><span data-stu-id="7feeb-106">Adding Annotations</span></span>  

 <span data-ttu-id="7feeb-107">Adnotację można dodać do zapytania śledzenia, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="7feeb-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="7feeb-108">Te elementy zapytania śledzenia może służyć do tworzenia profilu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="7feeb-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="7feeb-109">Można utworzyć profil śledzenia w konfiguracji lub przy użyciu kodu.</span><span class="sxs-lookup"><span data-stu-id="7feeb-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7feeb-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7feeb-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [<span data-ttu-id="7feeb-111">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="7feeb-111">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7feeb-112">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="7feeb-112">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
