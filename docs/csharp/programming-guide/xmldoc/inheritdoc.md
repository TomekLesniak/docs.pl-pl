---
title: <inheritdoc> — Przewodnik programowania w języku C#
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 8c416275254892efdb9f15cd2ae0af5634c82357
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184095"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="f21b2-102">\<inheritdoc> (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="f21b2-102">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="f21b2-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="f21b2-103">Syntax</span></span>  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a><span data-ttu-id="f21b2-104">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="f21b2-104">InheritDoc</span></span>

<span data-ttu-id="f21b2-105">Dziedzicz Komentarze XML z klas bazowych, interfejsów i podobnych metod.</span><span class="sxs-lookup"><span data-stu-id="f21b2-105">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="f21b2-106">Eliminuje to niechciane kopiowanie i wklejanie zduplikowanych komentarzy XML i automatycznie synchronizuje komentarze XML.</span><span class="sxs-lookup"><span data-stu-id="f21b2-106">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f21b2-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f21b2-107">Remarks</span></span>  

<span data-ttu-id="f21b2-108">Dodaj komentarze XML do klas bazowych lub interfejsów i pozwól InheritDoc skopiować komentarze do implementacji klas.</span><span class="sxs-lookup"><span data-stu-id="f21b2-108">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="f21b2-109">Dodaj komentarze XML do metod synchronicznych i pozwól InheritDoc skopiować komentarze do Twoich asynchronicznych wersji tych samych metod.</span><span class="sxs-lookup"><span data-stu-id="f21b2-109">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="f21b2-110">Jeśli chcesz skopiować komentarze z określonego elementu członkowskiego, możesz użyć `cref` atrybutu, aby określić element członkowski.</span><span class="sxs-lookup"><span data-stu-id="f21b2-110">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="f21b2-111">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f21b2-111">Examples</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="f21b2-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f21b2-112">See also</span></span>

- [<span data-ttu-id="f21b2-113">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="f21b2-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f21b2-114">Zalecane Tagi dla komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="f21b2-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
