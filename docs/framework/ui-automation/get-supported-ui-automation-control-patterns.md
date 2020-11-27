---
title: Pobierz obsługiwane wzorce kontrolek automatyzacji interfejsu użytkownika
description: Przeczytaj przykład pokazujący, jak pobrać obsługiwane obiekty wzorców kontroli z elementów automatyzacji interfejsu użytkownika.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: 68abe272e91c40932aba5bcf99394c4a8f815c53
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276454"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="88305-103">Pobierz obsługiwane wzorce kontrolek automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="88305-103">Get Supported UI Automation Control Patterns</span></span>

> [!NOTE]
> <span data-ttu-id="88305-104">Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="88305-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="88305-105">Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="88305-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="88305-106">W tym temacie przedstawiono sposób pobierania obiektów wzorców kontroli z [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elementów.</span><span class="sxs-lookup"><span data-stu-id="88305-106">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="88305-107">Uzyskaj wszystkie wzorce kontroli</span><span class="sxs-lookup"><span data-stu-id="88305-107">Obtain All Control Patterns</span></span>  
  
1. <span data-ttu-id="88305-108">Pobierz, <xref:System.Windows.Automation.AutomationElement> których wzorców kontroli interesują Cię.</span><span class="sxs-lookup"><span data-stu-id="88305-108">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="88305-109">Wywołanie <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> w celu pobrania wszystkich wzorców kontrolek z elementu.</span><span class="sxs-lookup"><span data-stu-id="88305-109">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="88305-110">Zdecydowanie zaleca się, aby klient nie był używany <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> .</span><span class="sxs-lookup"><span data-stu-id="88305-110">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="88305-111">Wydajność może być poważnie narażona na to, że ta metoda wywołuje <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> wewnętrznie dla każdego istniejącego wzorca kontrolki.</span><span class="sxs-lookup"><span data-stu-id="88305-111">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="88305-112">Jeśli to możliwe, klient powinien wywołać <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> kluczowe wzorce.</span><span class="sxs-lookup"><span data-stu-id="88305-112">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="88305-113">Uzyskiwanie określonego wzorca kontroli</span><span class="sxs-lookup"><span data-stu-id="88305-113">Obtain a Specific Control Pattern</span></span>  
  
1. <span data-ttu-id="88305-114">Pobierz, <xref:System.Windows.Automation.AutomationElement> których wzorców kontroli interesują Cię.</span><span class="sxs-lookup"><span data-stu-id="88305-114">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="88305-115">Wywołaj <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> lub <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> , aby wykonać zapytanie dotyczące określonego wzorca.</span><span class="sxs-lookup"><span data-stu-id="88305-115">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="88305-116">Te metody są podobne, ale jeśli wzorzec nie zostanie znaleziony, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> zgłasza wyjątek i <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="88305-116">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88305-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="88305-117">Example</span></span>  

 <span data-ttu-id="88305-118">Poniższy przykład pobiera <xref:System.Windows.Automation.AutomationElement> element listy i uzyskuje <xref:System.Windows.Automation.SelectionItemPattern> od tego elementu.</span><span class="sxs-lookup"><span data-stu-id="88305-118">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="88305-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="88305-119">See also</span></span>

- [<span data-ttu-id="88305-120">Wzorce kontrolek automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="88305-120">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
