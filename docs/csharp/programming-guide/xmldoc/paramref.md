---
title: <paramref>— Przewodnik programowania w języku C#
description: Dowiedz się więcej o <paramref> tagu XML. Ten tag umożliwia wskazanie, że słowo w kodzie jest parametrem.
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 133f43abfaf349806404d6d37fb472e3145c51b7
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381843"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="f85a5-104">\<paramref>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="f85a5-104">\<paramref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="f85a5-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f85a5-105">Syntax</span></span>

```xml
<paramref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="f85a5-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="f85a5-106">Parameters</span></span>

- `name`

  <span data-ttu-id="f85a5-107">Nazwa parametru, do którego się odwołuje.</span><span class="sxs-lookup"><span data-stu-id="f85a5-107">The name of the parameter to refer to.</span></span> <span data-ttu-id="f85a5-108">Ujmij nazwę w znaki podwójnego cudzysłowu ("").</span><span class="sxs-lookup"><span data-stu-id="f85a5-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="f85a5-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f85a5-109">Remarks</span></span>

<span data-ttu-id="f85a5-110">`<paramref>`Tag umożliwia wskazanie, że słowo w komentarzach do kodu, na przykład w `<summary>` `<remarks>` bloku lub odwołuje się do parametru.</span><span class="sxs-lookup"><span data-stu-id="f85a5-110">The `<paramref>` tag gives you a way to indicate that a word in the code comments, for example in a `<summary>` or `<remarks>` block refers to a parameter.</span></span> <span data-ttu-id="f85a5-111">Plik XML można przetworzyć, aby sformatować ten wyraz w sposób niezależny, na przykład za pomocą czcionki pogrubionej lub kursywy.</span><span class="sxs-lookup"><span data-stu-id="f85a5-111">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>

<span data-ttu-id="f85a5-112">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="f85a5-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="f85a5-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="f85a5-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a><span data-ttu-id="f85a5-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f85a5-114">See also</span></span>

- [<span data-ttu-id="f85a5-115">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="f85a5-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f85a5-116">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="f85a5-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
