---
title: ISymUnmanagedScope2 — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 40c437e109eaa4352a83c5566185593cbc6b0eba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725836"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="07365-102">ISymUnmanagedScope2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="07365-102">ISymUnmanagedScope2 Interface</span></span>

<span data-ttu-id="07365-103">Reprezentuje zakres leksykalny w ramach metody.</span><span class="sxs-lookup"><span data-stu-id="07365-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="07365-104">Ten interfejs rozszerza interfejs [ISymUnmanagedScope](isymunmanagedscope-interface.md) z metodami, które pobierają informacje o stałych zdefiniowanych w zakresie.</span><span class="sxs-lookup"><span data-stu-id="07365-104">This interface extends the [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07365-105">Metody</span><span class="sxs-lookup"><span data-stu-id="07365-105">Methods</span></span>  
  
|<span data-ttu-id="07365-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="07365-106">Method</span></span>|<span data-ttu-id="07365-107">Opis</span><span class="sxs-lookup"><span data-stu-id="07365-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07365-108">GetConstantCount, metoda</span><span class="sxs-lookup"><span data-stu-id="07365-108">GetConstantCount Method</span></span>](isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="07365-109">Pobiera liczbę stałych zdefiniowanych w tym zakresie.</span><span class="sxs-lookup"><span data-stu-id="07365-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="07365-110">GetConstants, metoda</span><span class="sxs-lookup"><span data-stu-id="07365-110">GetConstants Method</span></span>](isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="07365-111">Pobiera stałe lokalne zdefiniowane w tym zakresie.</span><span class="sxs-lookup"><span data-stu-id="07365-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07365-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="07365-112">Requirements</span></span>  

 <span data-ttu-id="07365-113">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="07365-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07365-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="07365-114">See also</span></span>

- [<span data-ttu-id="07365-115">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="07365-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="07365-116">ISymUnmanagedScope — Interfejs</span><span class="sxs-lookup"><span data-stu-id="07365-116">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
