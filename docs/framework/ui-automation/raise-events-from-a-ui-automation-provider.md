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
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="52108-104">Wywoływanie zdarzeń od dostawcy automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="52108-104">Raise Events from a UI Automation Provider</span></span>

> [!NOTE]
> <span data-ttu-id="52108-105">Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="52108-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="52108-106">Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="52108-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="52108-107">Ten temat zawiera przykładowy kod, który pokazuje, jak zgłosić zdarzenie od dostawcy automatyzacji interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="52108-107">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52108-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="52108-108">Example</span></span>  

 <span data-ttu-id="52108-109">W poniższym przykładzie [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] zdarzenie jest zgłaszane w implementacji niestandardowego przycisku kontrolki.</span><span class="sxs-lookup"><span data-stu-id="52108-109">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="52108-110">Implementacja umożliwia aplikacji klienta automatyzacji interfejsu użytkownika symulowanie kliknięcia przycisku.</span><span class="sxs-lookup"><span data-stu-id="52108-110">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="52108-111">Aby uniknąć niepotrzebnego przetwarzania, przykład sprawdza, <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> czy zdarzenia powinny być zgłaszane.</span><span class="sxs-lookup"><span data-stu-id="52108-111">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="52108-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="52108-112">See also</span></span>

- [<span data-ttu-id="52108-113">Przegląd dostawców automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="52108-113">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
