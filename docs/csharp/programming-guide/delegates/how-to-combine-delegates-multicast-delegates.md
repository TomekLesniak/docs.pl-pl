---
title: Jak łączyć delegatów (delegatów multiemisji) — Przewodnik programowania w języku C#
description: Dowiedz się, jak połączyć delegatów, aby utworzyć delegatów multiemisji. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 3e86c8ed4b7b091ee8c75930d427c22aa5bc0c52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185954"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a>Łączenie obiektów delegowanych (obiekty delegowane multiemisji) (Przewodnik programowania w języku C#)

W tym przykładzie pokazano, jak utworzyć delegatów multiemisji. Przydatna właściwość obiektów [delegatów](../../language-reference/builtin-types/reference-types.md) polega na tym, że wiele obiektów może być przypisanych do jednego wystąpienia delegata przy użyciu `+` operatora. Delegat multiemisji zawiera listę przypisanych delegatów. Gdy obiekt delegowany multiemisji jest wywoływany, wywołuje delegatów z listy w kolejności. Łączyć można tylko Delegaty tego samego typu.  
  
 `-`Operatora można użyć do usunięcia delegata składnika z delegata multiemisji.  
  
## <a name="example"></a>Przykład  

 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.MulticastDelegate>
- [Przewodnik programowania w języku C#](../index.md)
- [Zdarzenia](../events/index.md)
