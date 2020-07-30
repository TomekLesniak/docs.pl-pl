---
title: <permission> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <permission> seryjn. Ten tag umożliwia dokumentowanie dostępu do elementu członkowskiego, podczas gdy Klasa PermissionSet pozwala określić dostęp do elementu członkowskiego.
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 38c87505b8b2973875e474ffd296dc02b7fb9de6
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381726"
---
# <a name="permission-c-programming-guide"></a>\<permission>(Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a>Parametry

- cref = " `member` "

  Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywołania z bieżącego środowiska kompilacji. Kompilator sprawdza, czy dany element kodu istnieje i tłumaczy `member` na nazwę elementu kanonicznego w wyjściowym kodzie XML. *składowa* musi znajdować się w podwójnym cudzysłowie ("").

  Aby uzyskać informacje na temat sposobu tworzenia odwołania cref do typu ogólnego, zobacz [atrybut cref](./cref-attribute.md).

- `description`

  Opis dostępu do elementu członkowskiego.

## <a name="remarks"></a>Uwagi

`<permission>`Tag umożliwia dokumentowanie dostępu do elementu członkowskiego. <xref:System.Security.PermissionSet>Klasa pozwala określić dostęp do elementu członkowskiego.

Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
