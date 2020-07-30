---
title: <param> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <param> seryjn. Ten tag jest używany w komentarzu dla deklaracji metody do opisywania jednego z parametrów dla metody.
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: a9e3b2e86528afcbe1330788e248f0143efb5c1b
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381557"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="7f4b7-105">\<param>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="7f4b7-105">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="7f4b7-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="7f4b7-106">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="7f4b7-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="7f4b7-107">Parameters</span></span>

- `name`

  <span data-ttu-id="7f4b7-108">Nazwa parametru metody.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-108">The name of a method parameter.</span></span> <span data-ttu-id="7f4b7-109">Ujmij nazwę w znaki podwójnego cudzysłowu ("").</span><span class="sxs-lookup"><span data-stu-id="7f4b7-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="7f4b7-110">Opis parametru.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-110">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f4b7-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7f4b7-111">Remarks</span></span>

<span data-ttu-id="7f4b7-112">`<param>`Tag powinien być używany w komentarzu dla deklaracji metody, aby opisać jeden z parametrów dla metody.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-112">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="7f4b7-113">Aby udokumentować wiele parametrów, Użyj wielu `<param>` tagów.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-113">To document multiple parameters, use multiple `<param>` tags.</span></span>

<span data-ttu-id="7f4b7-114">Tekst `<param>` znacznika jest wyświetlany w obszarze IntelliSense, Przeglądarka obiektów i raport sieci Web komentarza do kodu.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-114">The text for the `<param>` tag is displayed in IntelliSense, the Object Browser, and the Code Comment Web Report.</span></span>

<span data-ttu-id="7f4b7-115">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-115">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="7f4b7-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="7f4b7-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="7f4b7-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7f4b7-117">See also</span></span>

- [<span data-ttu-id="7f4b7-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="7f4b7-118">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="7f4b7-119">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="7f4b7-119">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
