---
title: <example> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <example> seryjn. Ten tag pozwala określić przykład użycia metody lub innego elementu członkowskiego biblioteki.
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: dd529e8f2a54cf9086d0d8c555dd1adb70b99126
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381531"
---
# <a name="example-c-programming-guide"></a>\<example>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<example>description</example>
```

## <a name="parameters"></a>Parametry

- `description`

  Opis przykładu kodu.

## <a name="remarks"></a>Uwagi

`<example>`Tag pozwala określić przykład użycia metody lub innego elementu członkowskiego biblioteki. Zwykle obejmuje to użycie [\<code>](./code.md) znacznika.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
