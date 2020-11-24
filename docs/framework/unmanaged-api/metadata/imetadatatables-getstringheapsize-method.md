---
title: IMetaDataTables::GetStringHeapSize — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
ms.openlocfilehash: e3f6afaa79b7b299fa374c8220f5c2c3ad545ac9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672568"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="7a528-102">IMetaDataTables::GetStringHeapSize — Metoda</span><span class="sxs-lookup"><span data-stu-id="7a528-102">IMetaDataTables::GetStringHeapSize Method</span></span>

<span data-ttu-id="7a528-103">Pobiera rozmiar sterty ciągu w bajtach.</span><span class="sxs-lookup"><span data-stu-id="7a528-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a528-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7a528-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a528-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7a528-105">Parameters</span></span>  

 `pcbStrings`  
 <span data-ttu-id="7a528-106">określoną Wskaźnik do rozmiaru, w bajtach, sterty ciągu.</span><span class="sxs-lookup"><span data-stu-id="7a528-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a528-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7a528-107">Requirements</span></span>  

 <span data-ttu-id="7a528-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a528-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a528-109">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7a528-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7a528-110">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7a528-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a528-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a528-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a528-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7a528-112">See also</span></span>

- [<span data-ttu-id="7a528-113">IMetaDataTables — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7a528-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="7a528-114">IMetaDataTables2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7a528-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
