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
# <a name="inheritdoc-c-programming-guide"></a>\<inheritdoc> (Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a>InheritDoc

Dziedzicz Komentarze XML z klas bazowych, interfejsów i podobnych metod. Eliminuje to niechciane kopiowanie i wklejanie zduplikowanych komentarzy XML i automatycznie synchronizuje komentarze XML.
  
## <a name="remarks"></a>Uwagi  

Dodaj komentarze XML do klas bazowych lub interfejsów i pozwól InheritDoc skopiować komentarze do implementacji klas.

Dodaj komentarze XML do metod synchronicznych i pozwól InheritDoc skopiować komentarze do Twoich asynchronicznych wersji tych samych metod.  

Jeśli chcesz skopiować komentarze z określonego elementu członkowskiego, możesz użyć `cref` atrybutu, aby określić element członkowski.
  
## <a name="examples"></a>Przykłady

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane Tagi dla komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
