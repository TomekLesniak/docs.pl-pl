---
title: Private Protected
ms.date: 05/10/2018
f1_keywords:
- vb.PrivateProtected
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 8ad1509da71bc80b33700d363ddd4569a0965dff
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303468"
---
# <a name="private-protected-visual-basic"></a>Prywatna chroniona (Visual Basic)

`Private Protected`Kombinacja słowa kluczowego jest modyfikatorem dostępu składowej. `Private Protected`Członek jest dostępny dla wszystkich elementów członkowskich w swojej klasie zawierającej, a także typów pochodzących od klasy zawierającej, ale tylko wtedy, gdy znajdują się w jego zestawie zawierającym.

Można określić `Private Protected` tylko dla elementów członkowskich klasy; nie można stosować `Private Protected` do elementów członkowskich struktury, ponieważ struktury nie mogą być dziedziczone.

`Private Protected`Modyfikator dostępu jest obsługiwany przez Visual Basic 15,5 i nowsze. Aby go użyć, można dodać następujący element do pliku projektu Visual Basic ( \* . vbproj). Tak długo, jak Visual Basic 15,5 lub nowszy jest zainstalowany w systemie, umożliwia korzystanie ze wszystkich funkcji językowych obsługiwanych przez najnowszą wersję kompilatora Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Aby uzyskać więcej informacji [, zobacz Ustawianie wersji językowej Visual Basic](../configure-language-version.md).

> [!NOTE]
> W programie Visual Studio wybierz pozycję Pomoc F1, aby uzyskać pomoc dotyczącą `private protected` opcji [Private](private.md) lub [Protected](protected.md). IDE wybiera pojedynczy token w obszarze kursora zamiast słowa złożonego.

## <a name="rules"></a>Reguły

- **Kontekst deklaracji.** Można używać `Private Protected` tylko na poziomie klasy. Oznacza to, że kontekst deklaracji dla `Protected` elementu musi być klasą i nie może być plikiem źródłowym, przestrzenią nazw, interfejsem, modułem, strukturą ani procedurą.

## <a name="behavior"></a>Zachowanie

- **Poziom dostępu.** Cały kod w klasie ma dostęp do jego elementów. Kod w dowolnej klasie, która dziedziczy z klasy bazowej i znajduje się w tym samym zestawie, może uzyskać dostęp do wszystkich `Private Protected` elementów klasy bazowej. Jednak kod w dowolnej klasie, która dziedziczy z klasy bazowej i znajduje się w innym zestawie nie może uzyskać dostępu do elementów klasy bazowej `Private Protected` .

- **Modyfikatory dostępu.** Słowa kluczowe określające poziom dostępu są nazywane *modyfikatorami dostępu*. Aby porównać Modyfikatory dostępu, zobacz [poziomy dostępu w Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

`Private Protected`Modyfikator może być używany w tych kontekstach:

- [Instrukcja klasy](../statements/class-statement.md) klasy zagnieżdżonej

- [Const, instrukcja](../statements/const-statement.md)

- [Declare — Instrukcja](../statements/declare-statement.md)

- [Delegata — instrukcja](../statements/delegate-statement.md) delegata zagnieżdżona w klasie

- [Dim, instrukcja](../statements/dim-statement.md)

- [Instrukcja enum](../statements/enum-statement.md) wyliczenia zagnieżdżona w klasie

- [Event — Instrukcja](../statements/event-statement.md)

- [Function, instrukcja](../statements/function-statement.md)

- [Instrukcja interfejsu](../statements/interface-statement.md) w interfejsie zagnieżdżonym w klasie

- [Property — Instrukcja](../statements/property-statement.md)

- [Instrukcja struktury](../statements/structure-statement.md) struktury zagnieżdżonej w klasie

- [Sub, instrukcja](../statements/sub-statement.md)

## <a name="see-also"></a>Zobacz też

- [Publiczne](public.md)
- [Chronione](protected.md)
- [Osoby](friend.md)
- [Prywatne](private.md)
- [Protected Friend](./protected-friend.md)
- [Poziomy dostępu w Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedury](../../programming-guide/language-features/procedures/index.md)
- [Struktury](../../programming-guide/language-features/data-types/structures.md)
- [Obiekty i klasy](../../programming-guide/language-features/objects-and-classes/index.md)
