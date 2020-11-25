---
title: IMetaDataEmit2::SaveDeltaToMemory — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: a4dbe090987248ef77ce371b5bc6fb42d898f726
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705413"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="a6e78-102">IMetaDataEmit2::SaveDeltaToMemory — Metoda</span><span class="sxs-lookup"><span data-stu-id="a6e78-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>

<span data-ttu-id="a6e78-103">Zapisuje zmiany z bieżącej sesji edycji i kontynuowania w pamięci.</span><span class="sxs-lookup"><span data-stu-id="a6e78-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e78-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a6e78-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6e78-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a6e78-105">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="a6e78-106">określoną Adres, pod którym rozpocznie się zapisywanie różnic metadanych.</span><span class="sxs-lookup"><span data-stu-id="a6e78-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="a6e78-107">podczas Rozmiar zmian.</span><span class="sxs-lookup"><span data-stu-id="a6e78-107">[in] The size of the changes.</span></span> <span data-ttu-id="a6e78-108">Aby określić rozmiar, użyj [IMetaDataEmit2:: GetDeltaSaveSize —](imetadataemit2-getdeltasavesize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a6e78-108">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6e78-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a6e78-109">Requirements</span></span>  

 <span data-ttu-id="a6e78-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6e78-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e78-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a6e78-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6e78-112">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6e78-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6e78-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e78-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e78-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a6e78-114">See also</span></span>

- [<span data-ttu-id="a6e78-115">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a6e78-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="a6e78-116">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a6e78-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
