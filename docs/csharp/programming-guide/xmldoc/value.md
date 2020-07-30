---
title: <value> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <value> seryjn. Ten tag umożliwia opisanie wartości reprezentowanej przez właściwość.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: d8294b477d7067653c71d1ec2047a85a0bfe6d02
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380777"
---
# <a name="value-c-programming-guide"></a>\<value>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<value>property-description</value>
```

## <a name="parameters"></a>Parametry

- `property-description`

  Opis właściwości.

## <a name="remarks"></a>Uwagi

`<value>`Tag umożliwia opisanie wartości reprezentowanej przez właściwość. Po dodaniu właściwości za pośrednictwem Kreatora kodu w środowisku deweloperskim Visual Studio .NET dodaje [\<summary>](./summary.md) tag nowej właściwości. Następnie należy ręcznie dodać tag, `<value>` aby opisać wartość, którą reprezentuje właściwość.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
