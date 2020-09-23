---
title: 'Porady: deklarowanie zdarzeń niestandardowych w celu unikania blokowania'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: a9350470836652f65532068402c78375b4c5495c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077101"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Porady: deklarowanie zdarzeń niestandardowych w celu unikania blokowania (Visual Basic)

Istnieją pewne sytuacje, w których należy pamiętać, że jedna procedura obsługi zdarzeń nie blokuje kolejnych programów obsługi zdarzeń. Zdarzenia niestandardowe umożliwiają zdarzeniom Asynchroniczne wywoływanie obsługi zdarzeń.  
  
 Domyślnie pole zapasowe magazynu dla deklaracji zdarzenia jest delegatem multiemisji, który szeregowo łączy wszystkie programy obsługi zdarzeń. Oznacza to, że jeśli jedna procedura obsługi zajmuje dużo czasu, program blokuje inne programy obsługi do momentu jego zakończenia. (Dobrze działające programy obsługi zdarzeń nigdy nie wykonują długotrwałych ani potencjalnie blokujących operacji).  
  
 Zamiast korzystać z domyślnej implementacji zdarzeń, które Visual Basic zapewnia, można użyć niestandardowego zdarzenia do wykonywania obsługi zdarzeń asynchronicznie.  
  
## <a name="example"></a>Przykład  

 W tym przykładzie `AddHandler` metoda dostępu dodaje delegata dla każdego procedury obsługi `Click` zdarzenia do wartości <xref:System.Collections.ArrayList> przechowywanej w `EventHandlerList` polu.  
  
 Gdy kod wywołuje `Click` zdarzenie, `RaiseEvent` metoda dostępu wywołuje wszystkie delegatów obsługi zdarzeń asynchronicznie za pomocą <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> metody. Ta metoda wywołuje każdy program obsługi w wątku roboczym i zwraca natychmiast, dlatego programy obsługi nie mogą blokować siebie nawzajem.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [Zdarzenia](index.md)
- [Instrukcje: deklarowanie zdarzeń niestandardowych w celu zachowywania pamięci](how-to-declare-custom-events-to-conserve-memory.md)
