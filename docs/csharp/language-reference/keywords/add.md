---
description: 'Dowiedz się, jak utworzyć niestandardowe metody dostępu do zdarzeń za pomocą słowa kluczowego Add w języku C #'
title: Informacje o dodawaniu do języka C#
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: 9daf635206ff9727a4bf333c123f68be812723cd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168767"
---
# <a name="add-c-reference"></a>add (odwołanie w C#)

`add`Kontekstowe słowo kluczowe jest używane do definiowania niestandardowego akcesora zdarzeń, który jest wywoływany, gdy kod klienta subskrybuje [zdarzenie](./event.md). W przypadku podania niestandardowej `add` metody dostępu należy również podać metodę dostępu [Usuń](./remove.md) .  
  
## <a name="example"></a>Przykład  

Poniższy przykład pokazuje zdarzenie, które ma metody `add` dostępu niestandardowe i [usuwania](./remove.md) . Pełny przykład można znaleźć w temacie [jak zaimplementować zdarzenia interfejsu](../../programming-guide/events/how-to-implement-interface-events.md).
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 Zazwyczaj nie trzeba podawać własnych niestandardowych metod dostępu do zdarzeń. Metody dostępu, które są generowane automatycznie przez kompilator podczas deklarowania zdarzenia, są wystarczające dla większości scenariuszy.  
  
## <a name="see-also"></a>Zobacz też

- [Zdarzenia](../../programming-guide/events/index.md)
