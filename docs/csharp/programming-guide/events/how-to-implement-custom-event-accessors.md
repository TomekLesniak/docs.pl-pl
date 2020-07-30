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
ms.openlocfilehash: 4094aa1fedbceb68790b484608b3ea0ebc1e5cf6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302142"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="916a1-104">Jak zaimplementować niestandardowe metody dostępu do zdarzeń (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="916a1-104">How to implement custom event accessors (C# Programming Guide)</span></span>
<span data-ttu-id="916a1-105">Zdarzenie jest specjalnym rodzajem delegata multiemisji, który może być wywoływany z klasy, w której jest zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="916a1-105">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="916a1-106">Kod klienta subskrybuje zdarzenie, podając odwołanie do metody, która powinna być wywoływana, gdy zdarzenie zostanie wyzwolone.</span><span class="sxs-lookup"><span data-stu-id="916a1-106">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="916a1-107">Te metody są dodawane do listy wywołań delegata za pomocą metod dostępu do zdarzeń, które przypominają metody dostępu do właściwości, z tą różnicą, że dostęp do zdarzeń jest nazwany `add` i `remove` .</span><span class="sxs-lookup"><span data-stu-id="916a1-107">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="916a1-108">W większości przypadków nie trzeba podawać niestandardowych metod dostępu do zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="916a1-108">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="916a1-109">Gdy w kodzie nie są dostarczane żadne niestandardowe metody dostępu do zdarzeń, kompilator doda je automatycznie.</span><span class="sxs-lookup"><span data-stu-id="916a1-109">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="916a1-110">Jednak w niektórych przypadkach może być konieczne zapewnienie zachowania niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="916a1-110">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="916a1-111">W tym temacie pokazano, [jak zaimplementować zdarzenia interfejsu](./how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="916a1-111">One such case is shown in the topic [How to implement interface events](./how-to-implement-interface-events.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="916a1-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="916a1-112">Example</span></span>  
 <span data-ttu-id="916a1-113">Poniższy przykład przedstawia sposób implementacji niestandardowych metod dostępu do zdarzeń dodawania i usuwania.</span><span class="sxs-lookup"><span data-stu-id="916a1-113">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="916a1-114">Chociaż można zastąpić dowolny kod wewnątrz metod dostępu, Zalecamy zablokowanie zdarzenia przed dodaniem lub usunięciem nowej metody obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="916a1-114">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a><span data-ttu-id="916a1-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="916a1-115">See also</span></span>

- [<span data-ttu-id="916a1-116">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="916a1-116">Events</span></span>](./index.md)
- [<span data-ttu-id="916a1-117">wydarzen</span><span class="sxs-lookup"><span data-stu-id="916a1-117">event</span></span>](../../language-reference/keywords/event.md)
