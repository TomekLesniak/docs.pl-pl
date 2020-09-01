---
description: Private — słowo kluczowe — odwołanie w C#
title: Private — słowo kluczowe — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: e6f40712fd2cca6d7b1f64760f1c6c5dd5c71370
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139401"
---
# <a name="private-c-reference"></a>private (odwołanie w C#)

`private`Słowo kluczowe jest modyfikatorem dostępu składowej.

> Ta strona dotyczy `private` dostępu. `private`Słowo kluczowe jest również częścią [`private protected`](./private-protected.md) modyfikatora dostępu.

Dostęp prywatny to najmniejszy poziom dostępu. Prywatne elementy członkowskie są dostępne tylko w treści klasy lub struktury, w której są zadeklarowane, jak w poniższym przykładzie:

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

Typy zagnieżdżone w tej samej treści mogą również uzyskiwać dostęp do tych prywatnych członków.

Jest to błąd czasu kompilacji, który odwołuje się do prywatnego elementu członkowskiego spoza klasy lub struktury, w której jest zadeklarowany.

Aby uzyskać porównanie `private` z innymi modyfikatorami dostępu, zobacz [poziomy dostępności](accessibility-levels.md) i [Modyfikatory dostępu](../../programming-guide/classes-and-structs/access-modifiers.md).

## <a name="example"></a>Przykład

W tym przykładzie `Employee` Klasa zawiera dwa prywatne elementy członkowskie danych `name` i `salary` . Jako prywatne elementy członkowskie nie są dostępne z wyjątkiem metod składowych. Metody publiczne o nazwie `GetName` i `Salary` są dodawane w celu umożliwienia kontrolowanego dostępu do prywatnych członków. `name`Dostęp do elementu członkowskiego uzyskuje się za pomocą metody publicznej, a `salary` członek jest dostępny w postaci publicznej właściwości tylko do odczytu. (Zobacz [Właściwości](../../programming-guide/classes-and-structs/properties.md) , aby uzyskać więcej informacji).

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a>specyfikacja języka C#  

Aby uzyskać więcej informacji, zobacz [zadeklarowane ułatwienia dostępu](~/_csharplang/spec/basic-concepts.md#declared-accessibility) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction). Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Modyfikatory dostępu](access-modifiers.md)
- [Poziomy ułatwień dostępu](accessibility-levels.md)
- [Modyfikatory](index.md)
- [public](public.md)
- [protected](protected.md)
- [internal](internal.md)
