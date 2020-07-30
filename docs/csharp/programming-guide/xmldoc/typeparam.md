---
title: <typeparam> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <typeparam> seryjn. Ten tag jest używany w komentarzu dla typu ogólnego lub deklaracji metody do opisywania parametru typu.
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 5e5333e384e8c77b500f74ab7c6038146df6e2c0
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380790"
---
# <a name="typeparam-c-programming-guide"></a>\<typeparam>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a>Parametry

- `name`

  Nazwa parametru typu. Ujmij nazwę w znaki podwójnego cudzysłowu ("").

- `description`

  Opis parametru typu.

## <a name="remarks"></a>Uwagi

`<typeparam>`Tag powinien być używany w komentarzu dla typu ogólnego lub deklaracji metody, aby opisać parametr typu. Dodaj tag dla każdego parametru typu ogólnego typu lub metody.

Aby uzyskać więcej informacji, zobacz [Ogólne](../generics/index.md).

Tekst dla `<typeparam>` tagu będzie wyświetlany w IntelliSense, raport sieci web [przeglądarka obiektówgo](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) komentarza do kodu okna.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../../language-reference/index.md)
- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
