---
title: Nieobsługiwana funkcja
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: d4fe3d91b80197d962989cd2d3bc9bb2df6e3ffe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164158"
---
# <a name="unsupported-functionality"></a>Nieobsługiwana funkcja

W LINQ to SQL następujące funkcje SQL nie mogą być narażone na podstawie tłumaczenia istniejącego środowiska uruchomieniowego języka wspólnego (CLR) i konstrukcji .NET Framework:  
  
- `STDDEV`  
  
- `LIKE`  
  
     Chociaż `LIKE` nie jest obsługiwana za pośrednictwem bezpośredniego tłumaczenia, w klasie istnieją podobne funkcje <xref:System.Data.Linq.SqlClient.SqlMethods> . Aby uzyskać więcej informacji, zobacz <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
- `DATEDIFF`  
  
     LINQ to SQL ma ograniczoną obsługę programu `DATEDIFF` . Podobna funkcja istnieje w <xref:System.Data.Linq.SqlClient.SqlMethods> klasie.  
  
- `ROUND`  
  
     LINQ to SQL ma ograniczoną obsługę programu `ROUND` . Aby uzyskać więcej informacji, zobacz [metody System. Math](system-math-methods.md).  
  
## <a name="see-also"></a>Zobacz też

- [Typy danych i funkcje](data-types-and-functions.md)
