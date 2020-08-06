---
title: Zachowanie położenia okna podręcznego
description: Dowiedz się, jak przy użyciu właściwości określić położenie okna podręcznego platformy Windows Presentation Foundation względem kontrolki, myszy lub ekranu.
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 8184805518bc56693ead4c7d1f0e9a1bff9bff8f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167742"
---
# <a name="popup-placement-behavior"></a>Zachowanie położenia okna podręcznego
Kontrolka <xref:System.Windows.Controls.Primitives.Popup> wyświetla zawartość w osobnym oknie znajdującym się nad aplikacją. Możesz określić pozycję klasy <xref:System.Windows.Controls.Primitives.Popup> względem kontrolki, myszy lub ekranu przy użyciu właściwości <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> i <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>.  Razem te właściwości zapewniają elastyczność w określaniu pozycji klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
> Klasy <xref:System.Windows.Controls.ToolTip> i <xref:System.Windows.Controls.ContextMenu> również definiują tych pięć właściwości i zachowują się podobnie.  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>Pozycjonowanie okna podręcznego  
 Położenie klasy <xref:System.Windows.Controls.Primitives.Popup> można ustalić względem klasy <xref:System.Windows.UIElement> lub całego ekranu.  W poniższym przykładzie tworzone są cztery kontrolki <xref:System.Windows.Controls.Primitives.Popup> względem klasy <xref:System.Windows.UIElement>, w tym przypadku obrazu. Wszystkie kontrolki <xref:System.Windows.Controls.Primitives.Popup> mają właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> ustawioną na wartość `image1`, ale każda klasa <xref:System.Windows.Controls.Primitives.Popup> ma inną wartość właściwości położenia.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 Na poniższej ilustracji przedstawiono obraz i kontrolki <xref:System.Windows.Controls.Primitives.Popup>  
  
 ![Obraz z czterema kontrolkami okna podręcznego](./media/popup-placement-behavior/popup-placement-intro.png "Obraz z czterema oknami podręcznymi")
  
 W tym prostym przykładzie pokazano, jak ustawić właściwości <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> i <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, ale używając właściwości <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> i <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>, masz jeszcze większą kontrolę nad położeniem klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definicje terminów: anatomia okna podręcznego  
 Poniższe terminy są przydatne w zrozumieniu, jak właściwości <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> i <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> są powiązane ze sobą i klasą <xref:System.Windows.Controls.Primitives.Popup>:  
  
- Obiekt docelowy  
  
- Obszar docelowy  
  
- Źródło docelowe  
  
- Punkt wyrównania okna podręcznego  
  
 Dzięki tym terminom można w wygodny sposób odnosić się do różnych aspektów klasy <xref:System.Windows.Controls.Primitives.Popup> i skojarzonej z nim kontrolki.  
  
