---
title: _CorImageUnloading — Funkcja
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
ms.openlocfilehash: a8326f95286ef05dd370797a531417f81ed5c65b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723158"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="9c227-102">_CorImageUnloading — Funkcja</span><span class="sxs-lookup"><span data-stu-id="9c227-102">_CorImageUnloading Function</span></span>

<span data-ttu-id="9c227-103">Powiadamia moduł ładujący, gdy obrazy modułu zarządzanego są zwolnione.</span><span class="sxs-lookup"><span data-stu-id="9c227-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="9c227-104">Ta funkcja nie jest zaimplementowana.</span><span class="sxs-lookup"><span data-stu-id="9c227-104">This function is not implemented.</span></span> <span data-ttu-id="9c227-105">Jeśli zostanie wywołana, zwraca E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="9c227-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c227-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="9c227-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c227-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="9c227-107">Parameters</span></span>  

 `ImageBase`  
 <span data-ttu-id="9c227-108">podczas Wskaźnik do lokalizacji początkowej obrazu do zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="9c227-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c227-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9c227-109">Requirements</span></span>  

 <span data-ttu-id="9c227-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c227-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c227-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9c227-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c227-112">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9c227-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9c227-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c227-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c227-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9c227-114">See also</span></span>

- [<span data-ttu-id="9c227-115">Statyczne funkcje globalne metadanych</span><span class="sxs-lookup"><span data-stu-id="9c227-115">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
