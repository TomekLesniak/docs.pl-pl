---
title: Rozwiązywanie problemów związanych z odziedziczonymi programami obsługi zdarzeń
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: d228e916e45054bc088aa633afd9d591e592210d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058004"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Rozwiązywanie problemów związanych z odziedziczonymi programami obsługi zdarzeń w Visual Basic

W tym temacie wymieniono typowe problemy związane z obsługą zdarzeń w składnikach dziedziczonych.  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Kod w obsłudze zdarzeń jest wykonywany dwukrotnie dla każdego wywołania  
  
- Dziedziczona procedura obsługi zdarzeń nie może zawierać klauzuli [Handles](../../../language-reference/statements/handles-clause.md) . Metoda w klasie bazowej jest już skojarzona ze zdarzeniem i zostanie odpowiednio wyzwolona. Usuń `Handles` klauzulę z dziedziczonej metody.  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- Jeśli dziedziczona Metoda nie ma `Handles` słowa kluczowego, sprawdź, czy Twój kod nie zawiera dodatkowej [instrukcji AddHandler](../../../language-reference/statements/addhandler-statement.md) ani żadnych dodatkowych metod, które obsługują to samo zdarzenie.  
  
## <a name="see-also"></a>Zobacz także

- [Zdarzenia](index.md)
