---
title: <returns> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <returns> seryjn. Ten tag jest używany w komentarzu dla deklaracji metody, aby opisać wartość zwracaną.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381401"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="39db6-105">\<returns>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="39db6-105">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="39db6-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="39db6-106">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="39db6-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="39db6-107">Parameters</span></span>

- `description`

  <span data-ttu-id="39db6-108">Opis wartości zwracanej.</span><span class="sxs-lookup"><span data-stu-id="39db6-108">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="39db6-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="39db6-109">Remarks</span></span>

<span data-ttu-id="39db6-110">`<returns>`Tag powinien być używany w komentarzu dla deklaracji metody, aby opisać wartość zwracaną.</span><span class="sxs-lookup"><span data-stu-id="39db6-110">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="39db6-111">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="39db6-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="39db6-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="39db6-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="39db6-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="39db6-113">See also</span></span>

- [<span data-ttu-id="39db6-114">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="39db6-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="39db6-115">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="39db6-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
