---
title: alias zewnętrzny — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 891e56b064f8a327abe28293223a85b9d95e8fd3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301817"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="451f2-102">extern alias (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="451f2-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="451f2-103">Może zajść konieczność odwołująca się do dwóch wersji zestawów, które mają te same nazwy typów w pełni kwalifikowana.</span><span class="sxs-lookup"><span data-stu-id="451f2-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="451f2-104">Na przykład może być konieczne użycie co najmniej dwóch wersji zestawu w tej samej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="451f2-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="451f2-105">Korzystając z zewnętrznego aliasu zestawu, przestrzenie nazw z każdego zestawu mogą być opakowane w przestrzenie nazw poziomu głównego o nazwie alias, co umożliwia ich użycie w tym samym pliku.</span><span class="sxs-lookup"><span data-stu-id="451f2-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="451f2-106">Słowo kluczowe [extern](./extern.md) jest również używane jako modyfikator metody, deklarując metodę zapisaną w kodzie niezarządzanym.</span><span class="sxs-lookup"><span data-stu-id="451f2-106">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="451f2-107">Aby odwoływać się do dwóch zestawów z tymi samymi w pełni kwalifikowanymi nazwami typu, alias musi być określony w wierszu polecenia w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="451f2-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="451f2-108">Spowoduje to utworzenie aliasów zewnętrznych `GridV1` i `GridV2` .</span><span class="sxs-lookup"><span data-stu-id="451f2-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="451f2-109">Aby użyć tych aliasów z poziomu programu, odwołując się do nich za pomocą `extern` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="451f2-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="451f2-110">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="451f2-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="451f2-111">Każda deklaracja aliasu zewnętrznego wprowadza dodatkową przestrzeń nazw na poziomie głównym, która jest równoległa (ale nie znajduje się w obrębie) globalnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="451f2-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="451f2-112">Z tego względu typy z każdego zestawu mogą być określane bez niejednoznaczności przy użyciu ich w pełni kwalifikowanej nazwy, w której znajduje się odpowiedni alias przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="451f2-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="451f2-113">W poprzednim przykładzie `GridV1::Grid` jest to formant siatki z, który będzie `grid.dll` `GridV2::Grid` formantem siatki z `grid20.dll` .</span><span class="sxs-lookup"><span data-stu-id="451f2-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="using-visual-studio"></a><span data-ttu-id="451f2-114">Korzystanie z programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="451f2-114">Using Visual Studio</span></span>

<span data-ttu-id="451f2-115">Jeśli używasz programu Visual Studio, aliasy mogą być udostępniane w podobny sposób.</span><span class="sxs-lookup"><span data-stu-id="451f2-115">If you are using Visual Studio, aliases can be provided in similar way.</span></span>

<span data-ttu-id="451f2-116">Dodaj odwołanie do *grid.dll* i *grid20.dll* do projektu w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="451f2-116">Add reference of *grid.dll* and *grid20.dll* to your project in Visual Studio.</span></span> <span data-ttu-id="451f2-117">Otwórz kartę właściwości i Zmień aliasy z globalny na GridV1 i GridV2.</span><span class="sxs-lookup"><span data-stu-id="451f2-117">Open a property tab and change the Aliases from global to GridV1 and GridV2 respectively.</span></span>

<span data-ttu-id="451f2-118">Użyj tych aliasów w taki sam sposób, jak powyżej</span><span class="sxs-lookup"><span data-stu-id="451f2-118">Use these aliases the same way above</span></span>

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

<span data-ttu-id="451f2-119">Teraz można utworzyć alias dla przestrzeni nazw lub typu za *pomocą dyrektywy aliasu*.</span><span class="sxs-lookup"><span data-stu-id="451f2-119">Now you can create alias for a namespace or a type by *using alias directive*.</span></span> <span data-ttu-id="451f2-120">Aby uzyskać więcej informacji, zobacz [Używanie dyrektywy](using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="451f2-120">For more information, see [using directive](using-directive.md).</span></span>

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a><span data-ttu-id="451f2-121">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="451f2-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="451f2-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="451f2-122">See also</span></span>

- [<span data-ttu-id="451f2-123">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="451f2-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="451f2-124">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="451f2-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="451f2-125">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="451f2-125">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="451f2-126">:: Operator</span><span class="sxs-lookup"><span data-stu-id="451f2-126">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="451f2-127">-Reference (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="451f2-127">-reference (C# Compiler Options)</span></span>](../compiler-options/reference-compiler-option.md)
