---
title: Klasy pochodne nie mogą wywoływać zdarzeń klasy bazowej
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 7b86420466d77a6aa45b1201a9375b4433e4b5ec
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163444"
---
# <a name="bc30029-derived-classes-cannot-raise-base-class-events"></a>BC30029: klasy pochodne nie mogą wywoływać zdarzeń klasy bazowej

Zdarzenie może być zgłaszane tylko z przestrzeni deklaracji, w której jest zadeklarowany. W związku z tym Klasa nie może wywoływać zdarzeń z żadnej innej klasy, nawet jednego z nich, z której pochodzą.

 **Identyfikator błędu:** BC30029

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Przenieś `Event` instrukcję lub `RaiseEvent` instrukcję tak, aby znajdowały się w tej samej klasie.

## <a name="see-also"></a>Zobacz też

- [Event — Instrukcja](../statements/event-statement.md)
- [RaiseEvent — Instrukcja](../statements/raiseevent-statement.md)
