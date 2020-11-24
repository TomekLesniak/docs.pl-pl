---
title: IMetaDataEmit::SaveToMemory — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
ms.openlocfilehash: 1cd5e34d6afefab2fda7e20d4bf73b373ad42787
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688597"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="b71ab-102">IMetaDataEmit::SaveToMemory — Metoda</span><span class="sxs-lookup"><span data-stu-id="b71ab-102">IMetaDataEmit::SaveToMemory Method</span></span>

<span data-ttu-id="b71ab-103">Zapisuje wszystkie metadane w bieżącym zakresie do określonego obszaru pamięci.</span><span class="sxs-lookup"><span data-stu-id="b71ab-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b71ab-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b71ab-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b71ab-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b71ab-105">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="b71ab-106">określoną Adres, pod którym należy zacząć pisać metadane.</span><span class="sxs-lookup"><span data-stu-id="b71ab-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="b71ab-107">podczas Rozmiar przydzieloną pamięci (w bajtach).</span><span class="sxs-lookup"><span data-stu-id="b71ab-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b71ab-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b71ab-108">Requirements</span></span>  

 <span data-ttu-id="b71ab-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b71ab-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b71ab-110">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b71ab-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b71ab-111">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b71ab-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b71ab-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b71ab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b71ab-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b71ab-113">See also</span></span>

- [<span data-ttu-id="b71ab-114">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b71ab-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b71ab-115">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b71ab-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
