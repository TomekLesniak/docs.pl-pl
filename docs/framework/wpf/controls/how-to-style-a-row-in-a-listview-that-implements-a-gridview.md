---
title: 'Instrukcje: styl wiersza w ListView, który używa widoku GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 4b8b8e2f1b2d7207a37205d981bf2dab3f65122e
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271948"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="2e7d3-102">Jak nadać styl wierszowi w ListView, który implementuje GridView</span><span class="sxs-lookup"><span data-stu-id="2e7d3-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="2e7d3-103">Ten przykład pokazuje, jak stylować wiersz w <xref:System.Windows.Controls.ListView> kontrolce używającej <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> trybu.</span><span class="sxs-lookup"><span data-stu-id="2e7d3-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e7d3-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="2e7d3-104">Example</span></span>  
 <span data-ttu-id="2e7d3-105">Aby określić styl wiersza w <xref:System.Windows.Controls.ListView> kontrolce, należy ustawić <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> <xref:System.Windows.Controls.ListView> kontrolkę.</span><span class="sxs-lookup"><span data-stu-id="2e7d3-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="2e7d3-106">Ustaw styl dla elementów, które są reprezentowane jako <xref:System.Windows.Controls.ListViewItem> obiekty.</span><span class="sxs-lookup"><span data-stu-id="2e7d3-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="2e7d3-107"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Odwołuje się do <xref:System.Windows.Controls.ControlTemplate> obiektów, które są używane do wyświetlania zawartości wiersza.</span><span class="sxs-lookup"><span data-stu-id="2e7d3-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="2e7d3-108">Kompletny przykład, w którym następujące przykłady są wyodrębniane z programu, wyświetla kolekcję informacji o utworze, które są przechowywane w bazie danych XML.</span><span class="sxs-lookup"><span data-stu-id="2e7d3-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an XML database.</span></span> <span data-ttu-id="2e7d3-109">Każdy utwór w bazie danych ma pole Rating i wartość tego pola określa sposób wyświetlania wiersza informacji o utworze.</span><span class="sxs-lookup"><span data-stu-id="2e7d3-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="2e7d3-110">Poniższy przykład pokazuje, jak zdefiniować <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> dla <xref:System.Windows.Controls.ListViewItem> obiektów reprezentujących utwory muzyczne w kolekcji Song.</span><span class="sxs-lookup"><span data-stu-id="2e7d3-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="2e7d3-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Obiekty odwołań <xref:System.Windows.Controls.ControlTemplate> , które określają sposób wyświetlania wiersza informacji o utworze.</span><span class="sxs-lookup"><span data-stu-id="2e7d3-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="2e7d3-112">Poniższy przykład pokazuje <xref:System.Windows.Controls.ControlTemplate> , że dodaje ciąg tekstowy `"Strongly Recommended"` do wiersza.</span><span class="sxs-lookup"><span data-stu-id="2e7d3-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="2e7d3-113">Ten szablon jest przywoływany w <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> i wyświetla, gdy klasyfikacja utworu ma wartość 5 (pięć).</span><span class="sxs-lookup"><span data-stu-id="2e7d3-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="2e7d3-114"><xref:System.Windows.Controls.ControlTemplate>Zawiera <xref:System.Windows.Controls.GridViewRowPresenter> obiekt, który określa zawartość wiersza w kolumnach, zgodnie z definicją w <xref:System.Windows.Controls.GridView> trybie widoku.</span><span class="sxs-lookup"><span data-stu-id="2e7d3-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="2e7d3-115">Poniższy przykład definiuje <xref:System.Windows.Controls.GridView> .</span><span class="sxs-lookup"><span data-stu-id="2e7d3-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="2e7d3-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2e7d3-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="2e7d3-117">— Tematy porad</span><span class="sxs-lookup"><span data-stu-id="2e7d3-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="2e7d3-118">ListView — Przegląd</span><span class="sxs-lookup"><span data-stu-id="2e7d3-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="2e7d3-119">Tworzenie szablonów i stylów</span><span class="sxs-lookup"><span data-stu-id="2e7d3-119">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
