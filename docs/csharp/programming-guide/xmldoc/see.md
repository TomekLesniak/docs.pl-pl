---
title: <see>— Przewodnik programowania w języku C#
description: Dowiedz się więcej o <see> tagu XML. Ten tag umożliwia określenie linku w tekście, na przykład przy użyciu atrybutu cref.
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 1cc4982d1ebe9d6896404218a6d200b10cc6503f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381934"
---
# <a name="see-c-programming-guide"></a>\<see>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<see cref="member"/>
```

## <a name="parameters"></a>Parametry

- cref = " `member` "

  Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywołania z bieżącego środowiska kompilacji. Kompilator sprawdza, czy dany element kodu istnieje i przekazuje `member` do nazwy elementu w wyjściowym kodzie XML. Umieść *składową* w podwójnym cudzysłowie ("").

## <a name="remarks"></a>Uwagi

`<see>`Tag pozwala określić łącze z poziomu tekstu. Użyj [\<seealso>](./seealso.md) , aby wskazać, że tekst powinien być umieszczony w sekcji Zobacz też. Użyj [atrybutu cref](./cref-attribute.md) , aby utworzyć wewnętrzne hiperłącza do stron dokumentacji dla elementów kodu. Ponadto ``href`` jest prawidłowym atrybutem, który będzie działać jako hiperłącze.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

W poniższym przykładzie pokazano `<see>` tag w sekcji podsumowania.

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
