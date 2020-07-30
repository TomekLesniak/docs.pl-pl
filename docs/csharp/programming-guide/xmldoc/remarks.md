---
title: <remarks> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <remarks> seryjn. Ten tag służy do dodawania informacji o typie, uzupełnianiu informacji określonych za pomocą <summary>.
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: d38905d100e24158e7a1412f6be9f01a7ced2382
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381505"
---
# <a name="remarks-c-programming-guide"></a>\<remarks>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a>Parametry

- `Description`

  Opis elementu członkowskiego.

## <a name="remarks"></a>Uwagi

`<remarks>`Tag służy do dodawania informacji o typie, uzupełniając informacje określone za pomocą [\<summary>](./summary.md) . Te informacje są wyświetlane w oknie Przeglądarka obiektów.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
