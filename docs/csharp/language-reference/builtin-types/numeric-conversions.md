---
description: 'Dowiedz się więcej na temat konwersji niejawnych i jawnych między wbudowanymi typami liczbowymi w języku C #'
title: Wbudowane konwersje numeryczne — odwołanie w C#
ms.date: 10/22/2019
helpviewer_keywords:
- implicit numeric conversions [C#]
- explicit numeric conversion [C#]
- numeric conversions [C#], implicit
- numeric conversions [C#], explicit
- conversions [C#], implicit numeric
- conversions [C#], explicit numeric
ms.openlocfilehash: ee5def3b5e0e067919a8c8335db701dbb6dd4d88
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142248"
---
# <a name="built-in-numeric-conversions-c-reference"></a>Wbudowane konwersje numeryczne (odwołanie w C#)

Język C# zawiera zestaw [całkowitych](integral-numeric-types.md) i [zmiennoprzecinkowych](floating-point-numeric-types.md) typów liczbowych. Istnieje konwersja między dowolnymi dwoma typami liczbowymi, niejawnymi lub jawnymi. Aby przeprowadzić konwersję jawną, należy użyć [wyrażenia Cast](../operators/type-testing-and-cast.md#cast-expression) .

## <a name="implicit-numeric-conversions"></a>Niejawne konwersje liczbowe

W poniższej tabeli przedstawiono wstępnie zdefiniowane konwersje niejawne między wbudowanymi typami liczbowymi:

|Źródło|Działanie|
|----------|--------|
|[SByte](integral-numeric-types.md)|`short`, `int` , `long` , `float` , `double` lub `decimal`|
|[Bajc](integral-numeric-types.md)|`short`,,,,,, `ushort` `int` `uint` `long` `ulong` `float` , `double` lub `decimal`|
|[short](integral-numeric-types.md)|`int`, `long` , `float` , `double` lub `decimal`|
|[ushort](integral-numeric-types.md)|`int`, `uint` , `long` ,,, `ulong` `float` `double` lub `decimal`|
|[int](integral-numeric-types.md)|`long`, `float` , `double` lub `decimal`|
|[uint](integral-numeric-types.md)|`long`, `ulong` , `float` , `double` lub `decimal`|
|[liczba długa](integral-numeric-types.md)|`float`, `double` lub `decimal`|
|[ulong](integral-numeric-types.md)|`float`, `double` lub `decimal`|
|[liczba zmiennoprzecinkowa](floating-point-numeric-types.md)|`double`|

> [!NOTE]
> Niejawne konwersje z `int` , `uint` , `long` , lub `ulong` do `float` i z oraz do i z `long` lub do, `ulong` `double` mogą spowodować utratę precyzji, ale nigdy nie utracisz kolejności wielkości. Inne niejawne konwersje numeryczne nigdy nie tracą żadnych informacji.

Należy również pamiętać, że

- Dowolny [całkowity typ liczbowy](integral-numeric-types.md) jest niejawnie konwertowany do dowolnego [zmiennoprzecinkowego typu liczbowego](floating-point-numeric-types.md).

- Brak niejawnych konwersji do `byte` typów i `sbyte` . Brak niejawnych konwersji z `double` typów i `decimal` .

- Brak niejawnych konwersji między `decimal` typem a `float` lub `double` .

- Wartość stałego wyrażenia typu `int` (na przykład wartość reprezentowana przez literał typu integer) może być niejawnie konwertowana na `sbyte` ,,,, `byte` `short` `ushort` `uint` lub `ulong` , jeśli znajduje się w zakresie typu docelowego:

  ```csharp
  byte a = 13;
  byte b = 300;  // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

  Jak pokazano w poprzednim przykładzie, jeśli wartość stała znajduje się poza zakresem typu docelowego, wystąpi błąd kompilatora [CS0031](../../misc/cs0031.md) .

## <a name="explicit-numeric-conversions"></a>Jawne konwersje numeryczne

W poniższej tabeli przedstawiono wstępnie zdefiniowane Konwersje jawne między wbudowanymi typami liczbowymi, dla których nie istnieje [niejawna konwersja](#implicit-numeric-conversions):

|Źródło|Działanie|
|----------|--------|
|[SByte](integral-numeric-types.md)|`byte`, `ushort` , `uint` lub `ulong`|
|[Bajc](integral-numeric-types.md)|`sbyte`|
|[short](integral-numeric-types.md)|`sbyte`, `byte` , `ushort` , `uint` lub `ulong`|
|[ushort](integral-numeric-types.md)|`sbyte`, `byte` lub `short`|
|[int](integral-numeric-types.md)|`sbyte`, `byte` , `short` , `ushort` , `uint` lub `ulong`|
|[uint](integral-numeric-types.md)|`sbyte`, `byte` , `short` , `ushort` lub `int`|
|[liczba długa](integral-numeric-types.md)|`sbyte`, `byte` , `short` ,,, `ushort` `int` `uint` lub `ulong`|
|[ulong](integral-numeric-types.md)|`sbyte`, `byte` , `short` ,,, `ushort` `int` `uint` lub `long`|
|[liczba zmiennoprzecinkowa](floating-point-numeric-types.md)|`sbyte`,,,,,, `byte` `short` `ushort` `int` `uint` `long` , `ulong` lub `decimal`|
|[liczba o podwójnej precyzji](floating-point-numeric-types.md)|`sbyte`,,,,, `byte` `short` `ushort` `int` `uint` , `long` , `ulong` , `float` lub `decimal`|
|[liczba dziesiętna](floating-point-numeric-types.md)|`sbyte`,,,,, `byte` `short` `ushort` `int` `uint` , `long` , `ulong` , `float` lub `double`|

> [!NOTE]
> Jawna konwersja numeryczna może spowodować utratę danych lub zgłosić wyjątek, zwykle jest to <xref:System.OverflowException> .

Należy również pamiętać, że

- W przypadku konwersji wartości typu całkowitego na inny typ całkowity wynik zależy od [kontekstu sprawdzania](../keywords/checked-and-unchecked.md)przepełnienia. W kontekście zaznaczania konwersja powiedzie się, jeśli wartość źródłowa należy do zakresu typu docelowego. W przeciwnym razie <xref:System.OverflowException> jest zgłaszany. W kontekście niesprawdzonym konwersja zawsze kończy się powodzeniem i przechodzi w następujący sposób:

  - Jeśli typ źródła jest większy niż typ docelowy, wartość źródłowa zostanie obcięta przez odrzucenie jej najbardziej znaczących bitów. Następnie wynik jest traktowany jako wartość typu docelowego.

  - Jeśli typ źródła jest mniejszy niż typ docelowy, wartość źródłowa jest podwyższana lub równa zero, tak aby była tego samego rozmiaru co typ docelowy. Jeśli typ źródła jest podpisany, jest używane rozszerzenie-znak. Jeśli typ źródła jest niepodpisany, jest używane rozszerzenie o wartości zero. Następnie wynik jest traktowany jako wartość typu docelowego.

  - Jeśli typ źródła ma taki sam rozmiar jak typ docelowy, wartość źródłowa jest traktowana jako wartość typu docelowego.

- Podczas konwersji `decimal` wartości na typ całkowity, ta wartość jest zaokrąglana do zera do najbliższej wartości całkowitej. Jeśli uzyskana wartość całkowita jest poza zakresem typu docelowego, <xref:System.OverflowException> zostanie zgłoszony.

- W przypadku konwersji `double` lub `float` wartości na typ całkowity ta wartość jest zaokrąglana do zera do najbliższej wartości całkowitej. Jeśli wynikowa wartość całkowita znajduje się poza zakresem typu docelowego, wynik zależy od [kontekstu sprawdzania](../keywords/checked-and-unchecked.md)przepełnienia. W kontekście, który <xref:System.OverflowException> jest zgłaszany, a w kontekście niesprawdzonym, wynik jest nieokreśloną wartością typu docelowego.

- Podczas konwersji `double` na `float` `double` wartość jest zaokrąglana do najbliższej `float` wartości. Jeśli `double` wartość jest za mała lub zbyt duża, aby można ją było dopasować do `float` typu, wynik wynosi zero lub nieskończoność.

- Podczas konwertowania `float` lub `double` do `decimal` , wartość źródłowa jest konwertowana na `decimal` reprezentację i zaokrąglana do najbliższej liczby po 28 miejscach dziesiętnych, jeśli jest to wymagane. W zależności od wartości źródłowej może wystąpić jeden z następujących wyników:

  - Jeśli wartość źródłowa jest zbyt mała, aby była reprezentowana jako `decimal` , wynik zmieni się na zero.

  - Jeśli wartością źródłową jest NaN (nie liczba), nieskończoność lub zbyt duża do reprezentowania jako `decimal` , <xref:System.OverflowException> jest generowany.

- Podczas konwertowania `decimal` na `float` lub `double` , wartość źródłowa jest zaokrąglana odpowiednio do najbliższej `float` lub `double` wartości.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):

- [Niejawne konwersje liczbowe](~/_csharplang/spec/conversions.md#implicit-numeric-conversions)
- [Jawne konwersje numeryczne](~/_csharplang/spec/conversions.md#explicit-numeric-conversions)

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Rzutowanie i konwersje typów](../../programming-guide/types/casting-and-type-conversions.md)
