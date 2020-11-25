---
title: IMetaDataEmit::DefinePinvokeMap — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: b46d39ab3958227c1fca24ceb3a9934f2778aa2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719505"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="7a141-102">IMetaDataEmit::DefinePinvokeMap — Metoda</span><span class="sxs-lookup"><span data-stu-id="7a141-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>

<span data-ttu-id="7a141-103">Ustawia funkcje podpisu PInvoke metody, do której odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="7a141-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a141-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7a141-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a141-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7a141-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="7a141-106">podczas Token dla metody docelowej.</span><span class="sxs-lookup"><span data-stu-id="7a141-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="7a141-107">podczas Flagi używane przez funkcję PInvoke do wykonania mapowania.</span><span class="sxs-lookup"><span data-stu-id="7a141-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="7a141-108">podczas Nazwa docelowej metody eksportu w niezarządzanej bibliotece DLL.</span><span class="sxs-lookup"><span data-stu-id="7a141-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="7a141-109">podczas Token dla docelowej natywnej biblioteki DLL.</span><span class="sxs-lookup"><span data-stu-id="7a141-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a141-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7a141-110">Requirements</span></span>  

 <span data-ttu-id="7a141-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a141-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a141-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7a141-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7a141-113">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7a141-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a141-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a141-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a141-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7a141-115">See also</span></span>

- [<span data-ttu-id="7a141-116">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7a141-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7a141-117">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7a141-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
