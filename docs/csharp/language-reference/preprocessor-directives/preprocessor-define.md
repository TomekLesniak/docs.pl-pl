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
# <a name="define-c-reference"></a><span data-ttu-id="a8b86-103">#define (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="a8b86-103">#define (C# Reference)</span></span>
<span data-ttu-id="a8b86-104">Służy `#define` do definiowania symbolu.</span><span class="sxs-lookup"><span data-stu-id="a8b86-104">You use `#define` to define a symbol.</span></span> <span data-ttu-id="a8b86-105">Jeśli używasz symbolu jako wyrażenia, które jest przesyłane do dyrektywy [#if](./preprocessor-if.md) , wyrażenie będzie oceniane do `true` , jak pokazano na poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a8b86-105">When you use the symbol as the expression that's passed to the [#if](./preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  

 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="a8b86-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a8b86-106">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8b86-107">`#define`Dyrektywy nie można użyć do deklarowania wartości stałych, jak zwykle jest to wykonywane w C i C++.</span><span class="sxs-lookup"><span data-stu-id="a8b86-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="a8b86-108">Stałe w języku C# są najlepiej zdefiniowane jako statyczne elementy członkowskie klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="a8b86-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="a8b86-109">Jeśli masz kilka takich stałych, rozważ utworzenie oddzielnych "stałych" klasy, aby je przechowywać.</span><span class="sxs-lookup"><span data-stu-id="a8b86-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="a8b86-110">Symbole mogą służyć do określania warunków kompilacji.</span><span class="sxs-lookup"><span data-stu-id="a8b86-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="a8b86-111">Możesz sprawdzić, czy symbol ma [#if](./preprocessor-if.md) lub [#elif](./preprocessor-elif.md).</span><span class="sxs-lookup"><span data-stu-id="a8b86-111">You can test for the symbol with either [#if](./preprocessor-if.md) or [#elif](./preprocessor-elif.md).</span></span> <span data-ttu-id="a8b86-112">Można również użyć <xref:System.Diagnostics.ConditionalAttribute> do wykonania kompilacji warunkowej.</span><span class="sxs-lookup"><span data-stu-id="a8b86-112">You can also use the <xref:System.Diagnostics.ConditionalAttribute> to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="a8b86-113">Można zdefiniować symbol, ale nie można przypisać wartości do symbolu.</span><span class="sxs-lookup"><span data-stu-id="a8b86-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="a8b86-114">`#define`Dyrektywa musi znajdować się w pliku przed użyciem dowolnych instrukcji, które nie są również dyrektywami preprocesora.</span><span class="sxs-lookup"><span data-stu-id="a8b86-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="a8b86-115">Można również zdefiniować symbol z opcją [-define](../compiler-options/define-compiler-option.md) kompilatora.</span><span class="sxs-lookup"><span data-stu-id="a8b86-115">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="a8b86-116">Możesz oddefiniować symbol z [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="a8b86-116">You can undefine a symbol with [#undef](./preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="a8b86-117">Symbol zdefiniowany za pomocą `-define` lub with nie `#define` powoduje konfliktu ze zmienną o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="a8b86-117">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="a8b86-118">Oznacza to, że nazwa zmiennej nie powinna być przenoszona do dyrektywy preprocesora i symbol może być oceniany tylko przez dyrektywę preprocesora.</span><span class="sxs-lookup"><span data-stu-id="a8b86-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="a8b86-119">Zakres symbolu, który został utworzony przy użyciu, `#define` to plik, w którym został zdefiniowany symbol.</span><span class="sxs-lookup"><span data-stu-id="a8b86-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="a8b86-120">Jak pokazano na poniższym przykładzie, należy umieścić `#define` dyrektywy w górnej części pliku.</span><span class="sxs-lookup"><span data-stu-id="a8b86-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
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
  
 <span data-ttu-id="a8b86-121">Aby zapoznać się z przykładem, jak wydefiniować symbol, zobacz [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="a8b86-121">For an example of how to undefine a symbol, see [#undef](./preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b86-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a8b86-122">See also</span></span>

- [<span data-ttu-id="a8b86-123">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="a8b86-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a8b86-124">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="a8b86-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a8b86-125">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="a8b86-125">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="a8b86-126">const</span><span class="sxs-lookup"><span data-stu-id="a8b86-126">const</span></span>](../keywords/const.md)
- [<span data-ttu-id="a8b86-127">Instrukcje: Kompilowanie warunkowe ze śledzeniem i debugowaniem</span><span class="sxs-lookup"><span data-stu-id="a8b86-127">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [<span data-ttu-id="a8b86-128">#undef</span><span class="sxs-lookup"><span data-stu-id="a8b86-128">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="a8b86-129">#if</span><span class="sxs-lookup"><span data-stu-id="a8b86-129">#if</span></span>](./preprocessor-if.md)
