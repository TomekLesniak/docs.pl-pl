---
title: IMetaDataEmit::SetRVA — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: df9dc1a36a9adcef3f93a9929565cef117e84d75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704230"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="9e06b-102">IMetaDataEmit::SetRVA — Metoda</span><span class="sxs-lookup"><span data-stu-id="9e06b-102">IMetaDataEmit::SetRVA Method</span></span>

<span data-ttu-id="9e06b-103">Ustawia względny adres wirtualny określonej metody.</span><span class="sxs-lookup"><span data-stu-id="9e06b-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e06b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9e06b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e06b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9e06b-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="9e06b-106">podczas Token dla docelowej metody lub implementacji metody.</span><span class="sxs-lookup"><span data-stu-id="9e06b-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="9e06b-107">podczas Adres kodu lub obszaru danych.</span><span class="sxs-lookup"><span data-stu-id="9e06b-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e06b-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9e06b-108">Requirements</span></span>  

 <span data-ttu-id="9e06b-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e06b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e06b-110">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9e06b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e06b-111">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9e06b-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e06b-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e06b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e06b-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9e06b-113">See also</span></span>

- [<span data-ttu-id="9e06b-114">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9e06b-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9e06b-115">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9e06b-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
