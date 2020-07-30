---
title: <see>— Przewodnik programowania w języku C#
description: Dowiedz się więcej o <see> tagu XML. Ten tag umożliwia określenie linku w tekście, na przykład przy użyciu atrybutu cref.
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 1cc4982d1ebe9d6896404218a6d200b10cc6503f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381934"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="b4802-104">\<see>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="b4802-104">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="b4802-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b4802-105">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="b4802-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="b4802-106">Parameters</span></span>

- <span data-ttu-id="b4802-107">cref = " `member` "</span><span class="sxs-lookup"><span data-stu-id="b4802-107">cref = "`member`"</span></span>

  <span data-ttu-id="b4802-108">Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywołania z bieżącego środowiska kompilacji.</span><span class="sxs-lookup"><span data-stu-id="b4802-108">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="b4802-109">Kompilator sprawdza, czy dany element kodu istnieje i przekazuje `member` do nazwy elementu w wyjściowym kodzie XML.</span><span class="sxs-lookup"><span data-stu-id="b4802-109">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="b4802-110">Umieść *składową* w podwójnym cudzysłowie ("").</span><span class="sxs-lookup"><span data-stu-id="b4802-110">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="b4802-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b4802-111">Remarks</span></span>

<span data-ttu-id="b4802-112">`<see>`Tag pozwala określić łącze z poziomu tekstu.</span><span class="sxs-lookup"><span data-stu-id="b4802-112">The `<see>` tag lets you specify a link from within text.</span></span> <span data-ttu-id="b4802-113">Użyj [\<seealso>](./seealso.md) , aby wskazać, że tekst powinien być umieszczony w sekcji Zobacz też.</span><span class="sxs-lookup"><span data-stu-id="b4802-113">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="b4802-114">Użyj [atrybutu cref](./cref-attribute.md) , aby utworzyć wewnętrzne hiperłącza do stron dokumentacji dla elementów kodu.</span><span class="sxs-lookup"><span data-stu-id="b4802-114">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span> <span data-ttu-id="b4802-115">Ponadto ``href`` jest prawidłowym atrybutem, który będzie działać jako hiperłącze.</span><span class="sxs-lookup"><span data-stu-id="b4802-115">Also, ``href`` is a valid Attribute that will function as a hyperlink.</span></span>

<span data-ttu-id="b4802-116">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="b4802-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="b4802-117">W poniższym przykładzie pokazano `<see>` tag w sekcji podsumowania.</span><span class="sxs-lookup"><span data-stu-id="b4802-117">The following example shows a `<see>` tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="b4802-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b4802-118">See also</span></span>

- [<span data-ttu-id="b4802-119">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="b4802-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b4802-120">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="b4802-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
