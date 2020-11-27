---
title: Używanie niestandardowego działania
ms.date: 03/30/2017
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
ms.openlocfilehash: 43addd4e69b7f7ac3ac5cd8e5bcd41397d8f0a67
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293328"
---
# <a name="using-a-custom-activity"></a>Używanie niestandardowego działania

Działania pochodzące z <xref:System.Activities.Activity> lub jego podklasy mogą być złożone w większych przepływach pracy lub tworzone bezpośrednio w kodzie. W tym temacie opisano sposób używania działań niestandardowych w przepływach pracy utworzonych w kodzie lub w projektancie.  
  
> [!NOTE]
> Działań niestandardowych można używać w tym samym projekcie, w którym są zdefiniowane, tak długo jak działanie niestandardowe i działanie, które go używa, są kompilowane (tj. ładowane przez typ tworzenia wystąpienia generowanego przez proces kompilacji), jeśli działanie odwołujące jest ładowane dynamicznie (np. przy użyciu obiekt ActivityXamlServices), zestaw, do którego istnieje odwołanie, powinien być umieszczony w innym projekcie lub kod XAML wygenerowany przez projektanta musi być edytowany ręcznie, aby go włączyć.  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>Używanie niestandardowego działania do projektu przepływu pracy  
  
1. Dodaj odwołanie z projektu hosta do projektu biblioteki działań zawierającego działanie niestandardowe.  
  
2. Skompiluj rozwiązanie.  
  
3. Aby użyć działania niestandardowego w projektancie, zlokalizuj działanie niestandardowe w przyborniku i przeciągnij działanie na powierzchnię projektanta.  
  
4. Aby użyć działania niestandardowego w kodzie, Dodaj instrukcję using, która odwołuje się do projektu działania niestandardowego, i przekaż nowe wystąpienie działania do <xref:System.Activities.WorkflowInvoker.Invoke%2A> .
