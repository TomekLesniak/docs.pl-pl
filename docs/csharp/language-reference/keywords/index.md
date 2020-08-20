---
title: Słowa kluczowe języka C#
ms.date: 03/07/2017
f1_keywords:
- cs.keywords
helpviewer_keywords:
- keywords [C#]
- C# language, keywords
- Visual C#, keywords
- '@ keyword'
ms.custom: updateeachrelease
ms.assetid: e929b0f2-4b92-4d37-8060-23d323b098ad
ms.openlocfilehash: 51e3802ba7b78dab4c3f96365c51af83098c05c7
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656127"
---
# <a name="c-keywords"></a>Słowa kluczowe języka C#

Słowa kluczowe są wstępnie zdefiniowanymi, zarezerwowanymi identyfikatorami, które mają specjalne znaczenie dla kompilatora. Nie można ich używać jako identyfikatorów w programie, chyba że zawierają one `@` jako prefiks. Na przykład, `@if` jest prawidłowym identyfikatorem, ale `if` nie jest, ponieważ `if` jest słowem kluczowym.  
  
 W pierwszej tabeli w tym temacie wymieniono słowa kluczowe, które są zarezerwowane identyfikatory w dowolnej części programu w języku C#. W drugiej tabeli w tym temacie wymieniono kontekstowe słowa kluczowe w języku C#. Kontekstowe słowa kluczowe mają specjalne znaczenie tylko w ograniczonym kontekście programu i mogą być używane jako identyfikatory poza tym kontekstem. Ogólnie rzecz biorąc, po dodaniu nowych słów kluczowych do języka C# są one dodawane jako kontekstowe słowa kluczowe, aby uniknąć przerywania programów pisanych we wcześniejszych wersjach.  
  
|||||  
|---|---|---|---|  
|[streszczeń](abstract.md)|[definicj](../operators/type-testing-and-cast.md#as-operator)|[base](base.md)|[bool](../builtin-types/bool.md)|  
|[break](break.md)|[Bajc](../builtin-types/integral-numeric-types.md)|[spraw](switch.md)|[efektywn](try-catch.md)|  
|[char](../builtin-types/char.md)|[dane](checked.md)|[określonej](class.md)|[const](const.md)|  
|[utrzymać](continue.md)|[liczba dziesiętna](../builtin-types/floating-point-numeric-types.md)|[wartooć](default.md)|[Wierz](../builtin-types/reference-types.md)|  
|[do](do.md)|[liczba o podwójnej precyzji](../builtin-types/floating-point-numeric-types.md)|[else](if-else.md)|[podstawowe](../builtin-types/enum.md)|  
|[wydarzen](event.md)|[wprost](../operators/user-defined-conversion-operators.md)|[extern](extern.md)|[false](../builtin-types/bool.md)|  
|[finally](try-finally.md)|[FIXED](fixed-statement.md)|[liczba zmiennoprzecinkowa](../builtin-types/floating-point-numeric-types.md)|[dla](for.md)|  
|[foreach](foreach-in.md)|[goto](goto.md)|[if](if-else.md)|[Konwersja](../operators/user-defined-conversion-operators.md)|  
|[podczas](in.md)|[int](../builtin-types/integral-numeric-types.md)|[interfejsu](interface.md)|[internal](internal.md)|
|[była](is.md)|[skręt](lock-statement.md)|[liczba długa](../builtin-types/integral-numeric-types.md)|[obszaru](namespace.md)|
|[Nowy](../operators/new-operator.md)|[wartość null](null.md)|[object](../builtin-types/reference-types.md)|[zakład](../operators/operator-overloading.md)|
|[określoną](out.md)|[override](override.md)|[params](params.md)|[private](private.md)|
|[protected](protected.md)|[public](public.md)|[readonly](readonly.md)|[ref](ref.md)|
|[return](return.md)|[SByte](../builtin-types/integral-numeric-types.md)|[sealed](sealed.md)|[short](../builtin-types/integral-numeric-types.md)||
[sizeof](../operators/sizeof.md)|[stackalloc](../operators/stackalloc.md)|[static](static.md)|[parametry](../builtin-types/reference-types.md)|
|[konstrukcja](../builtin-types/struct.md)|[przełącznika](switch.md)|[this](this.md)|[throw](throw.md)|
|[oznacza](../builtin-types/bool.md)|[try](try-catch.md)|[typeof](../operators/type-testing-and-cast.md#typeof-operator)|[uint](../builtin-types/integral-numeric-types.md)|
|[ulong](../builtin-types/integral-numeric-types.md)|[unchecked](unchecked.md)|[niebezpieczne](unsafe.md)|[ushort](../builtin-types/integral-numeric-types.md)|
|[using](using.md)|[virtual](virtual.md)|[void](../builtin-types/void.md)|[volatile](volatile.md)|
|[while](while.md)|

## <a name="contextual-keywords"></a>Kontekstowe słowa kluczowe

 Kontekstowe słowo kluczowe jest używane do zapewnienia określonego znaczenia w kodzie, ale nie jest to słowo zarezerwowane w języku C#. Niektóre kontekstowe słowa kluczowe, takie jak `partial` i `where` , mają specjalne znaczenie w co najmniej dwóch kontekstach.  
  
||||  
|---|---|---|  
|[add](add.md)|[Użyj](extern-alias.md)|[ascending](ascending.md)|
|[async](async.md)|[await](../operators/await.md)|[by](by.md)|
|[descending](descending.md)|[dynamiczna](../builtin-types/reference-types.md)|[ubiegł](equals.md)|
|[wniosek](from-clause.md)|[get](get.md)|[globalne](../operators/namespace-alias-qualifier.md)|
|[Group](group-clause.md)|[przekształca](into.md)|[Złącza](join-clause.md)|
|[wpuść](let-clause.md)|[nameof](../operators/nameof.md)|[z](on.md)|
|[OrderBy](orderby-clause.md)|[częściowy (typ)](partial-type.md)|[częściowe (Metoda)](partial-method.md)|
|[usuwa](remove.md)|[zaznaczenia](select-clause.md)|[zbiór](set.md)|
|[niezarządzane (ograniczenie typu ogólnego)](where-generic-type-constraint.md)|[wartościami](value.md)|[funkcję](var.md)|
|[when (warunek filtru)](when.md)|[where (ograniczenie typu ogólnego)](where-generic-type-constraint.md)|[WHERE (klauzula zapytania)](where-clause.md)|
|[yield](yield.md)| | |
  
## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
