---
title: Porównanie właściwości i indeksatorów — Przewodnik programowania w języku C#
description: Porównaj, w jaki sposób indeksatory języka C# są podobne do właściwości. Z wyjątkiem różnic, reguły, które są zdefiniowane dla metod dostępu do właściwości, mają zastosowanie do metod dostępu indeksatora.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: fff20ca965e7614d26f7da32321a829d13292389
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192532"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a>Porównanie właściwości i indeksatorów (Przewodnik programowania w języku C#)

Indeksatory są podobne do właściwości. Z wyjątkiem różnic przedstawionych w poniższej tabeli, wszystkie reguły, które są zdefiniowane dla metod dostępu do właściwości stosuje się również do metod dostępu indeksatora.  
  
|Właściwość|Indeksator|  
|--------------|-------------|  
|Umożliwia wywoływanie metod w taki sposób, jakby były publicznymi elementami członkowskimi danych.|Zezwala na dostęp do elementów w wewnętrznej kolekcji obiektów przy użyciu notacji tablicy dla samego obiektu.|  
|Dostępne za pomocą prostej nazwy.|Dostępne za za poorednictwem indeksu.|  
|Może być elementem członkowskim typu static lub instance.|Musi być elementem członkowskim wystąpienia.|  
|Metoda dostępu [Get](../../language-reference/keywords/get.md) właściwości nie ma parametrów.|`get`Metoda dostępu indeksatora ma taką samą formalną listę parametrów jak indeksator.|  
|Metoda dostępu [Set](../../language-reference/keywords/set.md) właściwości zawiera parametr niejawny `value` .|`set`Metoda dostępu indeksatora ma taką samą formalną listę parametrów jak indeksator, a także parametr [Value](../../language-reference/keywords/value.md) .|  
|Obsługuje skróconą składnię z [zaimplementowanymi właściwościami](../classes-and-structs/auto-implemented-properties.md).|Obsługuje składowe wyrażeń składowanych tylko dla indeksatorów tylko do pobrania.|  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Indexers (Indeksatory)](./index.md)
- [Właściwości](../classes-and-structs/properties.md)
