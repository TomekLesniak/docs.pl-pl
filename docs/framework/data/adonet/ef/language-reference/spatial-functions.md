---
title: Funkcje przestrzenne
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 7d0979b5166c847244cbeec97acf4fa4f745a259
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169586"
---
# <a name="spatial-functions"></a>Funkcje przestrzenne

Nie ma formatu literału dla typów przestrzennych. Można jednak używać kanonicznych funkcji Entity Framework, które są wywoływane za pomocą ciągów w formacie dobrze znanego tekstu. Na przykład następujące wywołanie funkcji tworzy punkt geometrii:  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions>Metody mają wszystkie Entity Frameworkowe metody kanoniczne przestrzenne. Kliknij metodę zainteresowania, aby zobaczyć, jakie parametry mają być przenoszone do funkcji.
