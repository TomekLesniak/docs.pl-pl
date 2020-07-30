---
title: <typeparamref>— Przewodnik programowania w języku C#
description: Dowiedz się więcej o <typeparamref> tagu XML. Ten tag umożliwia użytkownikom pliku dokumentacji formatowanie wyrazu w niektórych odrębnych sposóbch, na przykład kursywą.
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: a39e896f1242452c7bcc94faa1e7ef3086ae2149
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380725"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="ecaa0-104">\<typeparamref>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="ecaa0-104">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ecaa0-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ecaa0-105">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="ecaa0-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="ecaa0-106">Parameters</span></span>

- `name`

  <span data-ttu-id="ecaa0-107">Nazwa parametru typu.</span><span class="sxs-lookup"><span data-stu-id="ecaa0-107">The name of the type parameter.</span></span> <span data-ttu-id="ecaa0-108">Ujmij nazwę w znaki podwójnego cudzysłowu ("").</span><span class="sxs-lookup"><span data-stu-id="ecaa0-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="ecaa0-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ecaa0-109">Remarks</span></span>

<span data-ttu-id="ecaa0-110">Aby uzyskać więcej informacji na temat parametrów typu w typach ogólnych i metodach, zobacz [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="ecaa0-110">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="ecaa0-111">Ten tag umożliwia użytkownikom pliku dokumentacji formatowanie wyrazu w niektórych odrębnych przypadkach, na przykład kursywą.</span><span class="sxs-lookup"><span data-stu-id="ecaa0-111">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="ecaa0-112">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="ecaa0-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="ecaa0-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="ecaa0-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="ecaa0-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ecaa0-114">See also</span></span>

- [<span data-ttu-id="ecaa0-115">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="ecaa0-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ecaa0-116">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="ecaa0-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
