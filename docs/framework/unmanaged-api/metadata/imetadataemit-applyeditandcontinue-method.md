---
title: IMetaDataEmit::ApplyEditAndContinue — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.ApplyEditAndContinue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type:
- apiref
ms.openlocfilehash: 0cc84893c4937bf6b23eae0d63b92b3b871901dd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700577"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="999cd-102">IMetaDataEmit::ApplyEditAndContinue — Metoda</span><span class="sxs-lookup"><span data-stu-id="999cd-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>

<span data-ttu-id="999cd-103">Aktualizuje bieżący zakres zestawu zmianami wprowadzonymi w określonych metadanych.</span><span class="sxs-lookup"><span data-stu-id="999cd-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="999cd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="999cd-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="999cd-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="999cd-105">Parameters</span></span>  

 `pImport`  
 <span data-ttu-id="999cd-106">\[w \] wskaźniku do obiektu [IUnknown](/cpp/atl/iunknown) , który reprezentuje metadane różnicowe z przenośnego pliku wykonywalnego (PE).</span><span class="sxs-lookup"><span data-stu-id="999cd-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="999cd-107">Metadane różnicowe to blok metadanych, który zawiera zmiany wprowadzone w kopii rzeczywistych metadanych modułu.</span><span class="sxs-lookup"><span data-stu-id="999cd-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="999cd-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="999cd-108">Requirements</span></span>  

 <span data-ttu-id="999cd-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="999cd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="999cd-110">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="999cd-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="999cd-111">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="999cd-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="999cd-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="999cd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="999cd-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="999cd-113">See also</span></span>

- [<span data-ttu-id="999cd-114">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="999cd-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="999cd-115">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="999cd-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
