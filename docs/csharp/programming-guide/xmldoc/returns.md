---
title: <returns> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <returns> seryjn. Ten tag jest używany w komentarzu dla deklaracji metody, aby opisać wartość zwracaną.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381401"
---
# <a name="returns-c-programming-guide"></a>\<returns>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<returns>description</returns>
```

## <a name="parameters"></a>Parametry

- `description`

  Opis wartości zwracanej.

## <a name="remarks"></a>Uwagi

`<returns>`Tag powinien być używany w komentarzu dla deklaracji metody, aby opisać wartość zwracaną.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
