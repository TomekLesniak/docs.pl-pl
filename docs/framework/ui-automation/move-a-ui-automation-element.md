---
title: Przenoszenie elementu automatyzacji interfejsu użytkownika
description: Zobacz przykładowy kod, który pokazuje, jak przenieść element automatyzacji interfejsu użytkownika do określonej lokalizacji ekranu. Używa wzorców kontrolek WindowPattern i TransformPattern.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- moving elements
- elements, moving
- UI Automation, moving elements
ms.assetid: 4042cb44-e27e-4a03-ac36-9be1eed65b47
ms.openlocfilehash: 847015818a6c916beb5d026cb7f59a86cebd68cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261192"
---
# <a name="move-a-ui-automation-element"></a>Przenoszenie elementu automatyzacji interfejsu użytkownika

> [!NOTE]
> Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw. Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).  
  
 W tym przykładzie pokazano, jak przenieść [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element do określonej lokalizacji ekranu.  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie zastosowano <xref:System.Windows.Automation.WindowPattern> <xref:System.Windows.Automation.TransformPattern> Wzorce formantów i do programistycznego przenoszenia aplikacji docelowej Win32 do lokalizacji dyskretnych ekranu i śledzenia <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent> .  
  
 [!code-csharp[WindowMove#1301](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1301)]
 [!code-vb[WindowMove#1301](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1301)]  
[!code-csharp[WindowMove#1300](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1300)]
[!code-vb[WindowMove#1300](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1300)]  
  
## <a name="see-also"></a>Zobacz też

- [Przykład WindowPattern](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/WindowMove)
