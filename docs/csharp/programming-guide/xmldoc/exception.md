---
title: <exception>— Przewodnik programowania w języku C#
description: Dowiedz się więcej o <exception> tagu XML. Ten tag pozwala określić, które wyjątki mogą być zgłaszane i mogą być stosowane do metod, właściwości, zdarzeń i indeksatorów.
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 22a28f3fe6de5a0db9aea0f1fd7963d4e6fcee05
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381739"
---
# <a name="exception-c-programming-guide"></a>\<exception>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a>Parametry

- cref = " `member` "

  Odwołanie do wyjątku, które jest dostępne w bieżącym środowisku kompilacji. Kompilator sprawdza, czy dany wyjątek istnieje i tłumaczy `member` na nazwę elementu kanonicznego w wyjściowym kodzie XML. `member`musi znajdować się w podwójnym cudzysłowie ("").

  Aby uzyskać więcej informacji na temat sposobu formatowania `member` w celu odwoływania się do typu ogólnego, zobacz [przetwarzanie pliku XML](processing-the-xml-file.md).

- `description`

  Opis wyjątku.

## <a name="remarks"></a>Uwagi

`<exception>`Tag pozwala określić, które wyjątki mogą być zgłaszane. Ten tag można zastosować do definicji metod, właściwości, zdarzeń i indeksatorów.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

Aby uzyskać więcej informacji na temat obsługi wyjątków, zobacz [wyjątki i obsługa wyjątków](../exceptions/index.md).

## <a name="example"></a>Przykład

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](recommended-tags-for-documentation-comments.md)
