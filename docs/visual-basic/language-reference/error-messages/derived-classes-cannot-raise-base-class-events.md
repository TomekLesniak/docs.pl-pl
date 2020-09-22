---
title: Klasy pochodne nie mogą wywoływać zdarzeń klasy bazowej
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0233a1584c5e871506b5c4762e98874c343f19b8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874487"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Klasy pochodne nie mogą wywoływać zdarzeń klasy bazowej

Zdarzenie może być zgłaszane tylko z przestrzeni deklaracji, w której jest zadeklarowany. W związku z tym Klasa nie może wywoływać zdarzeń z żadnej innej klasy, nawet jednego z nich, z której pochodzą.  
  
 **Identyfikator błędu:** BC30029  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Przenieś `Event` instrukcję lub `RaiseEvent` instrukcję tak, aby znajdowały się w tej samej klasie.  
  
## <a name="see-also"></a>Zobacz też

- [Event — Instrukcja](../statements/event-statement.md)
- [RaiseEvent — Instrukcja](../statements/raiseevent-statement.md)
