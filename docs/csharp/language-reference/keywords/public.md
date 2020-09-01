---
description: Public — słowo kluczowe — odwołanie w C#
title: Public — słowo kluczowe — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 26edaf7538d11d082a4b8863228213c3ebc46937
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122345"
---
# <a name="public-c-reference"></a>public (odwołanie w C#)

`public`Słowo kluczowe jest modyfikatorem dostępu dla typów i elementów członkowskich typu. Dostęp publiczny to najwyższy poziom dostępu. Nie ma żadnych ograniczeń dotyczących uzyskiwania dostępu do publicznych członków, jak w tym przykładzie:

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

Aby uzyskać więcej informacji, zobacz [Modyfikatory dostępu](../../programming-guide/classes-and-structs/access-modifiers.md) i [poziomy dostępności](accessibility-levels.md) .

## <a name="example"></a>Przykład

W poniższym przykładzie zadeklarowane są dwie klasy `PointTest` i `MainClass` . Publiczne elementy członkowskie `x` i `y` `PointTest` są dostępne bezpośrednio z programu `MainClass` .

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

W przypadku zmiany `public` poziomu dostępu na [prywatny](private.md) lub [chroniony](protected.md)zostanie wyświetlony komunikat o błędzie:

Element "PointTest. y" jest niedostępny z powodu swojego poziomu ochrony.

## <a name="c-language-specification"></a>specyfikacja języka C#  

Aby uzyskać więcej informacji, zobacz [zadeklarowane ułatwienia dostępu](~/_csharplang/spec/basic-concepts.md#declared-accessibility) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction). Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Modyfikatory dostępu](../../programming-guide/classes-and-structs/access-modifiers.md)
- [Słowa kluczowe języka C#](index.md)
- [Modyfikatory dostępu](access-modifiers.md)
- [Poziomy ułatwień dostępu](accessibility-levels.md)
- [Modyfikatory](index.md)
- [private](private.md)
- [protected](protected.md)
- [internal](internal.md)
