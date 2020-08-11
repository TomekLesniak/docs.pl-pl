---
title: Wyrażenia Lambda w PLINQ i TPL
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
ms.openlocfilehash: 469c164630e1dab84b3d54c16c43d031ebf560ed
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063773"
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a>Wyrażenia Lambda w PLINQ i TPL

Biblioteka zadań równoległych (TPL) zawiera wiele metod, które mają jedną z <xref:System.Func%601?displayProperty=nameWithType> lub <xref:System.Action?displayProperty=nameWithType> rodzinę delegatów jako parametry wejściowe. Te Delegaty służą do przekazywania niestandardowej logiki programu do pętli równoległej, zadania lub zapytania. Przykłady kodu dla TPL oraz PLINQ używają wyrażeń lambda do tworzenia wystąpień tych delegatów jako wbudowanych bloków kodu. Ten temat zawiera krótkie wprowadzenie do funkcji Func i Action oraz pokazuje, jak używać wyrażeń lambda w bibliotece zadań równoległych i PLINQ.

> [!NOTE]
> Aby uzyskać więcej informacji na temat ogólnie delegowanych delegatów, zobacz [delegats](../../csharp/programming-guide/delegates/index.md) and [delegats](../../visual-basic/programming-guide/language-features/delegates/index.md). Aby uzyskać więcej informacji na temat wyrażeń lambda w języku C# i Visual Basic, zobacz [wyrażenia lambda](../../csharp/language-reference/operators/lambda-expressions.md) i [wyrażenia lambda](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="func-delegate"></a>Obiekt delegowany Func

`Func`Delegat hermetyzuje metodę, która zwraca wartość. W `Func` podpisie, ostatni lub po prawej stronie, parametr typu zawsze określa typ zwracany. Jedną z typowych przyczyn błędów kompilatora jest próba przekazania dwóch parametrów wejściowych do <xref:System.Func%602?displayProperty=nameWithType> ; w rzeczywistości ten typ przyjmuje tylko jeden parametr wejściowy. Platforma .NET definiuje 17 wersji systemów `Func` : <xref:System.Func%601?displayProperty=nameWithType> , <xref:System.Func%602?displayProperty=nameWithType> , <xref:System.Func%603?displayProperty=nameWithType> i tak dalej <xref:System.Func%6017?displayProperty=nameWithType> .

## <a name="action-delegate"></a>Delegat akcji

<xref:System.Action?displayProperty=nameWithType>Delegat hermetyzuje metodę (sub in Visual Basic), która nie zwraca wartości. W `Action` sygnaturze typu parametry typu reprezentują tylko parametry wejściowe. Podobnie jak `Func` platforma .NET definiuje 17 wersji programu `Action` , z wersji, która nie ma parametrów typu w górę za pośrednictwem wersji zawierającej 16 parametrów typu.

## <a name="example"></a>Przykład

Poniższy przykład dla <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> metody pokazuje, jak przedstawić delegatów funkcji Func i Action przy użyciu wyrażeń lambda.

[!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
[!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]

## <a name="see-also"></a>Zobacz także

- [Programowanie równoległe](index.md)
