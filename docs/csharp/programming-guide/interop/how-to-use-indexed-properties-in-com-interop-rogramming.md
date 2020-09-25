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
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="8af3c-103">Jak używać właściwości indeksowanych w programowaniu międzyoperacyjnym modelu COM (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="8af3c-103">How to use indexed properties in COM interop programming (C# Programming Guide)</span></span>

<span data-ttu-id="8af3c-104">*Właściwości indeksowane* ulepszają sposób, w jaki właściwości com, które mają parametry są używane w programowaniu języka C#.</span><span class="sxs-lookup"><span data-stu-id="8af3c-104">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="8af3c-105">Właściwości indeksowane współpracują z innymi funkcjami w języku Visual C#, takimi jak [argumenty nazwane i opcjonalne](../classes-and-structs/named-and-optional-arguments.md), nowy typ ([dynamiczny](../../language-reference/builtin-types/reference-types.md)) i [Informacje o typie osadzonym](../../../standard/assembly/embed-types-visual-studio.md), aby usprawnić programowanie Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="8af3c-105">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../language-reference/builtin-types/reference-types.md)), and [embedded type information](../../../standard/assembly/embed-types-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="8af3c-106">We wcześniejszych wersjach języka C# metody są dostępne jako właściwości tylko wtedy, gdy `get` Metoda nie ma parametrów, a `set` Metoda ma jeden i tylko jeden parametr value.</span><span class="sxs-lookup"><span data-stu-id="8af3c-106">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="8af3c-107">Jednak nie wszystkie właściwości COM spełniają te ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="8af3c-107">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="8af3c-108">Na przykład właściwość programu Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> ma `get` metodę dostępu, która wymaga parametru dla nazwy zakresu.</span><span class="sxs-lookup"><span data-stu-id="8af3c-108">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="8af3c-109">W przeszłości, ponieważ nie można uzyskać dostępu do `Range` właściwości bezpośrednio, należy użyć `get_Range` metody zamiast tego, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="8af3c-109">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="8af3c-110">Właściwości indeksowane umożliwiają napisanie następujących danych:</span><span class="sxs-lookup"><span data-stu-id="8af3c-110">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> <span data-ttu-id="8af3c-111">W poprzednim przykładzie jest również stosowana funkcja [argumentów opcjonalnych](../classes-and-structs/named-and-optional-arguments.md) , która pozwala pominąć `Type.Missing` .</span><span class="sxs-lookup"><span data-stu-id="8af3c-111">The previous example also uses the [optional arguments](../classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="8af3c-112">Podobnie, aby ustawić wartość `Value` właściwości <xref:Microsoft.Office.Interop.Excel.Range> obiektu w języku C# 3,0 i wcześniejszych, wymagane są dwa argumenty.</span><span class="sxs-lookup"><span data-stu-id="8af3c-112">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="8af3c-113">Jeden dostarcza argument dla opcjonalnego parametru, który określa typ wartości zakresu.</span><span class="sxs-lookup"><span data-stu-id="8af3c-113">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="8af3c-114">Pozostałe dostarczają wartość `Value` właściwości.</span><span class="sxs-lookup"><span data-stu-id="8af3c-114">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="8af3c-115">Poniższe przykłady ilustrują te techniki.</span><span class="sxs-lookup"><span data-stu-id="8af3c-115">The following examples illustrate these techniques.</span></span> <span data-ttu-id="8af3c-116">Obie wartości mają ustawioną wartość komórki a1 `Name` .</span><span class="sxs-lookup"><span data-stu-id="8af3c-116">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="8af3c-117">Właściwości indeksowane umożliwiają zapisanie w zamian poniższego kodu.</span><span class="sxs-lookup"><span data-stu-id="8af3c-117">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="8af3c-118">Nie można tworzyć własnych właściwości indeksowanych.</span><span class="sxs-lookup"><span data-stu-id="8af3c-118">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="8af3c-119">Funkcja obsługuje tylko użycie istniejących właściwości indeksowanych.</span><span class="sxs-lookup"><span data-stu-id="8af3c-119">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8af3c-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="8af3c-120">Example</span></span>  

 <span data-ttu-id="8af3c-121">Poniższy kod przedstawia kompletny przykład.</span><span class="sxs-lookup"><span data-stu-id="8af3c-121">The following code shows a complete example.</span></span> <span data-ttu-id="8af3c-122">Aby uzyskać więcej informacji na temat sposobu konfigurowania projektu, który uzyskuje dostęp do interfejsu API pakietu Office, zobacz [jak uzyskać dostęp do obiektów międzyoperacyjności pakietu Office za pomocą funkcji języka C#](./how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="8af3c-122">For more information about how to set up a project that accesses the Office API, see [How to access Office interop objects by using C# features](./how-to-access-office-onterop-objects.md).</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="8af3c-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8af3c-123">See also</span></span>

- [<span data-ttu-id="8af3c-124">Argumenty nazwane i opcjonalne</span><span class="sxs-lookup"><span data-stu-id="8af3c-124">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="8af3c-125">dynamiczna</span><span class="sxs-lookup"><span data-stu-id="8af3c-125">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="8af3c-126">Używanie typu dynamicznego</span><span class="sxs-lookup"><span data-stu-id="8af3c-126">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="8af3c-127">Porada: użycie argumentów nazwanych i opcjonalnych w programowaniu pakietu Office</span><span class="sxs-lookup"><span data-stu-id="8af3c-127">How to use named and optional arguments in Office programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="8af3c-128">Uzyskiwanie dostępu do obiektów międzyoperacyjności pakietu Office za pomocą funkcji języka C#</span><span class="sxs-lookup"><span data-stu-id="8af3c-128">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="8af3c-129">Przewodnik: Programowanie Office</span><span class="sxs-lookup"><span data-stu-id="8af3c-129">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
