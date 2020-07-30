---
title: <remarks> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <remarks> seryjn. Ten tag służy do dodawania informacji o typie, uzupełnianiu informacji określonych za pomocą <summary>.
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: d38905d100e24158e7a1412f6be9f01a7ced2382
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381505"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="80f77-106">\<remarks>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="80f77-106">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="80f77-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="80f77-107">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="80f77-108">Parametry</span><span class="sxs-lookup"><span data-stu-id="80f77-108">Parameters</span></span>

- `Description`

  <span data-ttu-id="80f77-109">Opis elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="80f77-109">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="80f77-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="80f77-110">Remarks</span></span>

<span data-ttu-id="80f77-111">`<remarks>`Tag służy do dodawania informacji o typie, uzupełniając informacje określone za pomocą [\<summary>](./summary.md) .</span><span class="sxs-lookup"><span data-stu-id="80f77-111">The `<remarks>` tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="80f77-112">Te informacje są wyświetlane w oknie Przeglądarka obiektów.</span><span class="sxs-lookup"><span data-stu-id="80f77-112">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="80f77-113">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="80f77-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="80f77-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="80f77-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="80f77-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="80f77-115">See also</span></span>

- [<span data-ttu-id="80f77-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="80f77-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="80f77-117">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="80f77-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
