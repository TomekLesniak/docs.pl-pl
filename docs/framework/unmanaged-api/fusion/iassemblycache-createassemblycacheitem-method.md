---
title: IAssemblyCache::CreateAssemblyCacheItem — Metoda
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
ms.openlocfilehash: b417377ea1d0746e563490d87cc9a988e857d943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697041"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="780e0-102">IAssemblyCache::CreateAssemblyCacheItem — Metoda</span><span class="sxs-lookup"><span data-stu-id="780e0-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>

<span data-ttu-id="780e0-103">Pobiera odwołanie do nowego obiektu [IAssemblyCacheItem](iassemblycacheitem-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="780e0-103">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="780e0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="780e0-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="780e0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="780e0-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="780e0-106">podczas Flagi zdefiniowane w pliku Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="780e0-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="780e0-107">Obsługiwane są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="780e0-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="780e0-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="780e0-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="780e0-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="780e0-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="780e0-110">podczas Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="780e0-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="780e0-111">`pvReserved` musi być odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="780e0-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="780e0-112">określoną Zwrócony `IAssemblyCacheItem` wskaźnik.</span><span class="sxs-lookup"><span data-stu-id="780e0-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="780e0-113">[w, opcjonalnie] Niekanoniczne, pary rozdzielane przecinkami `name=value` .</span><span class="sxs-lookup"><span data-stu-id="780e0-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="780e0-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="780e0-114">Requirements</span></span>  

 <span data-ttu-id="780e0-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="780e0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="780e0-116">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="780e0-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="780e0-117">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="780e0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="780e0-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="780e0-118">See also</span></span>

- [<span data-ttu-id="780e0-119">IAssemblyCache — Interfejs</span><span class="sxs-lookup"><span data-stu-id="780e0-119">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="780e0-120">IAssemblyCacheItem — Interfejs</span><span class="sxs-lookup"><span data-stu-id="780e0-120">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
