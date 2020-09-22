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
# <a name="addhandler-statement"></a>AddHandler — Instrukcja

Kojarzy zdarzenie z programem obsługi zdarzeń w czasie wykonywania.  
  
## <a name="syntax"></a>Składnia  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Części  

|||
|---|---|
|event|Nazwa zdarzenia do obsłużenia.|  
|`eventhandler`|Nazwa procedury, która obsługuje zdarzenie.|
|||
  
## <a name="remarks"></a>Uwagi  

 `AddHandler`Instrukcje i `RemoveHandler` umożliwiają uruchamianie i zatrzymywanie obsługi zdarzeń w dowolnym momencie podczas wykonywania programu.  
  
 Podpis `eventhandler` procedury musi być zgodny z podpisem zdarzenia `event` .  
  
 `Handles`Słowo kluczowe i `AddHandler` instrukcja umożliwiają określenie, że konkretne procedury obsługują określone zdarzenia, ale istnieją różnice. `AddHandler`Instrukcja łączy procedury ze zdarzeniami w czasie wykonywania. Użyj `Handles` słowa kluczowego podczas definiowania procedury, aby określić, że obsługuje określone zdarzenie. Aby uzyskać więcej informacji, zobacz [Handles](handles-clause.md).  
  
> [!NOTE]
> W przypadku zdarzeń niestandardowych `AddHandler` instrukcja wywołuje `AddHandler` metodę dostępu zdarzenia. Aby uzyskać więcej informacji na temat zdarzeń niestandardowych, zobacz [instrukcja zdarzenia](event-statement.md).  
  
## <a name="example"></a>Przykład  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Zobacz też

- [RemoveHandler — Instrukcja](removehandler-statement.md)
- [Handles](handles-clause.md)
- [Event — Instrukcja](event-statement.md)
- [Zdarzenia](../../programming-guide/language-features/events/index.md)
