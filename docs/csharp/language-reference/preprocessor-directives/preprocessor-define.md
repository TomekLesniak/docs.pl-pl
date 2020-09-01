---
description: '#Definiowanie — odwołanie w C#'
title: '#Definiowanie — odwołanie w C#'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: a37f883a249ec74b66769ee40b84b20e8568c451
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132342"
---
# <a name="define-c-reference"></a>#define (odwołanie w C#)
Służy `#define` do definiowania symbolu. Jeśli używasz symbolu jako wyrażenia, które jest przesyłane do dyrektywy [#if](./preprocessor-if.md) , wyrażenie będzie oceniane do `true` , jak pokazano na poniższym przykładzie:  

 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> `#define`Dyrektywy nie można użyć do deklarowania wartości stałych, jak zwykle jest to wykonywane w C i C++. Stałe w języku C# są najlepiej zdefiniowane jako statyczne elementy członkowskie klasy lub struktury. Jeśli masz kilka takich stałych, rozważ utworzenie oddzielnych "stałych" klasy, aby je przechowywać.  
  
 Symbole mogą służyć do określania warunków kompilacji. Możesz sprawdzić, czy symbol ma [#if](./preprocessor-if.md) lub [#elif](./preprocessor-elif.md). Można również użyć <xref:System.Diagnostics.ConditionalAttribute> do wykonania kompilacji warunkowej.  
  
 Można zdefiniować symbol, ale nie można przypisać wartości do symbolu. `#define`Dyrektywa musi znajdować się w pliku przed użyciem dowolnych instrukcji, które nie są również dyrektywami preprocesora.  
  
 Można również zdefiniować symbol z opcją [-define](../compiler-options/define-compiler-option.md) kompilatora. Możesz oddefiniować symbol z [#undef](./preprocessor-undef.md).  
  
 Symbol zdefiniowany za pomocą `-define` lub with nie `#define` powoduje konfliktu ze zmienną o tej samej nazwie. Oznacza to, że nazwa zmiennej nie powinna być przenoszona do dyrektywy preprocesora i symbol może być oceniany tylko przez dyrektywę preprocesora.  
  
 Zakres symbolu, który został utworzony przy użyciu, `#define` to plik, w którym został zdefiniowany symbol.  
  
 Jak pokazano na poniższym przykładzie, należy umieścić `#define` dyrektywy w górnej części pliku.  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 Aby zapoznać się z przykładem, jak wydefiniować symbol, zobacz [#undef](./preprocessor-undef.md).  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
- [const](../keywords/const.md)
- [Instrukcje: Kompilowanie warunkowe ze śledzeniem i debugowaniem](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [#undef](./preprocessor-undef.md)
- [#if](./preprocessor-if.md)
