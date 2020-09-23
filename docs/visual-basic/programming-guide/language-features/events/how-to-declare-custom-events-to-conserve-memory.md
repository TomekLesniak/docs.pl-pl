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
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Porady: deklarowanie zdarzeń niestandardowych w celu zachowywania pamięci (Visual Basic)

Istnieje kilka okoliczności, w których ważna jest niska użycie pamięci przez aplikację. Zdarzenia niestandardowe umożliwiają aplikacji używanie pamięci tylko dla zdarzeń, które obsługuje.  
  
 Domyślnie, gdy Klasa deklaruje zdarzenie, kompilator przydziela pamięć dla pola do przechowywania informacji o zdarzeniu. Jeśli klasa ma wiele nieużywanych zdarzeń, niepotrzebnie zajmują pamięć.  
  
 Zamiast korzystać z domyślnej implementacji zdarzeń, które Visual Basic zapewnia, można użyć niestandardowych zdarzeń do szczegółowego zarządzania użyciem pamięci.  
  
## <a name="example"></a>Przykład  

 W tym przykładzie Klasa używa jednego wystąpienia <xref:System.ComponentModel.EventHandlerList> klasy, przechowywanego w `Events` polu, do przechowywania informacji o zdarzeniach w użyciu. <xref:System.ComponentModel.EventHandlerList>Klasa jest zoptymalizowaną klasą listy zaprojektowaną do przechowywania delegatów.  
  
 Wszystkie zdarzenia w klasie używają pola, `Events` Aby śledzić, które metody obsługują każde zdarzenie.  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.ComponentModel.EventHandlerList>
- [Zdarzenia](index.md)
- [Instrukcje: deklarowanie zdarzeń niestandardowych w celu unikania blokowania](how-to-declare-custom-events-to-avoid-blocking.md)
