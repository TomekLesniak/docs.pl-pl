---
title: <example> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <example> seryjn. Ten tag pozwala określić przykład użycia metody lub innego elementu członkowskiego biblioteki.
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: dd529e8f2a54cf9086d0d8c555dd1adb70b99126
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381531"
---
# <a name="example-c-programming-guide"></a><span data-ttu-id="1d6fb-105">\<example>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="1d6fb-105">\<example> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="1d6fb-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="1d6fb-106">Syntax</span></span>

```xml
<example>description</example>
```

## <a name="parameters"></a><span data-ttu-id="1d6fb-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="1d6fb-107">Parameters</span></span>

- `description`

  <span data-ttu-id="1d6fb-108">Opis przykładu kodu.</span><span class="sxs-lookup"><span data-stu-id="1d6fb-108">A description of the code sample.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d6fb-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1d6fb-109">Remarks</span></span>

<span data-ttu-id="1d6fb-110">`<example>`Tag pozwala określić przykład użycia metody lub innego elementu członkowskiego biblioteki.</span><span class="sxs-lookup"><span data-stu-id="1d6fb-110">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="1d6fb-111">Zwykle obejmuje to użycie [\<code>](./code.md) znacznika.</span><span class="sxs-lookup"><span data-stu-id="1d6fb-111">This commonly involves using the [\<code>](./code.md) tag.</span></span>

<span data-ttu-id="1d6fb-112">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="1d6fb-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="1d6fb-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="1d6fb-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a><span data-ttu-id="1d6fb-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1d6fb-114">See also</span></span>

- [<span data-ttu-id="1d6fb-115">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="1d6fb-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1d6fb-116">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="1d6fb-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
