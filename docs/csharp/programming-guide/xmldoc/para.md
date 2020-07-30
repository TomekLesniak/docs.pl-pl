---
title: <para> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <para> seryjn. Ten tag umożliwia dodanie struktury do tekstu w innym tagu, na przykład <summary>, <remarks>lub <returns>.
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: 146078bcb556b4085724ddcdac561ea868ab0481
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381856"
---
# <a name="para-c-programming-guide"></a>\<para>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<para>content</para>
```

## <a name="parameters"></a>Parametry

- `content`

  Tekst akapitu.

## <a name="remarks"></a>Uwagi

`<para>`Tag jest używany wewnątrz tagu, takiego jak [\<summary>](./summary.md) , [\<remarks>](./remarks.md) , lub [\<returns>](./returns.md) , i umożliwia dodanie struktury do tekstu.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

Zobacz [\<summary>](./summary.md) , aby zobaczyć przykład użycia `<para>` .

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
