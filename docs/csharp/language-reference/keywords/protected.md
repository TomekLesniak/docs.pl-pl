---
description: Protected — odwołanie w C#
title: Protected — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: af0c7ab5ebb6980bb0381e46fd38e9470f3a2152
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536759"
---
# <a name="protected-c-reference"></a>protected (odwołanie w C#)

`protected`Słowo kluczowe jest modyfikatorem dostępu składowej.

 > Ta strona dotyczy `protected` dostępu. `protected`Słowo kluczowe jest również częścią [`protected internal`](protected-internal.md) [`private protected`](private-protected.md) modyfikatorów i dostępu.

Chroniony element członkowski jest dostępny w jego klasie i wystąpieniach klasy pochodnej.

Aby uzyskać porównanie `protected` z innymi modyfikatorami dostępu, zobacz [poziomy dostępności](accessibility-levels.md).

## <a name="example"></a>Przykład

Chroniony element członkowski klasy bazowej jest dostępny w klasie pochodnej tylko wtedy, gdy dostęp odbywa się za pomocą typu klasy pochodnej. Rozważmy na przykład następujący segment kodu:

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

Instrukcja `a.x = 10` generuje błąd, ponieważ znajduje się w metodzie statycznej Main i nie jest wystąpieniem klasy B.

Elementy członkowskie struktury nie mogą być chronione, ponieważ struktura nie może być dziedziczona.

## <a name="example"></a>Przykład

W tym przykładzie Klasa pochodzi `DerivedPoint` od `Point` . W związku z tym można uzyskać dostęp do chronionych elementów członkowskich klasy bazowej bezpośrednio z klasy pochodnej.

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

Jeśli zmienisz poziomy dostępu dla `x` i `y` na [prywatne](private.md), kompilator będzie wystawiał komunikaty o błędach:

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a>specyfikacja języka C#  

Aby uzyskać więcej informacji, zobacz [zadeklarowane ułatwienia dostępu](~/_csharplang/spec/basic-concepts.md#declared-accessibility) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction). Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.

## <a name="see-also"></a>Zobacz także

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Modyfikatory dostępu](access-modifiers.md)
- [Poziomy ułatwień dostępu](accessibility-levels.md)
- [Modyfikatory](index.md)
- [public](public.md)
- [private](private.md)
- [internal](internal.md)
- [Zagadnienia dotyczące zabezpieczeń wewnętrznych wirtualnych słów kluczowych](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))
