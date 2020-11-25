---
title: ISymUnmanagedDispose — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose
helpviewer_keywords:
- ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type:
- apiref
ms.openlocfilehash: 932e76e73d5d40b36abcb17d8a53e6745927d873
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719609"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="8e68f-102">ISymUnmanagedDispose — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8e68f-102">ISymUnmanagedDispose Interface</span></span>

<span data-ttu-id="8e68f-103">Usuwa niezarządzane zasoby.</span><span class="sxs-lookup"><span data-stu-id="8e68f-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e68f-104">Metody</span><span class="sxs-lookup"><span data-stu-id="8e68f-104">Methods</span></span>  
  
|<span data-ttu-id="8e68f-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="8e68f-105">Method</span></span>|<span data-ttu-id="8e68f-106">Opis</span><span class="sxs-lookup"><span data-stu-id="8e68f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e68f-107">Destroy, metoda</span><span class="sxs-lookup"><span data-stu-id="8e68f-107">Destroy Method</span></span>](isymunmanageddispose-destroy-method.md)|<span data-ttu-id="8e68f-108">Powoduje, że obiekt źródłowy zwolni wszystkie odwołania wewnętrzne i zwróci niepowodzenie dla każdego kolejnego wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="8e68f-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e68f-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8e68f-109">Requirements</span></span>  

 <span data-ttu-id="8e68f-110">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8e68f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e68f-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8e68f-111">See also</span></span>

- [<span data-ttu-id="8e68f-112">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="8e68f-112">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
