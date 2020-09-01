---
description: modyfikator statyczny — odwołanie w C#
title: modyfikator statyczny — odwołanie w C#
ms.date: 04/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: f42636d1bbdf4342297f46f50ec6dfc2a70eacad
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142066"
---
# <a name="static-c-reference"></a>static (odwołanie w C#)

Na tej stronie omówiono `static` słowo kluczowe modyfikator. `static`Słowo kluczowe jest również częścią [`using static`](using-static.md) dyrektywy.

Użyj `static` modyfikatora, aby zadeklarować statyczną składową, która należy do samego typu, a nie do określonego obiektu. `static`Modyfikator może służyć do deklarowania `static` klas. W klasach, interfejsach i strukturach można dodać `static` modyfikator do pól, metod, właściwości, operatorów, zdarzeń i konstruktorów. `static`Modyfikator nie może być używany z indeksatorami lub finalizatorami. Aby uzyskać więcej informacji, zobacz [klasy statyczne i statyczne elementy członkowskie klas](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).

## <a name="example---static-class"></a>Przykład — Klasa statyczna

Następująca Klasa jest zadeklarowana jako `static` i zawiera tylko `static` metody:

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

Deklaracja stałej lub typu jest niejawnie członkiem `static` . `static`Nie można odwołać się do elementu członkowskiego za pomocą wystąpienia. Zamiast tego jest przywoływany przez nazwę typu. Rozważmy na przykład następujące klasy:

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

Aby odwołać się do `static` elementu członkowskiego `x` , należy użyć w pełni kwalifikowanej nazwy, `MyBaseC.MyStruct.x` chyba że element członkowski jest dostępny z tego samego zakresu:

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

Chociaż wystąpienie klasy zawiera oddzielną kopię wszystkich pól wystąpienia klasy, istnieje tylko jedna kopia każdego `static` pola.

Nie można użyć [`this`](this.md) w celu odwoływania się do `static` metod lub metody dostępu do właściwości.

Jeśli `static` słowo kluczowe jest stosowane do klasy, wszystkie elementy członkowskie klasy muszą mieć wartość `static` .

Klasy, interfejsy i `static` klasy mogą mieć `static` konstruktory. `static`Konstruktor jest wywoływany w pewnym momencie od momentu uruchomienia programu i wystąpienia klasy.

> [!NOTE]
> `static`Słowo kluczowe ma bardziej ograniczone zastosowania niż w języku C++. Aby porównać ze słowem kluczowym języka C++, zobacz [klasy magazynu (C++)](/cpp/cpp/storage-classes-cpp#static).

Aby przedstawić `static` członków, należy rozważyć klasę, która reprezentuje pracownika firmy. Załóżmy, że Klasa zawiera metodę służącą do policzania pracowników i pola do przechowywania liczby pracowników. Zarówno Metoda, jak i pole nie należy do żadnego wystąpienia jednego pracownika. Zamiast tego należą do klasy pracowników jako całości. Należy je zadeklarować jako `static` elementy członkowskie klasy.

## <a name="example---static-field-and-method"></a>Przykład — statyczne pole i Metoda

Ten przykład odczytuje nazwę i identyfikator nowego pracownika, zwiększa licznik pracownika według jednego i wyświetla informacje dotyczące nowego pracownika oraz nową liczbę pracowników. Ten program odczytuje bieżącą liczbę pracowników z klawiatury.

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a>Przykład — Inicjalizacja statyczna

Ten przykład pokazuje, że można zainicjować `static` pole przy użyciu innego `static` pola, które nie zostało jeszcze zadeklarowane. Wyniki będą niezdefiniowane, dopóki nie zostanie jawnie przypisana wartość do `static` pola.

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Modyfikatory](index.md)
- [za pomocą dyrektywy static](using-static.md)
- [Klasy statyczne i statyczni członkowie klas](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
