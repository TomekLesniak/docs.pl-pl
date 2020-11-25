---
title: ISymUnmanagedSymbolSearchInfo — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: 95ad3cbea4269173f22e662d15772ff97f7ee900
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705452"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="8740b-102">ISymUnmanagedSymbolSearchInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8740b-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>

<span data-ttu-id="8740b-103">Dostarcza metody, które pobierają informacje o ścieżce wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="8740b-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="8740b-104">Uzyskaj ten interfejs, wywołując `QueryInterface` obiekt, który implementuje interfejs [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="8740b-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8740b-105">Metody</span><span class="sxs-lookup"><span data-stu-id="8740b-105">Methods</span></span>  
  
|<span data-ttu-id="8740b-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="8740b-106">Method</span></span>|<span data-ttu-id="8740b-107">Opis</span><span class="sxs-lookup"><span data-stu-id="8740b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8740b-108">GetHRESULT, metoda</span><span class="sxs-lookup"><span data-stu-id="8740b-108">GetHRESULT Method</span></span>](isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="8740b-109">Pobiera wartość HRESULT.</span><span class="sxs-lookup"><span data-stu-id="8740b-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="8740b-110">GetSearchPath, metoda</span><span class="sxs-lookup"><span data-stu-id="8740b-110">GetSearchPath Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="8740b-111">Pobiera ścieżkę wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="8740b-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="8740b-112">GetSearchPathLength, metoda</span><span class="sxs-lookup"><span data-stu-id="8740b-112">GetSearchPathLength Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="8740b-113">Pobiera długość ścieżki wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="8740b-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8740b-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8740b-114">Requirements</span></span>  

 <span data-ttu-id="8740b-115">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8740b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8740b-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8740b-116">See also</span></span>

- [<span data-ttu-id="8740b-117">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="8740b-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
