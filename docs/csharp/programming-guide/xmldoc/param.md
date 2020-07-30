---
title: <param> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <param> seryjn. Ten tag jest używany w komentarzu dla deklaracji metody do opisywania jednego z parametrów dla metody.
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: a9e3b2e86528afcbe1330788e248f0143efb5c1b
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381557"
---
# <a name="param-c-programming-guide"></a>\<param>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<param name="name">description</param>
```

## <a name="parameters"></a>Parametry

- `name`

  Nazwa parametru metody. Ujmij nazwę w znaki podwójnego cudzysłowu ("").

- `description`

  Opis parametru.

## <a name="remarks"></a>Uwagi

`<param>`Tag powinien być używany w komentarzu dla deklaracji metody, aby opisać jeden z parametrów dla metody. Aby udokumentować wiele parametrów, Użyj wielu `<param>` tagów.

Tekst `<param>` znacznika jest wyświetlany w obszarze IntelliSense, Przeglądarka obiektów i raport sieci Web komentarza do kodu.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
