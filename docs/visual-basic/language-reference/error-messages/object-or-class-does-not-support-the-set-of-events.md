---
title: Obiekt lub klasa nie obsługuje zbioru zdarzeń
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: c5e8b8de3477147fc3174cdbee401c89753004ad
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159953"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Obiekt lub klasa nie obsługuje zbioru zdarzeń

Podjęto próbę użycia `WithEvents` zmiennej ze składnikiem, który nie może współpracować ze źródłem zdarzenia dla określonego zestawu zdarzeń. Na przykład chcesz wypróbować zdarzenia obiektu, a następnie utworzyć inny obiekt, który `Implements` jest pierwszym obiektem. Mimo że można zastanowić się, że można wymyślić zdarzenia z zaimplementowanego obiektu, nie zawsze jest to przypadek. `Implements` implementuje interfejs tylko dla metod i właściwości. `WithEvents` nie jest obsługiwany w przypadku prywatnych `UserControls` , ponieważ informacje o typie, które są konieczne do podniesienia, `ObjectEvent` nie są dostępne w czasie wykonywania.

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Nie można ujścia zdarzeń dla składnika, który nie jest źródłem zdarzeń.

## <a name="see-also"></a>Zobacz też

- [WithEvents](../modifiers/withevents.md)
- [Implements — Instrukcja](../statements/implements-statement.md)
