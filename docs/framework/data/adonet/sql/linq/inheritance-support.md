---
title: Obsługa dziedziczenia
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 7673e69458d5c1af854747c43ba463332a9cd588
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158256"
---
# <a name="inheritance-support"></a>Obsługa dziedziczenia

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] obsługuje *Mapowanie pojedynczej tabeli*. Innymi słowy, pełna Hierarchia dziedziczenia jest przechowywana w pojedynczej tabeli bazy danych. Tabela zawiera spłaszczoną Unię wszystkich możliwych kolumn danych dla całej hierarchii. (Unia jest wynikiem łączenia dwóch tabel w jedną tabelę, w której znajdują się wiersze, które znajdowały się w jednej z oryginalnych tabel). Każdy wiersz ma wartości null w kolumnach, które nie mają zastosowania do typu wystąpienia reprezentowanego przez wiersz.  
  
 Strategia mapowania jednej tabeli jest najprostszą reprezentacją dziedziczenia i zapewnia dobrą charakterystykę wydajności dla wielu różnych kategorii zapytań.  
  
 Aby zaimplementować to mapowanie w programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , należy określić atrybuty i właściwości atrybutów w klasie głównej hierarchii dziedziczenia. Aby uzyskać więcej informacji, zobacz [How to: map dziedziczenia hierarchii](how-to-map-inheritance-hierarchies.md).  
  
 Deweloperzy korzystający z programu Visual Studio mogą również używać Object Relational Designer do mapowania hierarchii dziedziczenia.  
  
## <a name="see-also"></a>Zobacz też

- [Informacje uzupełniające](background-information.md)
