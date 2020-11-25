---
title: IMetaDataEmit::SetMethodImplFlags — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
ms.openlocfilehash: 486d545413337f6696bd9f21c516466fc3747256
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730360"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="fa9f0-102">IMetaDataEmit::SetMethodImplFlags — Metoda</span><span class="sxs-lookup"><span data-stu-id="fa9f0-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>

<span data-ttu-id="fa9f0-103">Ustawia lub aktualizuje sygnaturę metadanych dziedziczonej metody, do której odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="fa9f0-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa9f0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fa9f0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa9f0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="fa9f0-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="fa9f0-106">podczas Token dla metody, która ma zostać zmieniona.</span><span class="sxs-lookup"><span data-stu-id="fa9f0-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="fa9f0-107">podczas Kombinacja wartości wyliczenia [CorMethodImpl —](cormethodimpl-enumeration.md) , która określa funkcje implementacji metody.</span><span class="sxs-lookup"><span data-stu-id="fa9f0-107">[in] A combination of the values of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa9f0-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fa9f0-108">Requirements</span></span>  

 <span data-ttu-id="fa9f0-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa9f0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa9f0-110">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fa9f0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa9f0-111">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa9f0-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa9f0-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa9f0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa9f0-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fa9f0-113">See also</span></span>

- [<span data-ttu-id="fa9f0-114">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fa9f0-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fa9f0-115">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fa9f0-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
