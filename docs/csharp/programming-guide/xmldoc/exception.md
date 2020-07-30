---
title: <exception>— Przewodnik programowania w języku C#
description: Dowiedz się więcej o <exception> tagu XML. Ten tag pozwala określić, które wyjątki mogą być zgłaszane i mogą być stosowane do metod, właściwości, zdarzeń i indeksatorów.
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 22a28f3fe6de5a0db9aea0f1fd7963d4e6fcee05
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381739"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="46043-104">\<exception>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="46043-104">\<exception> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="46043-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="46043-105">Syntax</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a><span data-ttu-id="46043-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="46043-106">Parameters</span></span>

- <span data-ttu-id="46043-107">cref = " `member` "</span><span class="sxs-lookup"><span data-stu-id="46043-107">cref = " `member`"</span></span>

  <span data-ttu-id="46043-108">Odwołanie do wyjątku, które jest dostępne w bieżącym środowisku kompilacji.</span><span class="sxs-lookup"><span data-stu-id="46043-108">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="46043-109">Kompilator sprawdza, czy dany wyjątek istnieje i tłumaczy `member` na nazwę elementu kanonicznego w wyjściowym kodzie XML.</span><span class="sxs-lookup"><span data-stu-id="46043-109">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="46043-110">`member`musi znajdować się w podwójnym cudzysłowie ("").</span><span class="sxs-lookup"><span data-stu-id="46043-110">`member` must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="46043-111">Aby uzyskać więcej informacji na temat sposobu formatowania `member` w celu odwoływania się do typu ogólnego, zobacz [przetwarzanie pliku XML](processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="46043-111">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>

- `description`

  <span data-ttu-id="46043-112">Opis wyjątku.</span><span class="sxs-lookup"><span data-stu-id="46043-112">A description of the exception.</span></span>

## <a name="remarks"></a><span data-ttu-id="46043-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="46043-113">Remarks</span></span>

<span data-ttu-id="46043-114">`<exception>`Tag pozwala określić, które wyjątki mogą być zgłaszane.</span><span class="sxs-lookup"><span data-stu-id="46043-114">The `<exception>` tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="46043-115">Ten tag można zastosować do definicji metod, właściwości, zdarzeń i indeksatorów.</span><span class="sxs-lookup"><span data-stu-id="46043-115">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>

<span data-ttu-id="46043-116">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="46043-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="46043-117">Aby uzyskać więcej informacji na temat obsługi wyjątków, zobacz [wyjątki i obsługa wyjątków](../exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="46043-117">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="46043-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="46043-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a><span data-ttu-id="46043-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="46043-119">See also</span></span>

- [<span data-ttu-id="46043-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="46043-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="46043-121">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="46043-121">Recommended tags for documentation comments</span></span>](recommended-tags-for-documentation-comments.md)
