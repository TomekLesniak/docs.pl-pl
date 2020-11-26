---
title: Biblioteka działań
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 1a0c289315d7181645573098916788f18493abb8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245711"
---
# <a name="activity-library"></a>Biblioteka działań

Ta sekcja zawiera przykłady demonstrujące zaawansowane działania niestandardowe w Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>W tej sekcji

 [Niestandardowe działanie SendMail](sendmail-custom-activity.md)  
 Pokazuje, jak utworzyć niestandardowe działanie, które wynika z programu <xref:System.Activities.AsyncCodeActivity> w celu wysłania wiadomości e-mail przy użyciu protokołu SMTP do użycia w aplikacji przepływu pracy.  
  
 [Działanie ThrottledParallelForEach](throttled-parallel-foreach.md)  
 Pokazuje, w jaki sposób `ThrottleParallelForEach` działanie jest podobne do <xref:System.Activities.Statements.ParallelForEach%601> działania z jedynym wyjątkiem, że umożliwia ustawienie współczynnika współbieżności, aby ograniczyć liczbę równoczesnych gałęzi do wykonania.
  
 [Działania dostępu do bazy danych](database-access-activities.md)  
 Pokazuje, jak tworzyć działania umożliwiające dostęp do baz danych w celu pobierania lub modyfikowania informacji oraz korzystania z [ADO.NET](../../data/adonet/index.md) w celu uzyskania dostępu do bazy danych.  
  
 [Działanie zasad zewnętrznych w programie .NET Framework 4.5](externalized-policy-activity-in-net-framework-4-5.md)  
 Pokazuje, jak działanie ExternalizedPolicy4 umożliwia wykonywanie istniejących Windows Workflow Foundation w .NET Framework 3,5 (WF 3,5) <xref:System.Workflow.Activities.Rules.RuleSet> obiektów w Windows Workflow Foundation [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4,5) bezpośrednio przy użyciu aparatu reguł, który jest dostarczany w programie WF 3,5.
  
 [Nieogólne działanie ForEach](non-generic-foreach.md)  
 Pokazuje, jak utworzyć nieogólną wersję <xref:System.Activities.Statements.ForEach%601> działania.  
  
 [Nieogólne działanie ParallelForEach](non-generic-parallelforeach.md)  
 Pokazuje, jak utworzyć nieogólną wersję <xref:System.Activities.Statements.ParallelForEach%601> działania.  
  
 [Działanie GetWorkflowInstanceId](get-workflowinstanceid.md)  
 Demonstruje sposób używania działania niestandardowego w `GetWorkflowInstanceId` celu ZWRÓCENIA identyfikatora wystąpienia przepływu pracy.
