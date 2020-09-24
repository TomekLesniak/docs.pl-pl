---
title: Debugowanie drzew wyrażeń w programie Visual Studio (C#)
description: Dowiedz się więcej o właściwości DebugView w programie Visual Studio. Zobacz, jak używać tej właściwości do analizowania struktury i zawartości drzew wyrażeń.
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 5dcf56f96ecdbfdc3f4cb171fdb30b96456b59c9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91154135"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a>Debugowanie drzew wyrażeń w programie Visual Studio (C#)

Można analizować strukturę i zawartość drzew wyrażeń podczas debugowania aplikacji. Aby uzyskać szybki przegląd struktury drzewa wyrażeń, można użyć `DebugView` właściwości, która reprezentuje drzewa wyrażeń [przy użyciu specjalnej składni](debugview-syntax.md). (Uwaga, która `DebugView` jest dostępna tylko w trybie debugowania).  

![Zrzut ekranu przedstawiający DebugView drzewa wyrażenia w debugerze programu VS.](media/debugging-expression-trees-in-visual-studio/debugview-expression-tree.png)

Ponieważ `DebugView` jest ciągiem, można użyć [wbudowanego wizualizatora tekstu](/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) , aby wyświetlić go w wielu wierszach, wybierając **wizualizator tekstu** z ikony lupy obok `DebugView` etykiety.

 ![Zrzut ekranu przedstawiający wizualizator tekstu stosowany do wyników DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-debugview.png)

Alternatywnie można zainstalować i używać [wizualizatora niestandardowego](/visualstudio/debugger/create-custom-visualizers-of-data) dla drzew wyrażeń, takich jak:

- [Wyrażenia](https://github.com/agileobjects/ReadableExpressions) możliwe do odczytu ([licencja mit](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), dostępna w [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renderuje drzewo wyrażenia jako kod języka C# z możliwością programowania z różnymi opcjami renderowania:

  ![Zrzut ekranu przedstawiający wizualizator wyrażeń możliwych do odczytu.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- [Wizualizator drzewa wyrażeń](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([licencja mit](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) zawiera widok drzewa drzewa wyrażenia i jego poszczególne węzły:

  ![Zrzut ekranu przedstawiający wizualizator drzewa wyrażeń.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Aby otworzyć wizualizator dla drzewa wyrażenia  
  
1. Kliknij ikonę lupy, która pojawia się obok drzewa wyrażenia w **etykietkach**danych, oknie **czujki** , oknie **autostarts** lub w oknie **zmiennych lokalnych** .  

    Zostanie wyświetlona lista dostępnych wizualizatorów.:

    ![Zrzut ekranu przedstawiający otwieranie wizualizatorów z programu Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers.png)

2. Kliknij wizualizator, którego chcesz użyć.  
  
## <a name="see-also"></a>Zobacz też

- [Drzewa wyrażeń (C#)](./index.md)
- [Debugowanie w Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Tworzenie niestandardowych wizualizatorów](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView` obowiązuje](debugview-syntax.md)
