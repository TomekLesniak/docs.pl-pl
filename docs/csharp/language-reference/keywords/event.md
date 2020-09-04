---
description: zdarzenie — odwołanie w C#
title: zdarzenie — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
ms.openlocfilehash: dff93496dfeceaf67777abe0b02ee2d620b3a5ca
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466043"
---
# <a name="event-c-reference"></a>zdarzenie (odwołanie w C#)

`event`Słowo kluczowe jest używane do deklarowania zdarzenia w klasie wydawcy.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak zadeklarować i zgłosić zdarzenie używające <xref:System.EventHandler> jako bazowego typu delegata. Aby zapoznać się z kompletnym przykładem kodu, który pokazuje, jak używać ogólnego <xref:System.EventHandler%601> typu delegata i jak subskrybować zdarzenie i utworzyć metodę obsługi zdarzeń, zobacz [How to Publish Events, które są zgodne z zaleceniami dotyczącymi platformy .NET](../../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).

[!code-csharp[csrefKeywordsModifiers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#7)]

Zdarzenia są specjalnym rodzajem delegatów multiemisji, który można wywołać tylko z poziomu klasy lub struktury, w której są zadeklarowane (Klasa wydawcy). Jeśli inne klasy lub struktury subskrybują zdarzenie, ich metody obsługi zdarzeń będą wywoływane, gdy Klasa wydawcy zgłasza zdarzenie. Aby uzyskać więcej informacji i przykładów kodu, zobacz [Events](../../programming-guide/events/index.md) and [delegats](../../programming-guide/delegates/index.md).

Zdarzenia mogą być oznaczone jako [publiczne](./public.md), [prywatne](./private.md), [chronione](./protected.md), [wewnętrzne](./internal.md), [chronione wewnętrznie](./protected-internal.md)lub [chronione prywatnie](./private-protected.md). Te Modyfikatory dostępu definiują sposób, w jaki użytkownicy klasy mogą uzyskać dostęp do zdarzenia. Aby uzyskać więcej informacji, zobacz [Modyfikatory dostępu](../../programming-guide/classes-and-structs/access-modifiers.md).

## <a name="keywords-and-events"></a>Słowa kluczowe i zdarzenia

Poniższe słowa kluczowe mają zastosowanie do zdarzeń.

|Słowo kluczowe|Opis|Więcej informacji|
|-------------|-----------------|--------------------------|
|[static](./static.md)|Sprawia, że zdarzenie jest dostępne dla wywoływania w dowolnym momencie, nawet jeśli nie istnieje żadne wystąpienie klasy.|[Klasy statyczne i statyczni członkowie klas](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|
|[virtual](./virtual.md)|Umożliwia klasom pochodnym przesłonięcie zachowania zdarzenia za pomocą słowa kluczowego [override](./override.md) .|[Dziedziczenie](../../programming-guide/classes-and-structs/inheritance.md)|
|[sealed](./sealed.md)|Określa, że dla klas pochodnych nie jest już wirtualna.||
|[streszczeń](./abstract.md)|Kompilator nie będzie generował `add` `remove` bloków dostępu do zdarzeń i, dlatego klasy pochodne muszą zapewnić własną implementację.||

Zdarzenie może być zadeklarowane jako zdarzenie statyczne za pomocą słowa kluczowego [static](./static.md) . To sprawia, że zdarzenie jest dostępne dla wywoływania w dowolnym momencie, nawet jeśli nie istnieje żadne wystąpienie klasy. Aby uzyskać więcej informacji, zobacz [klasy statyczne i statyczne elementy członkowskie klas](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).

Zdarzenie może być oznaczone jako zdarzenie wirtualne przy użyciu słowa kluczowego [Virtual](./virtual.md) . Dzięki temu klasy pochodne zastępują zachowanie zdarzeń za pomocą słowa kluczowego [override](./override.md) . Aby uzyskać więcej informacji, zobacz [dziedziczenie](../../programming-guide/classes-and-structs/inheritance.md). Zdarzenie przesłaniające zdarzenie wirtualne może być również [zapieczętowane](./sealed.md), które określa, że dla klas pochodnych nie jest już wirtualna. Na koniec zdarzenie może być zadeklarowane jako [abstract](./abstract.md), co oznacza, że kompilator nie będzie generował `add` `remove` bloków dostępu do zdarzeń i. W związku z tym klasy pochodne muszą dostarczać własne implementacje.

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz także

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](./index.md)
- [add](./add.md)
- [usuwa](./remove.md)
- [Modyfikatory](index.md)
- [Jak łączyć delegatów (delegatów multiemisji)](../../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
