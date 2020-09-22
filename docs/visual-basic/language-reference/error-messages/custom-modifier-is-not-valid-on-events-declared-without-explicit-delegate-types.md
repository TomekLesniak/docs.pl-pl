---
title: Modyfikator „Custom” jest nieprawidłowy w zdarzeniach deklarowanych bez jawnych typów delegowanych
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 88cdeccd7a3411b57a77116bde64d0a2cf8e537d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874541"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="959b2-102">Modyfikator „Custom” jest nieprawidłowy w zdarzeniach deklarowanych bez jawnych typów delegowanych</span><span class="sxs-lookup"><span data-stu-id="959b2-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>

<span data-ttu-id="959b2-103">W przeciwieństwie do zdarzenia nieniestandardowego, `Custom Event` Deklaracja wymaga `As` klauzuli następującej po nazwie zdarzenia, która jawnie określa typ delegata dla zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="959b2-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="959b2-104">Zdarzenia nieniestandardowe można definiować z `As` klauzulą i jawnym typem delegata lub z listą parametrów bezpośrednio po nazwie zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="959b2-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="959b2-105">**Identyfikator błędu:** BC31122</span><span class="sxs-lookup"><span data-stu-id="959b2-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="959b2-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="959b2-106">To correct this error</span></span>  
  
1. <span data-ttu-id="959b2-107">Zdefiniuj delegata z tą samą listą parametrów co zdarzenie niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="959b2-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="959b2-108">Na przykład, jeśli `Custom Event` zostało zdefiniowane przez `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` , odpowiadający mu delegat byłby następujący.</span><span class="sxs-lookup"><span data-stu-id="959b2-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. <span data-ttu-id="959b2-109">Zastąp listę parametrów zdarzenia niestandardowego `As` klauzulą określającą typ delegata.</span><span class="sxs-lookup"><span data-stu-id="959b2-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="959b2-110">Kontynuując z przykładem, `Custom Event` Deklaracja zostanie zmieniona w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="959b2-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="959b2-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="959b2-111">Example</span></span>  

 <span data-ttu-id="959b2-112">Ten przykład deklaruje `Custom Event` i określa `As` klauzulę wymaganą z typem delegata.</span><span class="sxs-lookup"><span data-stu-id="959b2-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="959b2-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="959b2-113">See also</span></span>

- [<span data-ttu-id="959b2-114">Event — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="959b2-114">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="959b2-115">Delegate — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="959b2-115">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="959b2-116">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="959b2-116">Events</span></span>](../../programming-guide/language-features/events/index.md)
