---
title: ISymUnmanagedSourceServerModule — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
ms.openlocfilehash: 5e438c75a29984e9200dc240f389f079a4eecfd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733957"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="f9174-102">ISymUnmanagedSourceServerModule — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f9174-102">ISymUnmanagedSourceServerModule Interface</span></span>

<span data-ttu-id="f9174-103">Zapewnia dane serwera źródłowego dla modułu.</span><span class="sxs-lookup"><span data-stu-id="f9174-103">Provides source server data for a module.</span></span> <span data-ttu-id="f9174-104">Uzyskaj ten interfejs, wywołując `QueryInterface` obiekt, który implementuje interfejs [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f9174-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9174-105">Metody</span><span class="sxs-lookup"><span data-stu-id="f9174-105">Methods</span></span>  
  
|<span data-ttu-id="f9174-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="f9174-106">Method</span></span>|<span data-ttu-id="f9174-107">Opis</span><span class="sxs-lookup"><span data-stu-id="f9174-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f9174-108">GetSourceServerData, metoda</span><span class="sxs-lookup"><span data-stu-id="f9174-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="f9174-109">Zwraca dane serwera źródłowego dla modułu.</span><span class="sxs-lookup"><span data-stu-id="f9174-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9174-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f9174-110">Requirements</span></span>  

 <span data-ttu-id="f9174-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f9174-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9174-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f9174-112">See also</span></span>

- [<span data-ttu-id="f9174-113">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="f9174-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
