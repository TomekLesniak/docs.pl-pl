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
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="85708-102">Obiekt lub klasa nie obsługuje zbioru zdarzeń</span><span class="sxs-lookup"><span data-stu-id="85708-102">Object or class does not support the set of events</span></span>

<span data-ttu-id="85708-103">Podjęto próbę użycia `WithEvents` zmiennej ze składnikiem, który nie może współpracować ze źródłem zdarzenia dla określonego zestawu zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="85708-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="85708-104">Na przykład chcesz wypróbować zdarzenia obiektu, a następnie utworzyć inny obiekt, który `Implements` jest pierwszym obiektem.</span><span class="sxs-lookup"><span data-stu-id="85708-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="85708-105">Mimo że można zastanowić się, że można wymyślić zdarzenia z zaimplementowanego obiektu, nie zawsze jest to przypadek.</span><span class="sxs-lookup"><span data-stu-id="85708-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="85708-106">`Implements` implementuje interfejs tylko dla metod i właściwości.</span><span class="sxs-lookup"><span data-stu-id="85708-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="85708-107">`WithEvents` nie jest obsługiwany w przypadku prywatnych `UserControls` , ponieważ informacje o typie, które są konieczne do podniesienia, `ObjectEvent` nie są dostępne w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="85708-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="85708-108">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="85708-108">To correct this error</span></span>

- <span data-ttu-id="85708-109">Nie można ujścia zdarzeń dla składnika, który nie jest źródłem zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="85708-109">You cannot sink events for a component that does not source events.</span></span>

## <a name="see-also"></a><span data-ttu-id="85708-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="85708-110">See also</span></span>

- [<span data-ttu-id="85708-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="85708-111">WithEvents</span></span>](../modifiers/withevents.md)
- [<span data-ttu-id="85708-112">Implements — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="85708-112">Implements Statement</span></span>](../statements/implements-statement.md)
