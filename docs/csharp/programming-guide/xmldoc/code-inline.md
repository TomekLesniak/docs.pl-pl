---
title: <c>— Przewodnik programowania w języku C#
description: Dowiedz się więcej o <c> tagu XML. Ten tag oznacza tekst jednowierszowy w opisie jako kod, podczas gdy <code>indicates multiple lines.
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: 78e59e1df4b096782e0a97b6d12c21c843a1cb21
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382025"
---
# <a name="c-c-programming-guide"></a>\<c>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<c>text</c>
```

## <a name="parameters"></a>Parametry

- `text`

  Tekst, który ma być wskazywany jako kod.

## <a name="remarks"></a>Uwagi

`<c>`Tag umożliwia wskazanie, że tekst w opisie powinien być oznaczony jako kod. Użyj [\<code>](./code.md) , aby wskazać wiele wierszy jako kod.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
