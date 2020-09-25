---
description: '#elif — odwołanie w C#'
title: '#elif — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 383c143792a39bb3abcd255804360ad5e2f8ef74
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168702"
---
# <a name="elif-c-reference"></a>#elif (odwołanie w C#)

`#elif` umożliwia utworzenie złożonej dyrektywy warunkowej. `#elif`Wyrażenie zostanie ocenione, jeśli żadna z powyższych [#if](./preprocessor-if.md) lub nie wszystkie poprzednie, opcjonalne wyrażenia dyrektywy nie będą oceniane `#elif` do `true` . Jeśli `#elif` wyrażenie daje w wyniku `true` , kompilator oblicza cały kod między `#elif` i następną dyrektywy warunkowej. Na przykład:  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 `==`Aby obliczyć wiele symboli, można użyć operatorów (równość), ( `!=` `&&` i), i `||` (lub). Można również grupować symbole i operatory za pomocą nawiasów.  
  
## <a name="remarks"></a>Uwagi  

 `#elif` jest równoważne użyciu:  
  
```csharp
#else  
#if  
```  
  
 Użycie `#elif` jest prostsze, ponieważ każdy z nich `#if` wymaga [#endif](./preprocessor-endif.md), a `#elif` może być używany bez dopasowywania `#endif` .  
  
 Zobacz [#if](./preprocessor-if.md) , aby zapoznać się z przykładem sposobu korzystania z programu `#elif` .  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
