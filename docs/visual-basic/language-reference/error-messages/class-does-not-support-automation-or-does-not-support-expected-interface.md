---
title: Klasa nie obsługuje automatyzacji lub oczekiwanego interfejsu
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: aa97ae420a0a289979fe86db373c635361dc6475
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874645"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="07f5a-102">Klasa nie obsługuje automatyzacji lub oczekiwanego interfejsu</span><span class="sxs-lookup"><span data-stu-id="07f5a-102">Class does not support Automation or does not support expected interface</span></span>

<span data-ttu-id="07f5a-103">Klasa określona w `GetObject` `CreateObject` wywołaniu lub funkcji nie ma interfejsu programowania lub zmieniono projekt z. dll na. exe lub odwrotnie.</span><span class="sxs-lookup"><span data-stu-id="07f5a-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="07f5a-104">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="07f5a-104">To correct this error</span></span>  
  
1. <span data-ttu-id="07f5a-105">Zapoznaj się z dokumentacją aplikacji, która utworzyła obiekt, aby uzyskać ograniczenia dotyczące używania automatyzacji z tą klasą obiektów.</span><span class="sxs-lookup"><span data-stu-id="07f5a-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2. <span data-ttu-id="07f5a-106">Jeśli projekt został zmieniony z. dll na. exe lub odwrotnie, należy ręcznie wyrejestrować stary plik. dll lub. exe.</span><span class="sxs-lookup"><span data-stu-id="07f5a-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f5a-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="07f5a-107">See also</span></span>

- [<span data-ttu-id="07f5a-108">Typy błędów</span><span class="sxs-lookup"><span data-stu-id="07f5a-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="07f5a-109">Porozmawiaj z nami</span><span class="sxs-lookup"><span data-stu-id="07f5a-109">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