### <a name="target-object"></a>Obiekt docelowy  
 *Obiekt docelowy* to element, z którym skojarzona jest klasa <xref:System.Windows.Controls.Primitives.Popup>. Jeśli właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> jest ustawiona, określa obiekt docelowy.  Jeśli właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> nie jest ustawiona, a klasa <xref:System.Windows.Controls.Primitives.Popup> ma element nadrzędny, ten element nadrzędny jest obiektem docelowym.  Jeśli nie ma wartości <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> ani elementu nadrzędnego, nie ma obiektu docelowego, a klasa <xref:System.Windows.Controls.Primitives.Popup> jest pozycjonowana względem ekranu.  
  
 W poniższym przykładzie tworzona jest klasa <xref:System.Windows.Controls.Primitives.Popup>, która jest elementem podrzędnym klasy <xref:System.Windows.Controls.Canvas>.  W tym przykładzie nie jest ustawiana właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> w klasie <xref:System.Windows.Controls.Primitives.Popup>. Wartość domyślna dla właściwości <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> to <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, dlatego klasa <xref:System.Windows.Controls.Primitives.Popup> pojawia się pod klasą <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 Na poniższej ilustracji widać, że klasa <xref:System.Windows.Controls.Primitives.Popup> jest pozycjonowana względem klasy <xref:System.Windows.Controls.Canvas>.  
  
 ![Kontrolka okna podręcznego bez właściwości PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Okno podręczne bez właściwości PlacementTarget.")  

 W poniższym przykładzie tworzona jest klasa <xref:System.Windows.Controls.Primitives.Popup>, która jest elementem podrzędnym klasy <xref:System.Windows.Controls.Canvas>, ale tym razem właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> ma ustawioną wartość `ellipse1` i dlatego okno podręczne jest wyświetlane pod klasą <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 Na poniższej ilustracji widać, że klasa <xref:System.Windows.Controls.Primitives.Popup> jest pozycjonowana względem klasy <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Okno podręczne pozycjonowane względem elipsy](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Okno podręczne z właściwością PlacementTarget")
  
> [!NOTE]
> Dla klasy <xref:System.Windows.Controls.ToolTip> wartość domyślna właściwości <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> to <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Dla klasy <xref:System.Windows.Controls.ContextMenu> wartość domyślna właściwości <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> to <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Te wartości są wyjaśnione później w sekcji „Jak właściwości współdziałają ze sobą”.  
  
### <a name="target-area"></a>Obszar docelowy  
 *Obszar docelowy* jest obszarem na ekranie, względem którego określana jest klasa <xref:System.Windows.Controls.Primitives.Popup>. W poprzednich przykładach klasa <xref:System.Windows.Controls.Primitives.Popup> jest wyrównana do granic obiektu docelowego, ale w niektórych przypadkach klasa <xref:System.Windows.Controls.Primitives.Popup> jest wyrównana do innych granic, nawet jeśli klasa <xref:System.Windows.Controls.Primitives.Popup> ma obiekt docelowy.  Jeśli właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest ustawiona, obszar docelowy jest inny niż granice obiektu docelowego.  
  
 W poniższym przykładzie tworzone są dwa obiekty <xref:System.Windows.Controls.Canvas>, każdy zawierający klasę <xref:System.Windows.Shapes.Rectangle> i <xref:System.Windows.Controls.Primitives.Popup>.  W obu przypadkach obiekt docelowy dla klasy <xref:System.Windows.Controls.Primitives.Popup> to klasa <xref:System.Windows.Controls.Canvas>. Klasa <xref:System.Windows.Controls.Primitives.Popup> w pierwszej klasie <xref:System.Windows.Controls.Canvas> ma ustawioną właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, a jej właściwości <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A> i <xref:System.Windows.Rect.Height%2A> mają ustawione odpowiednio wartości 50, 50, 50 i 100. Klasa <xref:System.Windows.Controls.Primitives.Popup> w drugiej klasie <xref:System.Windows.Controls.Canvas> nie ma ustawionej właściwości <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  Z tego powodu pierwsza klasa <xref:System.Windows.Controls.Primitives.Popup> jest pozycjonowana pod właściwością <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, a druga klasa <xref:System.Windows.Controls.Primitives.Popup> jest pozycjonowane pod klasą <xref:System.Windows.Controls.Canvas>. Każda klasa <xref:System.Windows.Controls.Canvas> zawiera również klasę <xref:System.Windows.Shapes.Rectangle>, która ma takie same granice jak właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> dla pierwszej klasy <xref:System.Windows.Controls.Primitives.Popup>.  Zauważ, że właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> nie tworzy widocznego elementu w aplikacji; w przykładzie tworzona jest klasa <xref:System.Windows.Shapes.Rectangle> reprezentujące właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 Na poniższej ilustracji przedstawiono wynik poprzedniego przykładu.  
  
 ![Okno podręczne z właściwością PlacementRectangle i bez niej](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Okno podręczne z właściwością PlacementRectangle i bez niej.")  

### <a name="target-origin-and-popup-alignment-point"></a>Źródło docelowe i punkt wyrównania okna podręcznego  
 *Źródło docelowe* i *punkt wyrównania okna podręcznego* są punktami odniesienia dla odpowiednio obszaru docelowego i okna podręcznego służącymi do pozycjonowania. Przy użyciu właściwości <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> i <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> możesz odsunąć okno podręczne od obszaru docelowego.  Właściwości <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> i <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> są względne wobec źródła docelowego i punktu wyrównania okna podręcznego. Wartość właściwości <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> określa, gdzie znajdują się źródło docelowe i punkt wyrównania okna podręcznego.  
  
 W poniższym przykładzie tworzona jest klasa <xref:System.Windows.Controls.Primitives.Popup> oraz ustawiane są właściwości <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> i <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> na wartość 20.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> jest ustawiona na wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (domyślnie), więc źródłem docelowym jest lewy dolny róg obszaru docelowego, a punktem wyrównania okna podręcznego jest lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 Na poniższej ilustracji przedstawiono wynik poprzedniego przykładu.  
  
 ![Położenie okna podręcznego z punktem wyrównania źródła docelowego](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Okno podręczne z właściwością HorizontalOffset i VerticalOffset.")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>Jak właściwości współdziałają ze sobą  
 Aby ustalić prawidłowy obszar docelowy, źródło docelowe i punkt wyrównania okna podręcznego, należy wziąć pod uwagę wartości właściwości <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> i <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> razem.  Na przykład jeśli właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, nie istnieje obiekt docelowy, właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest ignorowane, a obszarem docelowym są granice wskaźnika myszy. Z drugiej strony, jeśli właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> lub element nadrzędny określa obiekt docelowy, a właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> określa obszar docelowy.  
  
 W poniższej tabeli opisano obiekt docelowy, obszar docelowy, źródło docelowe i punkt wyrównania okna podręcznego oraz wskazano, czy właściwości <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> i <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> są używane dla każdej wartości wyliczenia właściwości <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Obiekt docelowy|Obszar docelowy|Źródło docelowe|Punkt wyrównania okna podręcznego|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Nie dotyczy. Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> jest ignorowana.|Ekran lub właściwość<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, jeśli jest ustawiona.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest określona względem ekranu.|Lewy górny róg obszaru docelowego.|Lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Nie dotyczy. Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> jest ignorowana.|Ekran lub właściwość<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, jeśli jest ustawiona.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest określona względem ekranu.|Lewy górny róg obszaru docelowego.|Lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> lub element nadrzędny.|Obiekt docelowy lub właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, jeśli jest ustawiona.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest określona względem obiektu docelowego.|Lewy dolny róg obszaru docelowego.|Lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> lub element nadrzędny.|Obiekt docelowy lub właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, jeśli jest ustawiona.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest określona względem obiektu docelowego.|Środek obszaru docelowego.|Środek klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> lub element nadrzędny.|Obiekt docelowy lub właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, jeśli jest ustawiona.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest określona względem obiektu docelowego.|Zdefiniowane przez delegat <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Zdefiniowane przez delegat <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> lub element nadrzędny.|Obiekt docelowy lub właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, jeśli jest ustawiona.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest określona względem obiektu docelowego.|Lewy górny róg obszaru docelowego.|Prawy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Nie dotyczy. Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> jest ignorowana.|Granice wskaźnika myszy. Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest ignorowana.|Lewy dolny róg obszaru docelowego.|Lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Nie dotyczy. Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> jest ignorowana.|Granice wskaźnika myszy. Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest ignorowana.|Lewy górny róg obszaru docelowego.|Lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> lub element nadrzędny.|Obiekt docelowy lub właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, jeśli jest ustawiona.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest określona względem obiektu docelowego.|Lewy górny róg obszaru docelowego.|Lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> lub element nadrzędny.|Obiekt docelowy lub właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, jeśli jest ustawiona.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest określona względem obiektu docelowego.|Lewy górny róg obszaru docelowego.|Lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> lub element nadrzędny.|Obiekt docelowy lub właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, jeśli jest ustawiona.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest określona względem obiektu docelowego.|Prawy górny róg obszaru docelowego.|Lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> lub element nadrzędny.|Obiekt docelowy lub właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, jeśli jest ustawiona.  Właściwość <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> jest określona względem obiektu docelowego.|Lewy górny róg obszaru docelowego.|Lewy dolny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 Na poniższych ilustracjach przedstawiono klasę <xref:System.Windows.Controls.Primitives.Popup>, obszar docelowy, źródło docelowe i punkt wyrównania okna podręcznego dla każdej wartości właściwości <xref:System.Windows.Controls.Primitives.PlacementMode>. Na każdym rysunku obszar docelowy jest żółty, a klasa <xref:System.Windows.Controls.Primitives.Popup> jest niebieska.  
  
 ![Okno podręczne z położeniem Absolute lub AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "Właściwość Placement ma wartość Absolute lub AbsolutePoint.")
  
 ![Okno podręczne z położeniem Bottom](./media/popup-placement-behavior/popup-placement-bottom.png "Właściwość Placement ma wartość Bottom.")
  
 ![Okno podręczne z położeniem Center](./media/popup-placement-behavior/popup-placement-center.png "Właściwość Placement ma wartość Center.")
  
 ![Okno podręczne z położeniem Left](./media/popup-placement-behavior/popup-placement-left.png "Właściwość Placement ma wartość Left.")
  
 ![Okno podręczne z położeniem Mouse](./media/popup-placement-behavior/popup-placement-mouse.png "Właściwość Placement ma wartość Mouse.")  
  
 ![Okno podręczne z położeniem MousePoint](./media/popup-placement-behavior/popup-placement-mousepoint.png "Właściwość Placement ma wartość MousePoint.")  
  
 ![Okno podręczne z położeniem Relative lub RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "Właściwość Placement ma wartość Relative lub RelativePoint.")
  
 ![Okno podręczne z położeniem Right](./media/popup-placement-behavior/popup-placement-right.png "Właściwość Placement ma wartość Right.")
  
 ![Okno podręczne z położeniem Top](./media/popup-placement-behavior/popup-placement-top.png "Właściwość Placement ma wartość Top.")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Gdy okno podręczne napotka krawędź ekranu  
 Ze względów bezpieczeństwa klasa <xref:System.Windows.Controls.Primitives.Popup> nie może być ukryta przez brzeg ekranu. Gdy klasa <xref:System.Windows.Controls.Primitives.Popup> napotka krawędź ekranu, dzieje się jedna z trzech następujących rzeczy:  
  
- Okno podręczne jest wyrównywane do krawędzi ekranu, która zasłaniałaby klasę <xref:System.Windows.Controls.Primitives.Popup>.  
  
- Okno podręczne używa innego punktu wyrównania okna podręcznego.  
  
- Okno podręczne używa innego źródła docelowego i punktu wyrównania okna podręcznego.  
  
 Te opcje są opisane w dalszej części tej sekcji.  
  
 Zachowanie klasy <xref:System.Windows.Controls.Primitives.Popup> w chwili napotkania krawędzi ekranu zależy od wartości właściwości <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> i tego, którą krawędź napotka okno podręczne. W poniższej tabeli podsumowano zachowanie, gdy klasa <xref:System.Windows.Controls.Primitives.Popup> napotka krawędź ekranu dla każdej wartości właściwości <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Górna krawędź|Dolna krawędź|Lewa krawędź|Prawa krawędź|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Wyrównanie do górnej krawędzi.|Wyrównanie do dolnej krawędzi.|Wyrównanie do lewej krawędzi.|Wyrównanie do prawej krawędzi.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Wyrównanie do górnej krawędzi.|Punkt wyrównania okna podręcznego zmieni się na lewy dolny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|Wyrównanie do lewej krawędzi.|Punkt wyrównania okna podręcznego zmieni się na prawy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Wyrównanie do górnej krawędzi.|Źródło docelowe zmieni się na lewy górny róg obszaru docelowego, a punkt wyrównania okna podręcznego zmieni się na lewy dolny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|Wyrównanie do lewej krawędzi.|Wyrównanie do prawej krawędzi.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Wyrównanie do górnej krawędzi.|Wyrównanie do dolnej krawędzi.|Wyrównanie do lewej krawędzi.|Wyrównanie do prawej krawędzi.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Wyrównanie do górnej krawędzi.|Wyrównanie do dolnej krawędzi.|Źródło docelowe zmieni się na prawy górny róg obszaru docelowego, a punkt wyrównania okna podręcznego zmieni się na lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|Wyrównanie do prawej krawędzi.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Wyrównanie do górnej krawędzi.|Źródło docelowe zmieni się na lewy górny róg obszaru docelowego (granice wskaźnika myszy), a punkt wyrównania okna podręcznego zmieni się na lewy dolny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|Wyrównanie do lewej krawędzi.|Wyrównanie do prawej krawędzi.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Wyrównanie do górnej krawędzi.|Punkt wyrównania okna podręcznego zmieni się na lewy dolny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|Wyrównanie do lewej krawędzi.|Punkt wyrównania okna podręcznego zmieni się na prawy górny róg okna podręcznego.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Wyrównanie do górnej krawędzi.|Wyrównanie do dolnej krawędzi.|Wyrównanie do lewej krawędzi.|Wyrównanie do prawej krawędzi.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Wyrównanie do górnej krawędzi.|Punkt wyrównania okna podręcznego zmieni się na lewy dolny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|Wyrównanie do lewej krawędzi.|Punkt wyrównania okna podręcznego zmieni się na prawy górny róg okna podręcznego.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Wyrównanie do górnej krawędzi.|Wyrównanie do dolnej krawędzi.|Wyrównanie do lewej krawędzi.|Źródło docelowe zmieni się na lewy górny róg obszaru docelowego, a punkt wyrównania okna podręcznego zmieni się na prawy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Źródło docelowe zmieni się na lewy dolny róg obszaru docelowego, a punkt wyrównania okna podręcznego zmieni się na lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>. Efekty jest taki sam, jak w przypadku, gdy właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Wyrównanie do dolnej krawędzi.|Wyrównanie do lewej krawędzi.|Wyrównanie do prawej krawędzi.|  
  
### <a name="aligning-to-the-screen-edge"></a>Wyrównywanie do krawędzi ekranu  
 Klasa <xref:System.Windows.Controls.Primitives.Popup> może wyrównać się do krawędzi ekranu, zmieniając swoje położenie tak, aby cała klasa <xref:System.Windows.Controls.Primitives.Popup> była widoczna na ekranie.  Gdy tak się stanie, odległość między źródłem docelowym a punktem wyrównania okna podręcznego może być inna niż wartości właściwości <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> i <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. Gdy właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center> lub <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, klasa <xref:System.Windows.Controls.Primitives.Popup> wyrównuje się do każdej krawędzi ekranu.  Załóżmy na przykład, że klasa <xref:System.Windows.Controls.Primitives.Popup> ma właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ustawioną na wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> i właściwość <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> ustawioną na wartość 100.  Jeśli dolna krawędź ekranu ukrywa całą klasę <xref:System.Windows.Controls.Primitives.Popup> lub jej część, klasa <xref:System.Windows.Controls.Primitives.Popup> zmienia położenie wzdłuż dolnej krawędzi ekranu, a odległość w pionie między źródłem docelowym a punktem wyrównania okna podręcznego wynosi mniej niż 100. Przedstawiono to na poniższej ilustracji.  
  
 ![Okno podręczne wyrównane do krawędzi ekranu](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Okno podręczne wyrównane do krawędzi ekranu.")
  
### <a name="changing-the-popup-alignment-point"></a>Zmiana punktu wyrównania okna podręcznego  
 Jeśli właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> lub <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, punkt wyrównania okna podręcznego zmieni się, gdy okno podręczne napotka dolną lub prawą krawędź ekranu.  
  
 Na poniższej ilustracji przedstawiono, że gdy dolna krawędź ekranu ukrywa całą klasę <xref:System.Windows.Controls.Primitives.Popup> lub jej część, punkt wyrównania okna podręcznego to lewy dolny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nowy punkt wyrównania ze względu na dolną krawędź ekranu](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Okno podręczne napotyka dolną krawędź ekranu i zmienia punkt wyrównania okna podręcznego.")  

 Na poniższej ilustracji przedstawiono, że gdy klasa <xref:System.Windows.Controls.Primitives.Popup> jest ukryta przez prawą krawędź ekranu, punkt wyrównania okna podręcznego to prawy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nowy punkt wyrównania okna podręcznego ze względu na krawędź ekranu](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Okno podręczne napotyka prawą krawędź ekranu i zmienia punkt wyrównania okna podręcznego.")
  
 Jeśli klasa <xref:System.Windows.Controls.Primitives.Popup> napotyka dolną i prawą krawędź ekranu, punkt wyrównania okna podręcznego to prawy dolny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Zmiana źródła docelowego i punktu wyrównania okna podręcznego  
 Gdy właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right> lub <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, źródło docelowe i punkt wyrównania okna podręcznego ulegają zmianie, jeśli zostanie napotkana dana krawędź ekranu.  Krawędź ekranu powodująca zmianę położenia zależy od wartości właściwości <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
 Na poniższej ilustracji przedstawiono, że gdy właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, a klasa <xref:System.Windows.Controls.Primitives.Popup> napotka dolną krawędź ekranu, źródło docelowe to lewy górny róg obszaru docelowego, a punkt wyrównania okna podręcznego to lewy dolny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nowy punkt wyrównania ze względu na dolną krawędź ekranu](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Właściwość Placement ma wartość Bottom, a okno podręczne napotyka dolną krawędź ekranu.")
  
 Na poniższej ilustracji przedstawiono, że gdy właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, a klasa <xref:System.Windows.Controls.Primitives.Popup> napotka lewą krawędź ekranu, źródło docelowe to prawy górny róg obszaru docelowego, a punkt wyrównania okna podręcznego to lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nowy punkt wyrównania ze względu na lewą krawędź ekranu](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Właściwość Placement ma wartość Left, a okno podręczne napotyka lewą krawędź ekranu.")  
  
 Na poniższej ilustracji przedstawiono, że gdy właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, a klasa <xref:System.Windows.Controls.Primitives.Popup> napotka prawą krawędź ekranu, źródło docelowe to lewy górny róg obszaru docelowego, a punkt wyrównania okna podręcznego to prawy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nowy punkt wyrównania ze względu na prawą krawędź ekranu](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Właściwość Placement ma wartość Right, a okno podręczne napotyka prawą krawędź ekranu.")  

 Na poniższej ilustracji przedstawiono, że gdy właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, a klasa <xref:System.Windows.Controls.Primitives.Popup> napotka górną krawędź ekranu, źródło docelowe to lewy dolny róg obszaru docelowego, a punkt wyrównania okna podręcznego to lewy górny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nowy punkt wyrównania ze względu na górną krawędź ekranu](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Właściwość Placement ma wartość Top, a okno podręczne napotyka górną krawędź ekranu.")  
  
 Na poniższej ilustracji przedstawiono, że gdy właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ma wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, a klasa <xref:System.Windows.Controls.Primitives.Popup> napotka dolną krawędź ekranu, źródło docelowe to lewy górny róg obszaru docelowego (granice wskaźnika myszy), a punkt wyrównania okna podręcznego to lewy dolny róg klasy <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![nowy punkt wyrównania ze względu bliskość wskaźnika myszy do krawędzi ekranu](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Właściwość Placement ma wartość Mouse, a okno podręczne napotyka dolną krawędź ekranu.")
  
### <a name="customizing-popup-placement"></a>Dostosowywanie położenia okna podręcznego  
 Możesz dostosować źródło docelowe i punkt wyrównania okna podręcznego, ustawiając właściwość <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> na wartość <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Następnie zdefiniuj delegata <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>, który zwraca zestaw możliwych punktów umieszczania i osi podstawowych (w kolejności preferencji) dla klasy <xref:System.Windows.Controls.Primitives.Popup>. Zostanie wybrany punkt pokazujący największą część klasy <xref:System.Windows.Controls.Primitives.Popup>.  Pozycja klasy <xref:System.Windows.Controls.Primitives.Popup> jest automatycznie dostosowywana, jeśli klasa <xref:System.Windows.Controls.Primitives.Popup> jest ukryta przez brzeg ekranu. Aby zapoznać się z przykładem, zobacz [Określanie niestandardowego położenia okna podręcznego](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Zobacz także

- [Przykład położenia okna podręcznego](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
