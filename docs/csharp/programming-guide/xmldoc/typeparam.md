---
title: <typeparam> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <typeparam> seryjn. Ten tag jest używany w komentarzu dla typu ogólnego lub deklaracji metody do opisywania parametru typu.
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 5e5333e384e8c77b500f74ab7c6038146df6e2c0
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380790"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="6f14d-105">\<typeparam>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="6f14d-105">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="6f14d-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="6f14d-106">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="6f14d-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="6f14d-107">Parameters</span></span>

- `name`

  <span data-ttu-id="6f14d-108">Nazwa parametru typu.</span><span class="sxs-lookup"><span data-stu-id="6f14d-108">The name of the type parameter.</span></span> <span data-ttu-id="6f14d-109">Ujmij nazwę w znaki podwójnego cudzysłowu ("").</span><span class="sxs-lookup"><span data-stu-id="6f14d-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="6f14d-110">Opis parametru typu.</span><span class="sxs-lookup"><span data-stu-id="6f14d-110">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f14d-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6f14d-111">Remarks</span></span>

<span data-ttu-id="6f14d-112">`<typeparam>`Tag powinien być używany w komentarzu dla typu ogólnego lub deklaracji metody, aby opisać parametr typu.</span><span class="sxs-lookup"><span data-stu-id="6f14d-112">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="6f14d-113">Dodaj tag dla każdego parametru typu ogólnego typu lub metody.</span><span class="sxs-lookup"><span data-stu-id="6f14d-113">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="6f14d-114">Aby uzyskać więcej informacji, zobacz [Ogólne](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f14d-114">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="6f14d-115">Tekst dla `<typeparam>` tagu będzie wyświetlany w IntelliSense, raport sieci web [przeglądarka obiektówgo](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) komentarza do kodu okna.</span><span class="sxs-lookup"><span data-stu-id="6f14d-115">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="6f14d-116">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="6f14d-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="6f14d-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="6f14d-117">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="6f14d-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6f14d-118">See also</span></span>

- [<span data-ttu-id="6f14d-119">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="6f14d-119">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="6f14d-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="6f14d-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="6f14d-121">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="6f14d-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
