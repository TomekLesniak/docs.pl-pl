---
description: Typ częściowy — odwołanie w C#
title: Typ częściowy — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 8ae98805eea7231e3a15cb74e636313e796796a2
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89117990"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="ff0e6-103">Typ częściowy (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="ff0e6-103">partial type (C# Reference)</span></span>

<span data-ttu-id="ff0e6-104">Definicje typu częściowego umożliwiają poddzielenie definicji klasy, struktury lub interfejsu na wiele plików.</span><span class="sxs-lookup"><span data-stu-id="ff0e6-104">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="ff0e6-105">W *file1.cs*:</span><span class="sxs-lookup"><span data-stu-id="ff0e6-105">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="ff0e6-106">W *file2.cs* deklaracji:</span><span class="sxs-lookup"><span data-stu-id="ff0e6-106">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="ff0e6-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ff0e6-107">Remarks</span></span>

<span data-ttu-id="ff0e6-108">Dzielenie klasy, struktury lub interfejsu za pomocą kilku plików może być przydatne podczas pracy z dużymi projektami lub z automatycznie generowanym kodem, takim jak [Projektant formularzy systemu Windows](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="ff0e6-108">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="ff0e6-109">Typ częściowy może zawierać [metodę częściową](partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="ff0e6-109">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="ff0e6-110">Aby uzyskać więcej informacji, zobacz [częściowe klasy i metody](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ff0e6-110">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ff0e6-111">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="ff0e6-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ff0e6-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ff0e6-112">See also</span></span>

- [<span data-ttu-id="ff0e6-113">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="ff0e6-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ff0e6-114">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="ff0e6-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ff0e6-115">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="ff0e6-115">Modifiers</span></span>](index.md)
- [<span data-ttu-id="ff0e6-116">Wprowadzenie do typów ogólnych</span><span class="sxs-lookup"><span data-stu-id="ff0e6-116">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
