---
title: Wywoływanie funkcji w zapytaniach składnika LINQ to Entities
description: Skorzystaj z poniższych artykułów, aby zobaczyć, jak klasy EntityFunctions i SqlFunctions zapewniają dostęp do funkcji kanonicznych i baz danych w ramach Entity Framework.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 8c771c93e0c3ed82f3ad550613dd855fd06b6f48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177491"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Wywoływanie funkcji w zapytaniach składnika LINQ to Entities

W tematach w tej sekcji opisano sposób wywoływania funkcji w LINQ to Entities zapytaniach.  
  
 <xref:System.Data.Objects.EntityFunctions>Klasy i <xref:System.Data.Objects.SqlClient.SqlFunctions> zapewniają dostęp do funkcji kanonicznych i baz danych w ramach Entity Framework. Aby uzyskać więcej informacji, zobacz [instrukcje: wywoływanie funkcji kanonicznych](how-to-call-canonical-functions.md) i [instrukcje: wywoływanie funkcji bazy danych](how-to-call-database-functions.md).  
  
 Proces wywoływania funkcji niestandardowej wymaga wykonania trzech podstawowych czynności:  
  
1. Zdefiniuj funkcję w modelu koncepcyjnym lub Zadeklaruj funkcję w modelu magazynu.  
  
2. Dodaj metodę do aplikacji i zamapuj ją na funkcję w modelu z <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> .  
  
3. Wywołaj funkcję w kwerendzie LINQ to Entities.  
  
 Więcej informacji znajduje się w tematach w tej sekcji.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Instrukcje: Wywoływanie funkcji kanonicznych](how-to-call-canonical-functions.md)  
  
 [Instrukcje: Wywoływanie funkcji bazy danych](how-to-call-database-functions.md)  
  
 [Instrukcje: Wywoływanie niestandardowych funkcji bazy danych](how-to-call-custom-database-functions.md)  
  
 [Instrukcje: Wywoływanie funkcji definiowanych przez model w zapytaniach](how-to-call-model-defined-functions-in-queries.md)  
  
 [Instrukcje: Wywoływanie funkcji definiowanych przez model jako metod obiektu](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>Zobacz też

- [Zapytania w składniku LINQ to Entities](queries-in-linq-to-entities.md)
- [Funkcje Canonical](canonical-functions.md)
- [Plik. edmx — Omówienie](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Instrukcje: Definiowanie funkcji niestandardowych w modelu koncepcyjnym](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
