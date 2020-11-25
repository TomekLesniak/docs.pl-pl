---
title: IMetaDataImport::GetModuleFromScope — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
ms.openlocfilehash: 2eddd7a80c2b9c1b71f3e7fc5b1e4686ba11bccd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733168"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="fa37c-102">IMetaDataImport::GetModuleFromScope — Metoda</span><span class="sxs-lookup"><span data-stu-id="fa37c-102">IMetaDataImport::GetModuleFromScope Method</span></span>

<span data-ttu-id="fa37c-103">Pobiera token metadanych dla modułu, do którego odwołuje się bieżący zakres metadanych.</span><span class="sxs-lookup"><span data-stu-id="fa37c-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa37c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fa37c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa37c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="fa37c-105">Parameters</span></span>  

 `pmd`  
 <span data-ttu-id="fa37c-106">określoną Wskaźnik do tokenu reprezentującego moduł, do którego odwołuje się bieżący zakres metadanych.</span><span class="sxs-lookup"><span data-stu-id="fa37c-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa37c-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fa37c-107">Requirements</span></span>  

 <span data-ttu-id="fa37c-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa37c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa37c-109">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fa37c-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa37c-110">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa37c-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa37c-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa37c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa37c-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fa37c-112">See also</span></span>

- [<span data-ttu-id="fa37c-113">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fa37c-113">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="fa37c-114">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fa37c-114">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
