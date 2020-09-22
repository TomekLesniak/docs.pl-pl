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
# <a name="removehandler-statement"></a>RemoveHandler — Instrukcja

Usuwa skojarzenie między zdarzeniem a programem obsługi zdarzeń.  
  
## <a name="syntax"></a>Składnia  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Części  
  
|Termin|Definicja|  
|---|---|  
|`event`|Nazwa obsługiwanego zdarzenia.|  
|`eventhandler`|Nazwa procedury, która obecnie obsługuje zdarzenie.|  
  
## <a name="remarks"></a>Uwagi  

 `AddHandler`Instrukcje i `RemoveHandler` umożliwiają uruchamianie i zatrzymywanie obsługi zdarzeń dla określonego zdarzenia w dowolnym momencie podczas wykonywania programu.  
  
> [!NOTE]
> W przypadku zdarzeń niestandardowych `RemoveHandler` instrukcja wywołuje `RemoveHandler` metodę dostępu zdarzenia. Aby uzyskać więcej informacji na temat zdarzeń niestandardowych, zobacz [instrukcja zdarzenia](event-statement.md).  
  
## <a name="example"></a>Przykład  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Zobacz też

- [AddHandler — Instrukcja](addhandler-statement.md)
- [Handles](handles-clause.md)
- [Event — Instrukcja](event-statement.md)
- [Zdarzenia](../../programming-guide/language-features/events/index.md)
