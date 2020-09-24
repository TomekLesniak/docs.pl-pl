---
title: Jak zaimplementować niestandardowe metody dostępu do zdarzeń — Przewodnik programowania w języku C#
description: Dowiedz się, jak zaimplementować niestandardowe metody dostępu do zdarzeń. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 41c9bd255bf66cd914982b6044c4acaef66b8fcf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167564"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="5410d-104">Jak zaimplementować niestandardowe metody dostępu do zdarzeń (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="5410d-104">How to implement custom event accessors (C# Programming Guide)</span></span>

<span data-ttu-id="5410d-105">Zdarzenie jest specjalnym rodzajem delegata multiemisji, który może być wywoływany z klasy, w której jest zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="5410d-105">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="5410d-106">Kod klienta subskrybuje zdarzenie, podając odwołanie do metody, która powinna być wywoływana, gdy zdarzenie zostanie wyzwolone.</span><span class="sxs-lookup"><span data-stu-id="5410d-106">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="5410d-107">Te metody są dodawane do listy wywołań delegata za pomocą metod dostępu do zdarzeń, które przypominają metody dostępu do właściwości, z tą różnicą, że dostęp do zdarzeń jest nazwany `add` i `remove` .</span><span class="sxs-lookup"><span data-stu-id="5410d-107">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="5410d-108">W większości przypadków nie trzeba podawać niestandardowych metod dostępu do zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="5410d-108">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="5410d-109">Gdy w kodzie nie są dostarczane żadne niestandardowe metody dostępu do zdarzeń, kompilator doda je automatycznie.</span><span class="sxs-lookup"><span data-stu-id="5410d-109">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="5410d-110">Jednak w niektórych przypadkach może być konieczne zapewnienie zachowania niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="5410d-110">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="5410d-111">W tym temacie pokazano, [jak zaimplementować zdarzenia interfejsu](./how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="5410d-111">One such case is shown in the topic [How to implement interface events](./how-to-implement-interface-events.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="5410d-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="5410d-112">Example</span></span>  

 <span data-ttu-id="5410d-113">Poniższy przykład przedstawia sposób implementacji niestandardowych metod dostępu do zdarzeń dodawania i usuwania.</span><span class="sxs-lookup"><span data-stu-id="5410d-113">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="5410d-114">Chociaż można zastąpić dowolny kod wewnątrz metod dostępu, Zalecamy zablokowanie zdarzenia przed dodaniem lub usunięciem nowej metody obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="5410d-114">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a><span data-ttu-id="5410d-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5410d-115">See also</span></span>

- [<span data-ttu-id="5410d-116">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="5410d-116">Events</span></span>](./index.md)
- [<span data-ttu-id="5410d-117">wydarzen</span><span class="sxs-lookup"><span data-stu-id="5410d-117">event</span></span>](../../language-reference/keywords/event.md)
