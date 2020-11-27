---
title: Wywoływanie zdarzeń od dostawcy automatyzacji interfejsu użytkownika
description: Zobacz przykład pokazujący, jak zgłosić zdarzenie od dostawcy automatyzacji interfejsu użytkownika. Wywołuje zdarzenie automatyzacji interfejsu użytkownika w implementacji niestandardowej kontrolki przycisku.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: 73be7fd92f3fde90255326c51bed03427fd68e8d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250492"
---
# <a name="raise-events-from-a-ui-automation-provider"></a>Wywoływanie zdarzeń od dostawcy automatyzacji interfejsu użytkownika

> [!NOTE]
> Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw. Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).  
  
 Ten temat zawiera przykładowy kod, który pokazuje, jak zgłosić zdarzenie od dostawcy automatyzacji interfejsu użytkownika.  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] zdarzenie jest zgłaszane w implementacji niestandardowego przycisku kontrolki. Implementacja umożliwia aplikacji klienta automatyzacji interfejsu użytkownika symulowanie kliknięcia przycisku.  
  
 Aby uniknąć niepotrzebnego przetwarzania, przykład sprawdza, <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> czy zdarzenia powinny być zgłaszane.  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a>Zobacz też

- [Przegląd dostawców automatyzacji interfejsu użytkownika](ui-automation-providers-overview.md)
