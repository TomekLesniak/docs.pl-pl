---
title: <permission> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <permission> seryjn. Ten tag umożliwia dokumentowanie dostępu do elementu członkowskiego, podczas gdy Klasa PermissionSet pozwala określić dostęp do elementu członkowskiego.
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 38c87505b8b2973875e474ffd296dc02b7fb9de6
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381726"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="ac288-105">\<permission>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="ac288-105">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ac288-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="ac288-106">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="ac288-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="ac288-107">Parameters</span></span>

- <span data-ttu-id="ac288-108">cref = " `member` "</span><span class="sxs-lookup"><span data-stu-id="ac288-108">cref = " `member`"</span></span>

  <span data-ttu-id="ac288-109">Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywołania z bieżącego środowiska kompilacji.</span><span class="sxs-lookup"><span data-stu-id="ac288-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ac288-110">Kompilator sprawdza, czy dany element kodu istnieje i tłumaczy `member` na nazwę elementu kanonicznego w wyjściowym kodzie XML.</span><span class="sxs-lookup"><span data-stu-id="ac288-110">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="ac288-111">*składowa* musi znajdować się w podwójnym cudzysłowie ("").</span><span class="sxs-lookup"><span data-stu-id="ac288-111">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="ac288-112">Aby uzyskać informacje na temat sposobu tworzenia odwołania cref do typu ogólnego, zobacz [atrybut cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="ac288-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

- `description`

  <span data-ttu-id="ac288-113">Opis dostępu do elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="ac288-113">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac288-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ac288-114">Remarks</span></span>

<span data-ttu-id="ac288-115">`<permission>`Tag umożliwia dokumentowanie dostępu do elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="ac288-115">The `<permission>` tag lets you document the access of a member.</span></span> <span data-ttu-id="ac288-116"><xref:System.Security.PermissionSet>Klasa pozwala określić dostęp do elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="ac288-116">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="ac288-117">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="ac288-117">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="ac288-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="ac288-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="ac288-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ac288-119">See also</span></span>

- [<span data-ttu-id="ac288-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="ac288-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ac288-121">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="ac288-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
