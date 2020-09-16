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
ms.openlocfilehash: 112f38d6bef726f92dbf13da70b88732929175dd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557687"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="70404-104">Znajdź element automatyzacji interfejsu użytkownika na podstawie warunku właściwości</span><span class="sxs-lookup"><span data-stu-id="70404-104">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
> <span data-ttu-id="70404-105">Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="70404-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="70404-106">Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="70404-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="70404-107">Ten temat zawiera przykładowy kod pokazujący sposób lokalizowania elementu w [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] drzewie na podstawie określonej właściwości lub właściwości.</span><span class="sxs-lookup"><span data-stu-id="70404-107">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70404-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="70404-108">Example</span></span>  
 <span data-ttu-id="70404-109">W poniższym przykładzie określono zestaw warunków właściwości, które identyfikują określony element (lub elementy) zainteresowania w <xref:System.Windows.Automation.AutomationElement> drzewie.</span><span class="sxs-lookup"><span data-stu-id="70404-109">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="70404-110">Wyszukiwanie wszystkich pasujących elementów jest następnie wykonywane przy użyciu <xref:System.Windows.Automation.AutomationElement.FindAll%2A> metody, która obejmuje serię <xref:System.Windows.Automation.AndCondition> operacji logicznych, aby ograniczyć liczbę pasujących elementów.</span><span class="sxs-lookup"><span data-stu-id="70404-110">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70404-111">Podczas wyszukiwania z programu należy <xref:System.Windows.Automation.AutomationElement.RootElement%2A> próbować uzyskać tylko bezpośrednie elementy podrzędne.</span><span class="sxs-lookup"><span data-stu-id="70404-111">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="70404-112">Wyszukiwanie elementów podrzędnych może się powtarzać przez setki lub nawet tysiące elementów, prawdopodobnie w wyniku przepełnienia stosu.</span><span class="sxs-lookup"><span data-stu-id="70404-112">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="70404-113">Jeśli próbujesz uzyskać określony element na niższym poziomie, należy rozpocząć wyszukiwanie od okna aplikacji lub kontenera na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="70404-113">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="70404-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="70404-114">See also</span></span>

- <span data-ttu-id="70404-115">[Przykład elementu menu InvokePattern i ExpandCollapsePattern](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="70404-115">[InvokePattern and ExpandCollapsePattern Menu Item Sample](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="70404-116">Uzyskiwanie elementów automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="70404-116">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
- [<span data-ttu-id="70404-117">Użyj właściwości AutomationID</span><span class="sxs-lookup"><span data-stu-id="70404-117">Use the AutomationID Property</span></span>](use-the-automationid-property.md)
