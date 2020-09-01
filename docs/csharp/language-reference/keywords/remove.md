---
description: Usuń kontekstowe słowo kluczowe — odwołanie w C#
title: Usuń kontekstowe słowo kluczowe — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: a5514e72a04daa1232dbdf9a37813f09de791590
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136957"
---
# <a name="remove-c-reference"></a>remove (odwołanie w C#)

`remove`Kontekstowe słowo kluczowe jest używane do definiowania niestandardowego akcesora zdarzeń, który jest wywoływany, gdy kod klienta anulował subskrypcję ze [zdarzenia](event.md). W przypadku podania niestandardowej `remove` metody dostępu należy również podać metodę dostępu [Dodaj](add.md) .

## <a name="example"></a>Przykład

Poniższy przykład pokazuje zdarzenie z [dodaniem](add.md) niestandardowego i `remove` dostępem. Pełny przykład można znaleźć w temacie [jak zaimplementować zdarzenia interfejsu](../../programming-guide/events/how-to-implement-interface-events.md).

 [!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]

Zazwyczaj nie trzeba podawać własnych niestandardowych metod dostępu do zdarzeń. Metody dostępu, które są generowane automatycznie przez kompilator podczas deklarowania zdarzenia, są wystarczające dla większości scenariuszy.

## <a name="see-also"></a>Zobacz też

- [Zdarzenia](../../programming-guide/events/index.md)
