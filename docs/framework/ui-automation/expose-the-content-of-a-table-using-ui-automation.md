---
title: Udostępnianie zawartości tabel za pomocą automatyzacji interfejsu użytkownika
description: Zobacz, jak uwidocznić zawartość tabeli przy użyciu automatyzacji interfejsu użytkownika. Zawartość i wewnętrzne właściwości każdej komórki w formancie tabelarycznym są uwidocznione.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables, exposing content of
- UI Automation, exposing content of tables
- exposing content of tables using UI Automation
ms.assetid: ac3c5eaa-49c7-4653-b83e-532e2a2604a2
ms.openlocfilehash: e089f1371dba476b1f75f9fffe7d224c840f8d80
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276519"
---
# <a name="expose-the-content-of-a-table-using-ui-automation"></a><span data-ttu-id="27c9a-104">Udostępnianie zawartości tabel za pomocą automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="27c9a-104">Expose the Content of a Table Using UI Automation</span></span>

> [!NOTE]
> <span data-ttu-id="27c9a-105">Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="27c9a-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="27c9a-106">Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="27c9a-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="27c9a-107">W tym temacie pokazano, jak [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] można użyć, aby uwidocznić zawartość i wewnętrzne właściwości każdej komórki w formancie tabelarycznym.</span><span class="sxs-lookup"><span data-stu-id="27c9a-107">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose the content and intrinsic properties of each cell within a tabular control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27c9a-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="27c9a-108">Example</span></span>  

 <span data-ttu-id="27c9a-109">Poniższy przykład kodu demonstruje, jak uzyskać element <xref:System.Windows.Automation.AutomationElement> reprezentujący zawartość komórki tabeli; są również uzyskiwane właściwości komórek, takie jak indeksy wierszy i kolumn, zakresy wierszy i kolumn oraz informacje nagłówka wiersza i kolumny.</span><span class="sxs-lookup"><span data-stu-id="27c9a-109">The following code example demonstrates how to obtain a <xref:System.Windows.Automation.AutomationElement> that represents the content of a table cell; cell properties such as row and column indices, row and column spans, and row and column header information are also obtained.</span></span> <span data-ttu-id="27c9a-110">W tym przykładzie zastosowano procedurę obsługi zdarzeń zmiany fokusu, aby symulować przechodzenie klawiatury w formancie tabelarycznym, który implementuje [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27c9a-110">This example uses a focus change event handler to simulate keyboard traversal of a tabular control that implements [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="27c9a-111">Informacje dla każdego elementu tabeli są ujawniane w przypadku zdarzenia zmiany fokusu.</span><span class="sxs-lookup"><span data-stu-id="27c9a-111">Information for each table item is exposed on a focus change event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27c9a-112">Ponieważ zmiany ostrości są globalnymi zdarzeniami pulpitu, zdarzenia zmiany fokusu spoza tabeli powinny być filtrowane.</span><span class="sxs-lookup"><span data-stu-id="27c9a-112">Since focus changes are global desktop events, focus change events outside the table should be filtered.</span></span> <span data-ttu-id="27c9a-113">Zobacz [przykład TrackFocus](/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) dla powiązanej implementacji.</span><span class="sxs-lookup"><span data-stu-id="27c9a-113">See the [TrackFocus Sample](/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) for a related implementation.</span></span>  
  
 [!code-csharp[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#starttarget)]
 [!code-vb[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#starttarget)]  
[!code-csharp[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#gettableelement)]
[!code-vb[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#gettableelement)]  
[!code-csharp[UIATableItemPattern_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#101)]
[!code-vb[UIATableItemPattern_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#101)]  
[!code-csharp[UIATableItemPattern_snip#1015](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#1015)]
[!code-vb[UIATableItemPattern_snip#1015](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#1015)]  
[!code-csharp[UIATableItemPattern_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#102)]
[!code-vb[UIATableItemPattern_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#102)]  
[!code-csharp[UIATableItemPattern_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#103)]
[!code-vb[UIATableItemPattern_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="27c9a-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="27c9a-114">See also</span></span>

- [<span data-ttu-id="27c9a-115">Wzorce formantów automatyzacji interfejsu użytkownika — omówienie</span><span class="sxs-lookup"><span data-stu-id="27c9a-115">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="27c9a-116">Wzorce kontrolek automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="27c9a-116">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="27c9a-117">Implementacja wzorca formantu tabeli automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="27c9a-117">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="27c9a-118">Implementacja wzorca kontrolki TableItem dla automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="27c9a-118">Implementing the UI Automation TableItem Control Pattern</span></span>](implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="27c9a-119">Implementacja wzorca kontrolki siatki automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="27c9a-119">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="27c9a-120">Implementacja wzorca kontrolki GridItem dla automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="27c9a-120">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
