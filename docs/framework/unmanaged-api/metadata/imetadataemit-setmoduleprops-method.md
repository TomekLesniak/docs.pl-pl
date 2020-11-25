---
title: IMetaDataEmit::SetModuleProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: 1757662d2004dce3156182c35b37237ff91bae7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730347"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="cf9a1-102">IMetaDataEmit::SetModuleProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="cf9a1-102">IMetaDataEmit::SetModuleProps Method</span></span>

<span data-ttu-id="cf9a1-103">Aktualizuje odwołania do modułu zdefiniowanego przez poprzednie wywołanie do [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="cf9a1-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf9a1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cf9a1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf9a1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cf9a1-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="cf9a1-106">podczas Nazwa modułu w formacie Unicode.</span><span class="sxs-lookup"><span data-stu-id="cf9a1-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="cf9a1-107">Jest to tylko nazwa pliku, a nie pełna nazwa ścieżki.</span><span class="sxs-lookup"><span data-stu-id="cf9a1-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf9a1-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cf9a1-108">Requirements</span></span>  

 <span data-ttu-id="cf9a1-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf9a1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf9a1-110">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cf9a1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf9a1-111">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf9a1-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf9a1-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf9a1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf9a1-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cf9a1-113">See also</span></span>

- [<span data-ttu-id="cf9a1-114">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cf9a1-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="cf9a1-115">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cf9a1-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
