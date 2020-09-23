---
title: 'Porady: deklarowanie zdarzeń niestandardowych w celu zachowywania pamięci'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 78934e3e5ae7d5a3f5867c99a9f1db760c65ecbf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075125"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="5ff98-102">Porady: deklarowanie zdarzeń niestandardowych w celu zachowywania pamięci (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ff98-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>

<span data-ttu-id="5ff98-103">Istnieje kilka okoliczności, w których ważna jest niska użycie pamięci przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="5ff98-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="5ff98-104">Zdarzenia niestandardowe umożliwiają aplikacji używanie pamięci tylko dla zdarzeń, które obsługuje.</span><span class="sxs-lookup"><span data-stu-id="5ff98-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="5ff98-105">Domyślnie, gdy Klasa deklaruje zdarzenie, kompilator przydziela pamięć dla pola do przechowywania informacji o zdarzeniu.</span><span class="sxs-lookup"><span data-stu-id="5ff98-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="5ff98-106">Jeśli klasa ma wiele nieużywanych zdarzeń, niepotrzebnie zajmują pamięć.</span><span class="sxs-lookup"><span data-stu-id="5ff98-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="5ff98-107">Zamiast korzystać z domyślnej implementacji zdarzeń, które Visual Basic zapewnia, można użyć niestandardowych zdarzeń do szczegółowego zarządzania użyciem pamięci.</span><span class="sxs-lookup"><span data-stu-id="5ff98-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ff98-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="5ff98-108">Example</span></span>  

 <span data-ttu-id="5ff98-109">W tym przykładzie Klasa używa jednego wystąpienia <xref:System.ComponentModel.EventHandlerList> klasy, przechowywanego w `Events` polu, do przechowywania informacji o zdarzeniach w użyciu.</span><span class="sxs-lookup"><span data-stu-id="5ff98-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="5ff98-110"><xref:System.ComponentModel.EventHandlerList>Klasa jest zoptymalizowaną klasą listy zaprojektowaną do przechowywania delegatów.</span><span class="sxs-lookup"><span data-stu-id="5ff98-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="5ff98-111">Wszystkie zdarzenia w klasie używają pola, `Events` Aby śledzić, które metody obsługują każde zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="5ff98-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="5ff98-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5ff98-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="5ff98-113">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="5ff98-113">Events</span></span>](index.md)
- [<span data-ttu-id="5ff98-114">Instrukcje: deklarowanie zdarzeń niestandardowych w celu unikania blokowania</span><span class="sxs-lookup"><span data-stu-id="5ff98-114">How to: Declare Custom Events To Avoid Blocking</span></span>](how-to-declare-custom-events-to-avoid-blocking.md)
