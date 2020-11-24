---
title: ISymUnmanagedReaderSymbolSearchInfo — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
ms.openlocfilehash: af4124aed823a0a2475a181efe3fa68e1fae0bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678392"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="70161-102">ISymUnmanagedReaderSymbolSearchInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="70161-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>

<span data-ttu-id="70161-103">Dostarcza metody, które pobierają informacje o wyszukiwaniu symboli.</span><span class="sxs-lookup"><span data-stu-id="70161-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="70161-104">Uzyskaj ten interfejs, wywołując `QueryInterface` obiekt, który implementuje interfejs [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="70161-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70161-105">Metody</span><span class="sxs-lookup"><span data-stu-id="70161-105">Methods</span></span>  
  
|<span data-ttu-id="70161-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="70161-106">Method</span></span>|<span data-ttu-id="70161-107">Opis</span><span class="sxs-lookup"><span data-stu-id="70161-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70161-108">GetSymbolSearchInfo, metoda</span><span class="sxs-lookup"><span data-stu-id="70161-108">GetSymbolSearchInfo Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="70161-109">Pobiera informacje o wyszukiwaniu symboli.</span><span class="sxs-lookup"><span data-stu-id="70161-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="70161-110">GetSymbolSearchInfoCount, metoda</span><span class="sxs-lookup"><span data-stu-id="70161-110">GetSymbolSearchInfoCount Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="70161-111">Pobiera liczbę informacji o wyszukiwaniu symboli.</span><span class="sxs-lookup"><span data-stu-id="70161-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70161-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="70161-112">Requirements</span></span>  

 <span data-ttu-id="70161-113">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="70161-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70161-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="70161-114">See also</span></span>

- [<span data-ttu-id="70161-115">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="70161-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
