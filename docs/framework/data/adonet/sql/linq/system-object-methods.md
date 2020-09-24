---
title: System.Object, metody
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: d2b96ca9e7bedd0e0438b47698d4b963844c92f3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155643"
---
# <a name="systemobject-methods"></a>System.Object, metody

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] obsługuje następujące <xref:System.Object> metody.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Program nie obsługuje następujących <xref:System.Object> metod.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> w przypadku typów binarnych `BINARY` , takich jak, `VARBINARY` , `IMAGE` i `TIMESTAMP` .||  
  
## <a name="differences-from-net"></a>Różnice od platformy .NET  

 Dane wyjściowe <xref:System.Object.ToString?displayProperty=nameWithType> dla elementu Double używają języka SQL `CONVERT` (nvarchar (30), @x , 2) na serwerze SQL. W tym przypadku SQL zawsze używa 16 cyfr i notacji wykładniczej (na przykład "0.000000000000000 e + 000" dla 0). W związku z tym <xref:System.Object.ToString?displayProperty=nameWithType> Konwersja nie produkuje tego samego ciągu co <xref:System.Convert.ToString%2A?displayProperty=nameWithType> w .NET Framework.  
  
## <a name="see-also"></a>Zobacz też

- [Typy danych i funkcje](data-types-and-functions.md)
