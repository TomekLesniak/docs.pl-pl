---
title: 'Porady: obsługa wielu zdarzeń przy użyciu właściwości zdarzenia'
description: Dowiedz się, jak obsługiwać wiele zdarzeń przy użyciu właściwości zdarzenia. Zdefiniuj kolekcje delegatów, klucze zdarzeń, & właściwości zdarzenia. Zaimplementuj Dodawanie & usuwanie metod dostępu.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET]
- multiple events [.NET]
- event handling [.NET], with multiple events
- events [.NET], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: c62073e26ff0831bb582c9e64c16b7ec7c05b26e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828378"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a>Porady: obsługa wielu zdarzeń przy użyciu właściwości zdarzenia
Aby użyć właściwości zdarzeń należy zdefiniować właściwości zdarzenia w klasie, która wywołuje zdarzenia, a następnie ustawić delegatów dla właściwości zdarzenia w klasach, które obsługują zdarzenia. Aby zaimplementować w klasie wiele właściwości zdarzeń, klasa musi wewnętrznie przechowywać i zachowywać zdefiniowanego delegata dla każdego zdarzenia. Typowym podejściem jest implementacja kolekcji delegata, która jest indeksowana przy użyciu klucza zdarzenia.  
  
 Aby przechowywać delegatów dla każdego zdarzenia, można użyć klasy <xref:System.ComponentModel.EventHandlerList> lub zaimplementować własną kolekcję. Klasa kolekcji musi dostarczać metody do ustawiania, uzyskiwania dostępu i pobierania delegata obsługi zdarzeń opartego na kluczu zdarzeń. Na przykład można użyć klasy <xref:System.Collections.Hashtable> lub pochodnej niestandardowej klasy na podstawie klasy <xref:System.Collections.DictionaryBase>. Szczegóły implementacji kolekcji delegata nie muszą być udostępniane poza klasą.  
  
 Każda właściwość zdarzenia w klasie definiuje metody dodawania i usuwania akcesora. Dodanie akcesora do właściwości zdarzenia dodaje wystąpienie delegata wejściowego do kolekcji delegata. Usunięcie akcesora właściwości zdarzenia usuwa wystąpienie delegata wejściowego z kolekcji delegata. Akcesory właściwości zdarzenia używają wstępnie zdefiniowanego klucza dla właściwości zdarzenia do dodawania i usuwania wystąpień z kolekcji delegata.  
  
### <a name="to-handle-multiple-events-using-event-properties"></a>Do obsługi wielu zdarzeń przy użyciu właściwości zdarzenia  
  
1. Zdefiniuj kolekcje delegata w klasie, która wywołuje zdarzenia.  
  
2. Zdefiniuj klucz dla każdego zdarzenia.  
  
3. Zdefiniuj właściwości zdarzenia w klasie, która wywołuje zdarzenia.  
  
4. Użyj kolekcji delegata do implementacji metod dodawania i usuwania akcesora dla właściwości zdarzenia.  
  
5. Użyj publicznych zdarzeń właściwości, aby dodawać i usuwać delegatów obsługi zdarzeń w klasach, które obsługują zdarzenia.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład napisany w języku C# implementuje właściwości zdarzenia `MouseDown` i `MouseUp`, z wykorzystaniem <xref:System.ComponentModel.EventHandlerList> do przechowywania każdego zdarzenia delegata. Słowa kluczowe w konstrukcji właściwości zdarzenia są pogrubione.  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [Zdarzenia](index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [Instrukcje: deklarowanie zdarzeń niestandardowych w celu zachowywania pamięci](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
