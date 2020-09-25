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
# <a name="spatial-functions"></a><span data-ttu-id="01102-102">Funkcje przestrzenne</span><span class="sxs-lookup"><span data-stu-id="01102-102">Spatial Functions</span></span>

<span data-ttu-id="01102-103">Nie ma formatu literału dla typów przestrzennych.</span><span class="sxs-lookup"><span data-stu-id="01102-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="01102-104">Można jednak używać kanonicznych funkcji Entity Framework, które są wywoływane za pomocą ciągów w formacie dobrze znanego tekstu.</span><span class="sxs-lookup"><span data-stu-id="01102-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="01102-105">Na przykład następujące wywołanie funkcji tworzy punkt geometrii:</span><span class="sxs-lookup"><span data-stu-id="01102-105">For example, the following function call creates a geometry point:</span></span>  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="01102-106"><xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions>Metody mają wszystkie Entity Frameworkowe metody kanoniczne przestrzenne.</span><span class="sxs-lookup"><span data-stu-id="01102-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="01102-107">Kliknij metodę zainteresowania, aby zobaczyć, jakie parametry mają być przenoszone do funkcji.</span><span class="sxs-lookup"><span data-stu-id="01102-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
