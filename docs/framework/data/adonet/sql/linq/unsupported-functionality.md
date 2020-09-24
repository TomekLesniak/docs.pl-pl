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
# <a name="unsupported-functionality"></a><span data-ttu-id="0731c-102">Nieobsługiwana funkcja</span><span class="sxs-lookup"><span data-stu-id="0731c-102">Unsupported Functionality</span></span>

<span data-ttu-id="0731c-103">W LINQ to SQL następujące funkcje SQL nie mogą być narażone na podstawie tłumaczenia istniejącego środowiska uruchomieniowego języka wspólnego (CLR) i konstrukcji .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0731c-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
- `STDDEV`  
  
- `LIKE`  
  
     <span data-ttu-id="0731c-104">Chociaż `LIKE` nie jest obsługiwana za pośrednictwem bezpośredniego tłumaczenia, w klasie istnieją podobne funkcje <xref:System.Data.Linq.SqlClient.SqlMethods> .</span><span class="sxs-lookup"><span data-stu-id="0731c-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="0731c-105">Aby uzyskać więcej informacji, zobacz <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0731c-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
- `DATEDIFF`  
  
     <span data-ttu-id="0731c-106">LINQ to SQL ma ograniczoną obsługę programu `DATEDIFF` .</span><span class="sxs-lookup"><span data-stu-id="0731c-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="0731c-107">Podobna funkcja istnieje w <xref:System.Data.Linq.SqlClient.SqlMethods> klasie.</span><span class="sxs-lookup"><span data-stu-id="0731c-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
- `ROUND`  
  
     <span data-ttu-id="0731c-108">LINQ to SQL ma ograniczoną obsługę programu `ROUND` .</span><span class="sxs-lookup"><span data-stu-id="0731c-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="0731c-109">Aby uzyskać więcej informacji, zobacz [metody System. Math](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0731c-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0731c-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0731c-110">See also</span></span>

- [<span data-ttu-id="0731c-111">Typy danych i funkcje</span><span class="sxs-lookup"><span data-stu-id="0731c-111">Data Types and Functions</span></span>](data-types-and-functions.md)
