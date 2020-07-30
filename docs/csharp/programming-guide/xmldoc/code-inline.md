---
title: <c>— Przewodnik programowania w języku C#
description: Dowiedz się więcej o <c> tagu XML. Ten tag oznacza tekst jednowierszowy w opisie jako kod, podczas gdy <code>indicates multiple lines.
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: 78e59e1df4b096782e0a97b6d12c21c843a1cb21
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382025"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="07acf-104">\<c>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="07acf-104">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="07acf-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="07acf-105">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="07acf-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="07acf-106">Parameters</span></span>

- `text`

  <span data-ttu-id="07acf-107">Tekst, który ma być wskazywany jako kod.</span><span class="sxs-lookup"><span data-stu-id="07acf-107">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="07acf-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="07acf-108">Remarks</span></span>

<span data-ttu-id="07acf-109">`<c>`Tag umożliwia wskazanie, że tekst w opisie powinien być oznaczony jako kod.</span><span class="sxs-lookup"><span data-stu-id="07acf-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="07acf-110">Użyj [\<code>](./code.md) , aby wskazać wiele wierszy jako kod.</span><span class="sxs-lookup"><span data-stu-id="07acf-110">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="07acf-111">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="07acf-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="07acf-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="07acf-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="07acf-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="07acf-113">See also</span></span>

- [<span data-ttu-id="07acf-114">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="07acf-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="07acf-115">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="07acf-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
