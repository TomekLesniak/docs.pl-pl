---
title: Zdarzenia zmiennych WithEvents nie mogą być obsługiwane przez metody nieudostępnione
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: d519463e036de215143efad5be3745484ac17d82
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874294"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Zdarzenia zmiennych WithEvents nie mogą być obsługiwane przez metody nieudostępnione

Zmienna zadeklarowana z `Shared` modyfikatorem jest zmienną udostępnioną. Zmienna współdzielona identyfikuje dokładnie jedną lokalizację magazynu. Zmienna zadeklarowana z `WithEvents` modyfikatorem modyfikującym, że typ, do którego należy zmienna, obsługuje zestaw zdarzeń zgłaszanych przez zmienną. Gdy wartość jest przypisana do zmiennej, właściwość utworzona przez `WithEvents` deklarację odłączy wszelkie istniejące procedury obsługi zdarzeń i przechwytuje nowy program obsługi zdarzeń za pośrednictwem `Add` metody.  
  
 **Identyfikator błędu:** BC30594  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Zadeklaruj procedurę obsługi zdarzeń `Shared` .  
  
## <a name="see-also"></a>Zobacz też

- [Shared](../modifiers/shared.md)
- [WithEvents](../modifiers/withevents.md)
