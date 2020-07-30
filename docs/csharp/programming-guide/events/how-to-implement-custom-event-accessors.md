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
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Jak zaimplementować niestandardowe metody dostępu do zdarzeń (Przewodnik programowania w języku C#)
Zdarzenie jest specjalnym rodzajem delegata multiemisji, który może być wywoływany z klasy, w której jest zadeklarowany. Kod klienta subskrybuje zdarzenie, podając odwołanie do metody, która powinna być wywoływana, gdy zdarzenie zostanie wyzwolone. Te metody są dodawane do listy wywołań delegata za pomocą metod dostępu do zdarzeń, które przypominają metody dostępu do właściwości, z tą różnicą, że dostęp do zdarzeń jest nazwany `add` i `remove` . W większości przypadków nie trzeba podawać niestandardowych metod dostępu do zdarzeń. Gdy w kodzie nie są dostarczane żadne niestandardowe metody dostępu do zdarzeń, kompilator doda je automatycznie. Jednak w niektórych przypadkach może być konieczne zapewnienie zachowania niestandardowego. W tym temacie pokazano, [jak zaimplementować zdarzenia interfejsu](./how-to-implement-interface-events.md).
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia sposób implementacji niestandardowych metod dostępu do zdarzeń dodawania i usuwania. Chociaż można zastąpić dowolny kod wewnątrz metod dostępu, Zalecamy zablokowanie zdarzenia przed dodaniem lub usunięciem nowej metody obsługi zdarzeń.  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a>Zobacz też

- [Zdarzenia](./index.md)
- [wydarzen](../../language-reference/keywords/event.md)
