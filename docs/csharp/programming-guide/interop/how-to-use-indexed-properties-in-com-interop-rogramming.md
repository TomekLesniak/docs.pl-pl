---
title: Jak korzystać z właściwości indeksowanych w programowaniu międzyoperacyjnym modelu COM — Przewodnik programowania w języku C#
description: Dowiedz się, jak indeksowane właściwości poprawiają sposób, w jaki właściwości COM z parametrami są używane w tym przykładzie w języku C#.
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 5f239a0772f734391bd68ef6618ea8ece8e8c9cd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178492"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>Jak używać właściwości indeksowanych w programowaniu międzyoperacyjnym modelu COM (Przewodnik programowania w języku C#)

*Właściwości indeksowane* ulepszają sposób, w jaki właściwości com, które mają parametry są używane w programowaniu języka C#. Właściwości indeksowane współpracują z innymi funkcjami w języku Visual C#, takimi jak [argumenty nazwane i opcjonalne](../classes-and-structs/named-and-optional-arguments.md), nowy typ ([dynamiczny](../../language-reference/builtin-types/reference-types.md)) i [Informacje o typie osadzonym](../../../standard/assembly/embed-types-visual-studio.md), aby usprawnić programowanie Microsoft Office.  
  
 We wcześniejszych wersjach języka C# metody są dostępne jako właściwości tylko wtedy, gdy `get` Metoda nie ma parametrów, a `set` Metoda ma jeden i tylko jeden parametr value. Jednak nie wszystkie właściwości COM spełniają te ograniczenia. Na przykład właściwość programu Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> ma `get` metodę dostępu, która wymaga parametru dla nazwy zakresu. W przeszłości, ponieważ nie można uzyskać dostępu do `Range` właściwości bezpośrednio, należy użyć `get_Range` metody zamiast tego, jak pokazano w poniższym przykładzie.  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 Właściwości indeksowane umożliwiają napisanie następujących danych:  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> W poprzednim przykładzie jest również stosowana funkcja [argumentów opcjonalnych](../classes-and-structs/named-and-optional-arguments.md) , która pozwala pominąć `Type.Missing` .  
  
 Podobnie, aby ustawić wartość `Value` właściwości <xref:Microsoft.Office.Interop.Excel.Range> obiektu w języku C# 3,0 i wcześniejszych, wymagane są dwa argumenty. Jeden dostarcza argument dla opcjonalnego parametru, który określa typ wartości zakresu. Pozostałe dostarczają wartość `Value` właściwości. Poniższe przykłady ilustrują te techniki. Obie wartości mają ustawioną wartość komórki a1 `Name` .
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 Właściwości indeksowane umożliwiają zapisanie w zamian poniższego kodu.  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 Nie można tworzyć własnych właściwości indeksowanych. Funkcja obsługuje tylko użycie istniejących właściwości indeksowanych.  
  
## <a name="example"></a>Przykład  

 Poniższy kod przedstawia kompletny przykład. Aby uzyskać więcej informacji na temat sposobu konfigurowania projektu, który uzyskuje dostęp do interfejsu API pakietu Office, zobacz [jak uzyskać dostęp do obiektów międzyoperacyjności pakietu Office za pomocą funkcji języka C#](./how-to-access-office-onterop-objects.md).
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a>Zobacz też

- [Argumenty nazwane i opcjonalne](../classes-and-structs/named-and-optional-arguments.md)
- [dynamiczna](../../language-reference/builtin-types/reference-types.md)
- [Używanie typu dynamicznego](../types/using-type-dynamic.md)
- [Porada: użycie argumentów nazwanych i opcjonalnych w programowaniu pakietu Office](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [Uzyskiwanie dostępu do obiektów międzyoperacyjności pakietu Office za pomocą funkcji języka C#](./how-to-access-office-onterop-objects.md)
- [Przewodnik: Programowanie Office](./walkthrough-office-programming.md)
