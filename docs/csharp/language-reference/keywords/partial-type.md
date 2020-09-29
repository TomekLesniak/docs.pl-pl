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
ms.openlocfilehash: 4e73b34390143a2ac9b839e1da79b7894232c4b4
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2020
ms.locfileid: "91437885"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="50f38-103">Typ częściowy (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="50f38-103">partial type (C# Reference)</span></span>

<span data-ttu-id="50f38-104">Definicje typu częściowego umożliwiają poddzielenie definicji klasy, struktury, interfejsu lub rekordu na wiele plików.</span><span class="sxs-lookup"><span data-stu-id="50f38-104">Partial type definitions allow for the definition of a class, struct, interface, or record to be split into multiple files.</span></span>

<span data-ttu-id="50f38-105">W *file1.cs*:</span><span class="sxs-lookup"><span data-stu-id="50f38-105">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="50f38-106">W *file2.cs* deklaracji:</span><span class="sxs-lookup"><span data-stu-id="50f38-106">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="50f38-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="50f38-107">Remarks</span></span>

<span data-ttu-id="50f38-108">Dzielenie klasy, struktury lub interfejsu za pomocą kilku plików może być przydatne podczas pracy z dużymi projektami lub z automatycznie generowanym kodem, takim jak [Projektant formularzy systemu Windows](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time).</span><span class="sxs-lookup"><span data-stu-id="50f38-108">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time).</span></span> <span data-ttu-id="50f38-109">Typ częściowy może zawierać [metodę częściową](partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="50f38-109">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="50f38-110">Aby uzyskać więcej informacji, zobacz [częściowe klasy i metody](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="50f38-110">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="50f38-111">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="50f38-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="50f38-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="50f38-112">See also</span></span>

- [<span data-ttu-id="50f38-113">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="50f38-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="50f38-114">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="50f38-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="50f38-115">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="50f38-115">Modifiers</span></span>](index.md)
- [<span data-ttu-id="50f38-116">Wprowadzenie do typów ogólnych</span><span class="sxs-lookup"><span data-stu-id="50f38-116">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
