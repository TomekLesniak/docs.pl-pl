---
title: RemoveHandler — Instrukcja
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: a815241f20be12b3b7b4f2b87d50a8965021bbf0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871942"
---
# <a name="removehandler-statement"></a><span data-ttu-id="9ca3d-102">RemoveHandler — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="9ca3d-102">RemoveHandler Statement</span></span>

<span data-ttu-id="9ca3d-103">Usuwa skojarzenie między zdarzeniem a programem obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="9ca3d-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca3d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9ca3d-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="9ca3d-105">Części</span><span class="sxs-lookup"><span data-stu-id="9ca3d-105">Parts</span></span>  
  
|<span data-ttu-id="9ca3d-106">Termin</span><span class="sxs-lookup"><span data-stu-id="9ca3d-106">Term</span></span>|<span data-ttu-id="9ca3d-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="9ca3d-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="9ca3d-108">Nazwa obsługiwanego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="9ca3d-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="9ca3d-109">Nazwa procedury, która obecnie obsługuje zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="9ca3d-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ca3d-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9ca3d-110">Remarks</span></span>  

 <span data-ttu-id="9ca3d-111">`AddHandler`Instrukcje i `RemoveHandler` umożliwiają uruchamianie i zatrzymywanie obsługi zdarzeń dla określonego zdarzenia w dowolnym momencie podczas wykonywania programu.</span><span class="sxs-lookup"><span data-stu-id="9ca3d-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ca3d-112">W przypadku zdarzeń niestandardowych `RemoveHandler` instrukcja wywołuje `RemoveHandler` metodę dostępu zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="9ca3d-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="9ca3d-113">Aby uzyskać więcej informacji na temat zdarzeń niestandardowych, zobacz [instrukcja zdarzenia](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9ca3d-113">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ca3d-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="9ca3d-114">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="9ca3d-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9ca3d-115">See also</span></span>

- [<span data-ttu-id="9ca3d-116">AddHandler — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="9ca3d-116">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="9ca3d-117">Handles</span><span class="sxs-lookup"><span data-stu-id="9ca3d-117">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="9ca3d-118">Event — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="9ca3d-118">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="9ca3d-119">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="9ca3d-119">Events</span></span>](../../programming-guide/language-features/events/index.md)
