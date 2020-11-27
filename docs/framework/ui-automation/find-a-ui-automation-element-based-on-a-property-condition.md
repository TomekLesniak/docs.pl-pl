---
title: Znajdź element automatyzacji interfejsu użytkownika na podstawie warunku właściwości
description: Znajdź element automatyzacji interfejsu użytkownika na podstawie warunku właściwości. Znajdź element w drzewie automatyzacji interfejsu użytkownika na podstawie określonej właściwości lub właściwości.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 603ecf5375af919a558168e14792035a16fb20f2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276493"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Znajdź element automatyzacji interfejsu użytkownika na podstawie warunku właściwości

> [!NOTE]
> Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw. Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).  
  
 Ten temat zawiera przykładowy kod pokazujący sposób lokalizowania elementu w [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] drzewie na podstawie określonej właściwości lub właściwości.  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie określono zestaw warunków właściwości, które identyfikują określony element (lub elementy) zainteresowania w <xref:System.Windows.Automation.AutomationElement> drzewie. Wyszukiwanie wszystkich pasujących elementów jest następnie wykonywane przy użyciu <xref:System.Windows.Automation.AutomationElement.FindAll%2A> metody, która obejmuje serię <xref:System.Windows.Automation.AndCondition> operacji logicznych, aby ograniczyć liczbę pasujących elementów.  
  
> [!NOTE]
> Podczas wyszukiwania z programu należy <xref:System.Windows.Automation.AutomationElement.RootElement%2A> próbować uzyskać tylko bezpośrednie elementy podrzędne. Wyszukiwanie elementów podrzędnych może się powtarzać przez setki lub nawet tysiące elementów, prawdopodobnie w wyniku przepełnienia stosu. Jeśli próbujesz uzyskać określony element na niższym poziomie, należy rozpocząć wyszukiwanie od okna aplikacji lub kontenera na niższym poziomie.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>Zobacz też

- [Przykład elementu menu InvokePattern i ExpandCollapsePattern](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [Uzyskiwanie elementów automatyzacji interfejsu użytkownika](obtaining-ui-automation-elements.md)
- [Użyj właściwości AutomationID](use-the-automationid-property.md)
