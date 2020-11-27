---
title: Opcje tworzenia działań w WF
ms.date: 03/30/2017
ms.assetid: b9061f5f-12c3-47f0-adbe-1330e2714c94
ms.openlocfilehash: e80750b3865a21d072f45b0245ae114660012e66
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289207"
---
# <a name="activity-authoring-options-in-wf"></a>Opcje tworzenia działań w WF

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] oferuje kilka opcji tworzenia działań niestandardowych. Poprawna metoda tworzenia danego działania zależy od tego, jakie funkcje czasu wykonywania są wymagane.  
  
## <a name="deciding-which-base-activity-class-to-use-for-authoring-custom-activities"></a>Decydowanie o klasie działania podstawowego, która ma być używana do tworzenia działań niestandardowych  

 W poniższej tabeli wymieniono funkcje dostępne w klasach podstawowych działań niestandardowych.  
  
|Podstawowa aktywność — Klasa|Dostępne funkcje|  
|-------------------------|------------------------|  
|<xref:System.Activities.Activity>|Tworzy grupy działań dostarczonych przez system i niestandardowych w ramach działania złożonego.|  
|<xref:System.Activities.CodeActivity>|Implementuje bezwzględną funkcjonalność, dostarczając <xref:System.Activities.CodeActivity%601.Execute%2A> metodę, którą można zastąpić. Zapewnia również dostęp do śledzenia, zmiennych i argumentów..|  
|<xref:System.Activities.NativeActivity>|Program udostępnia wszystkie funkcje programu <xref:System.Activities.CodeActivity> , a także przerywa wykonywanie działań, anulowanie wykonywania działania podrzędnego, używanie zakładek i działań planowania, akcje działania i funkcje.|  
|<xref:System.Activities.DynamicActivity>|Zapewnia podejście podobne do modelu DOM do konstruowania działań, które są związane z projektantem WF oraz maszynami czasu wykonywania przez <xref:System.ComponentModel.ICustomTypeDescriptor> program, umożliwiając tworzenie nowych działań bez definiowania nowych typów.|  
  
## <a name="authoring-activities-using-activity"></a>Działania tworzenia przy użyciu działania  

 Działania, które pochodzą od <xref:System.Activities.Activity> funkcji redagowania przez złożenie innych istniejących działań. Te działania mogą być istniejącymi działaniami niestandardowymi i działaniami z poziomu [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] biblioteki działań. Montaż tych działań jest najbardziej podstawowym sposobem na tworzenie funkcji niestandardowych. Takie podejście jest zazwyczaj podejmowane w przypadku używania środowiska projektowania wizualnego do tworzenia przepływów pracy.  
  
## <a name="authoring-activities-using-codeactivity-or-asynccodeactivity"></a>Tworzenie działań za pomocą elementu CodeActivity lub metoda AsyncCodeActivity  

 Działania, które pochodzą z <xref:System.Activities.CodeActivity> lub <xref:System.Activities.AsyncCodeActivity> mogą implementować bezwzględne funkcje przez zastąpienie <xref:System.Activities.CodeActivity%601.Execute%2A> metody niestandardowym kodem. Kod niestandardowy jest wykonywany, gdy działanie jest wykonywane przez środowisko uruchomieniowe. Podczas gdy działania utworzone w ten sposób mają dostęp do funkcji niestandardowych, nie mają dostępu do wszystkich funkcji środowiska uruchomieniowego, takich jak pełny dostęp do środowiska wykonawczego, możliwość planowania działań podrzędnych, tworzenia zakładek lub obsługi metody Cancel lub Abort. Gdy jest <xref:System.Activities.CodeActivity> wykonywana, ma dostęp do zmniejszonej wersji środowiska wykonawczego (za pomocą <xref:System.Activities.CodeActivityContext> <xref:System.Activities.AsyncCodeActivityContext> klasy lub). Działania utworzone przy użyciu <xref:System.Activities.CodeActivity> mają dostęp do argumentów i rozpoznawania zmiennych, rozszerzeń i śledzenia. Asynchroniczne planowanie aktywności można wykonać przy użyciu <xref:System.Activities.AsyncCodeActivity> .  
  
## <a name="authoring-activities-using-nativeactivity"></a>Działania tworzenia przy użyciu natywnego  

 Działania, które pochodzą z <xref:System.Activities.NativeActivity> , takie jak te, które pochodzą z <xref:System.Activities.CodeActivity> , tworzą bezwzględne funkcje przez zastępowanie <xref:System.Activities.NativeActivity.Execute%2A> , ale również mają dostęp do wszystkich funkcji środowiska uruchomieniowego przepływu pracy za pośrednictwem, <xref:System.Activities.NativeActivityContext> który jest przesyłany do <xref:System.Activities.NativeActivity.Execute%2A> metody. Ten kontekst obsługuje planowanie i anulowanie działań podrzędnych, wykonywanie <xref:System.Activities.ActivityAction> i <xref:System.Activities.ActivityFunc%601> obiekty, przepływowanie transakcji do przepływu pracy, wywoływanie procesów asynchronicznych, anulowanie i przerywanie wykonywania, dostęp do właściwości i rozszerzeń wykonywania oraz zakładki (uchwyty dla wznawiania wstrzymanych przepływów pracy).  
  
## <a name="authoring-activities-using-dynamicactivity"></a>Działania tworzenia przy użyciu operacji dynamicznej  

 W przeciwieństwie do innych typów działań, nowe funkcje nie są tworzone przez wyprowadzanie nowych typów z <xref:System.Activities.DynamicActivity> (Klasa jest zapieczętowana), ale zamiast tego przez umieszczenie funkcji we <xref:System.Activities.DynamicActivity.Properties%2A> <xref:System.Activities.DynamicActivity.Implementation%2A> właściwościach i przy użyciu modelu DOM (Document Object Model).  
  
## <a name="authoring-activities-that-return-a-result"></a>Działania tworzenia zwracające wynik  

 Wiele działań musi zwrócić wynik po ich wykonaniu. Chociaż można zawsze definiować niestandardowe <xref:System.Activities.OutArgument%601> działania w tym celu, sugerowane jest użycie <xref:System.Activities.Activity%601> lub pochodna z <xref:System.Activities.CodeActivity%601> lub <xref:System.Activities.NativeActivity%601> . Każda z tych klas podstawowych ma <xref:System.Activities.OutArgument%601> nazwany wynik, którego działanie może używać dla zwracanej wartości. Działania, które zwracają wynik, powinny być używane tylko wtedy, gdy tylko jeden wynik należy zwrócić z działania; Jeśli trzeba zwrócić wiele wyników, <xref:System.Activities.OutArgument%601> zamiast tego należy użyć oddzielnych elementów członkowskich.
