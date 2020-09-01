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
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Jak nadać styl wierszowi w ListView, który implementuje GridView
Ten przykład pokazuje, jak stylować wiersz w <xref:System.Windows.Controls.ListView> kontrolce używającej <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> trybu.  
  
## <a name="example"></a>Przykład  
 Aby określić styl wiersza w <xref:System.Windows.Controls.ListView> kontrolce, należy ustawić <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> <xref:System.Windows.Controls.ListView> kontrolkę. Ustaw styl dla elementów, które są reprezentowane jako <xref:System.Windows.Controls.ListViewItem> obiekty. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Odwołuje się do <xref:System.Windows.Controls.ControlTemplate> obiektów, które są używane do wyświetlania zawartości wiersza.  
  
 Kompletny przykład, w którym następujące przykłady są wyodrębniane z programu, wyświetla kolekcję informacji o utworze, które są przechowywane w bazie danych XML. Każdy utwór w bazie danych ma pole Rating i wartość tego pola określa sposób wyświetlania wiersza informacji o utworze.  
  
 Poniższy przykład pokazuje, jak zdefiniować <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> dla <xref:System.Windows.Controls.ListViewItem> obiektów reprezentujących utwory muzyczne w kolekcji Song. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Obiekty odwołań <xref:System.Windows.Controls.ControlTemplate> , które określają sposób wyświetlania wiersza informacji o utworze.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 Poniższy przykład pokazuje <xref:System.Windows.Controls.ControlTemplate> , że dodaje ciąg tekstowy `"Strongly Recommended"` do wiersza. Ten szablon jest przywoływany w <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> i wyświetla, gdy klasyfikacja utworu ma wartość 5 (pięć). <xref:System.Windows.Controls.ControlTemplate>Zawiera <xref:System.Windows.Controls.GridViewRowPresenter> obiekt, który określa zawartość wiersza w kolumnach, zgodnie z definicją w <xref:System.Windows.Controls.GridView> trybie widoku.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 Poniższy przykład definiuje <xref:System.Windows.Controls.GridView> .  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [— Tematy porad](listview-how-to-topics.md)
- [ListView — Przegląd](listview-overview.md)
- [Tworzenie szablonów i stylów](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
