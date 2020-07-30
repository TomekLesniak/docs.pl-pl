---
title: <seealso> — Przewodnik programowania w języku C#
description: Dowiedz się, jak używać kodu XML <seealso> seryjn. Ten tag pozwala określić tekst, który może być wyświetlany w sekcji "Zobacz też".
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: e8618ef352a4fa7f0fd4c88733c6568b0e12e376
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380647"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="c9bdc-105">\<seealso>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="c9bdc-105">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="c9bdc-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="c9bdc-106">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="c9bdc-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="c9bdc-107">Parameters</span></span>

- <span data-ttu-id="c9bdc-108">cref = " `member` "</span><span class="sxs-lookup"><span data-stu-id="c9bdc-108">cref = " `member`"</span></span>

  <span data-ttu-id="c9bdc-109">Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywołania z bieżącego środowiska kompilacji.</span><span class="sxs-lookup"><span data-stu-id="c9bdc-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="c9bdc-110">Kompilator sprawdza, czy dany element kodu istnieje i przekazuje `member` do nazwy elementu w wyjściowym kodzie XML.`member`</span><span class="sxs-lookup"><span data-stu-id="c9bdc-110">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="c9bdc-111">musi znajdować się w podwójnym cudzysłowie ("").</span><span class="sxs-lookup"><span data-stu-id="c9bdc-111">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="c9bdc-112">Aby uzyskać informacje na temat sposobu tworzenia odwołania cref do typu ogólnego, zobacz [atrybut cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="c9bdc-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="c9bdc-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c9bdc-113">Remarks</span></span>

<span data-ttu-id="c9bdc-114">`<seealso>`Tag pozwala określić tekst, który może być wyświetlany w sekcji Zobacz też.</span><span class="sxs-lookup"><span data-stu-id="c9bdc-114">The `<seealso>` tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="c9bdc-115">Służy [\<see>](./see.md) do określania linku w tekście.</span><span class="sxs-lookup"><span data-stu-id="c9bdc-115">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="c9bdc-116">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="c9bdc-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="c9bdc-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="c9bdc-117">Example</span></span>

<span data-ttu-id="c9bdc-118">Zobacz [\<summary>](./summary.md) , aby zobaczyć przykład użycia \<seealso> .</span><span class="sxs-lookup"><span data-stu-id="c9bdc-118">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9bdc-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c9bdc-119">See also</span></span>

- [<span data-ttu-id="c9bdc-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="c9bdc-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="c9bdc-121">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="c9bdc-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
