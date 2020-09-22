---
title: AddHandler — Instrukcja
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 79dbe174209e91f13f5b43e8cdeb0b42edc4d163
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866715"
---
# <a name="addhandler-statement"></a><span data-ttu-id="b1a92-102">AddHandler — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="b1a92-102">AddHandler Statement</span></span>

<span data-ttu-id="b1a92-103">Kojarzy zdarzenie z programem obsługi zdarzeń w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b1a92-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1a92-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b1a92-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="b1a92-105">Części</span><span class="sxs-lookup"><span data-stu-id="b1a92-105">Parts</span></span>  

|||
|---|---|
|<span data-ttu-id="b1a92-106">event</span><span class="sxs-lookup"><span data-stu-id="b1a92-106">event</span></span>|<span data-ttu-id="b1a92-107">Nazwa zdarzenia do obsłużenia.</span><span class="sxs-lookup"><span data-stu-id="b1a92-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="b1a92-108">Nazwa procedury, która obsługuje zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="b1a92-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="b1a92-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b1a92-109">Remarks</span></span>  

 <span data-ttu-id="b1a92-110">`AddHandler`Instrukcje i `RemoveHandler` umożliwiają uruchamianie i zatrzymywanie obsługi zdarzeń w dowolnym momencie podczas wykonywania programu.</span><span class="sxs-lookup"><span data-stu-id="b1a92-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="b1a92-111">Podpis `eventhandler` procedury musi być zgodny z podpisem zdarzenia `event` .</span><span class="sxs-lookup"><span data-stu-id="b1a92-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="b1a92-112">`Handles`Słowo kluczowe i `AddHandler` instrukcja umożliwiają określenie, że konkretne procedury obsługują określone zdarzenia, ale istnieją różnice.</span><span class="sxs-lookup"><span data-stu-id="b1a92-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="b1a92-113">`AddHandler`Instrukcja łączy procedury ze zdarzeniami w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b1a92-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="b1a92-114">Użyj `Handles` słowa kluczowego podczas definiowania procedury, aby określić, że obsługuje określone zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="b1a92-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="b1a92-115">Aby uzyskać więcej informacji, zobacz [Handles](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b1a92-115">For more information, see [Handles](handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1a92-116">W przypadku zdarzeń niestandardowych `AddHandler` instrukcja wywołuje `AddHandler` metodę dostępu zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="b1a92-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="b1a92-117">Aby uzyskać więcej informacji na temat zdarzeń niestandardowych, zobacz [instrukcja zdarzenia](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b1a92-117">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1a92-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="b1a92-118">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="b1a92-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b1a92-119">See also</span></span>

- [<span data-ttu-id="b1a92-120">RemoveHandler — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="b1a92-120">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="b1a92-121">Handles</span><span class="sxs-lookup"><span data-stu-id="b1a92-121">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="b1a92-122">Event — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="b1a92-122">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="b1a92-123">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="b1a92-123">Events</span></span>](../../programming-guide/language-features/events/index.md)
