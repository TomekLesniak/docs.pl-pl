---
title: <value> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <value> seryjn. Ten tag umożliwia opisanie wartości reprezentowanej przez właściwość.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: d8294b477d7067653c71d1ec2047a85a0bfe6d02
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380777"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="af32a-105">\<value>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="af32a-105">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="af32a-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="af32a-106">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="af32a-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="af32a-107">Parameters</span></span>

- `property-description`

  <span data-ttu-id="af32a-108">Opis właściwości.</span><span class="sxs-lookup"><span data-stu-id="af32a-108">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="af32a-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="af32a-109">Remarks</span></span>

<span data-ttu-id="af32a-110">`<value>`Tag umożliwia opisanie wartości reprezentowanej przez właściwość.</span><span class="sxs-lookup"><span data-stu-id="af32a-110">The `<value>` tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="af32a-111">Po dodaniu właściwości za pośrednictwem Kreatora kodu w środowisku deweloperskim Visual Studio .NET dodaje [\<summary>](./summary.md) tag nowej właściwości.</span><span class="sxs-lookup"><span data-stu-id="af32a-111">When you add a property via code wizard in the Visual Studio .NET development environment, it adds a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="af32a-112">Następnie należy ręcznie dodać tag, `<value>` aby opisać wartość, którą reprezentuje właściwość.</span><span class="sxs-lookup"><span data-stu-id="af32a-112">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>

<span data-ttu-id="af32a-113">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="af32a-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="af32a-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="af32a-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="af32a-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="af32a-115">See also</span></span>

- [<span data-ttu-id="af32a-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="af32a-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="af32a-117">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="af32a-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
