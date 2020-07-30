---
title: Porównanie właściwości i indeksatorów — Przewodnik programowania w języku C#
description: Porównaj, w jaki sposób indeksatory języka C# są podobne do właściwości. Z wyjątkiem różnic, reguły, które są zdefiniowane dla metod dostępu do właściwości, mają zastosowanie do metod dostępu indeksatora.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: b83ce3db3d4b53fb7bcc5f3b3cd603a375d5d473
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299178"
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
