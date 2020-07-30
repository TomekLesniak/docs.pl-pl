---
title: <paramref>— Przewodnik programowania w języku C#
description: Dowiedz się więcej o <paramref> tagu XML. Ten tag umożliwia wskazanie, że słowo w kodzie jest parametrem.
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 133f43abfaf349806404d6d37fb472e3145c51b7
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381843"
---
# <a name="paramref-c-programming-guide"></a>\<paramref>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<paramref name="name"/>
```

## <a name="parameters"></a>Parametry

- `name`

  Nazwa parametru, do którego się odwołuje. Ujmij nazwę w znaki podwójnego cudzysłowu ("").

## <a name="remarks"></a>Uwagi

`<paramref>`Tag umożliwia wskazanie, że słowo w komentarzach do kodu, na przykład w `<summary>` `<remarks>` bloku lub odwołuje się do parametru. Plik XML można przetworzyć, aby sformatować ten wyraz w sposób niezależny, na przykład za pomocą czcionki pogrubionej lub kursywy.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
