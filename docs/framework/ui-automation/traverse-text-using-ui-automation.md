---
title: Przenoszenie tekstu przy użyciu automatyzacji interfejsu użytkownika
description: Zobacz przykład sposobu przechodzenia zawartości tekstowej dokumentu przy użyciu automatyzacji interfejsu użytkownika firmy Microsoft w przyrostach TextUnit.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
ms.openlocfilehash: 1413cac56e3d6358eb58d55eb2fc0ca583147571
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242035"
---
# <a name="traverse-text-using-ui-automation"></a><span data-ttu-id="544e5-103">Przenoszenie tekstu przy użyciu automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="544e5-103">Traverse Text Using UI Automation</span></span>

> [!NOTE]
> <span data-ttu-id="544e5-104">Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="544e5-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="544e5-105">Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="544e5-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="544e5-106">W tym temacie pokazano, jak użyć [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] do przechodzenia zawartości tekstowej dokumentu przez <xref:System.Windows.Automation.Text.TextUnit> przyrosty.</span><span class="sxs-lookup"><span data-stu-id="544e5-106">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to traverse the textual content of a document by <xref:System.Windows.Automation.Text.TextUnit> increments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="544e5-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="544e5-107">Example</span></span>  

 <span data-ttu-id="544e5-108">Poniższy przykład kodu demonstruje sposób przechodzenia zawartości dostawcy tekstu automatyzacji interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="544e5-108">The following code example demonstrates how to traverse the content of a UI Automation text provider.</span></span> <span data-ttu-id="544e5-109"><xref:System.Windows.Automation.Text.TextPatternRange.Move%2A>Metoda przenosi <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> punkty końcowe i <xref:System.Windows.Automation.Text.TextPatternRange> .</span><span class="sxs-lookup"><span data-stu-id="544e5-109">The <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> method moves the <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> and <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> endpoints of a <xref:System.Windows.Automation.Text.TextPatternRange>.</span></span> <span data-ttu-id="544e5-110">Ten zakres tekstu jest zazwyczaj zakresem degeneracji reprezentującym punkt wstawiania tekstu.</span><span class="sxs-lookup"><span data-stu-id="544e5-110">This text range is typically a degenerate range representing the text insertion point.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="544e5-111">Ponieważ tylko tekstowe obiekty osadzone są uważane za część strumienia tekstu, obiekty osadzone, takie jak obrazy, nie wpływają `Move` lub nie zwraca wartości.</span><span class="sxs-lookup"><span data-stu-id="544e5-111">Since only text-based embedded objects are considered part of the text stream, embedded objects such as images do not affect `Move` or its return value.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 <span data-ttu-id="544e5-112">Każda metoda przy użyciu <xref:System.Windows.Automation.Text.TextUnit> będzie przełożyć na następną największą <xref:System.Windows.Automation.Text.TextUnit> obsługiwaną wartość, jeśli dana <xref:System.Windows.Automation.Text.TextUnit> kontrolka nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="544e5-112">Any method using <xref:System.Windows.Automation.Text.TextUnit> will defer to the next largest <xref:System.Windows.Automation.Text.TextUnit> supported if the given <xref:System.Windows.Automation.Text.TextUnit> is not supported by the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="544e5-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="544e5-113">See also</span></span>

- [<span data-ttu-id="544e5-114">Przegląd automatyzacji interfejsu użytkownika — TextPattern</span><span class="sxs-lookup"><span data-stu-id="544e5-114">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="544e5-115">Dodawanie zawartości do pola tekstowego przy użyciu automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="544e5-115">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="544e5-116">Znajdowanie i wyróżnianie tekstu przy użyciu automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="544e5-116">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
- [<span data-ttu-id="544e5-117">Wzorce formantów automatyzacji interfejsu użytkownika — omówienie</span><span class="sxs-lookup"><span data-stu-id="544e5-117">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="544e5-118">Wzorce kontrolek automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="544e5-118">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
