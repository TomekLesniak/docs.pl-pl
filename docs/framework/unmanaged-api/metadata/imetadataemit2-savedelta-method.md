---
title: IMetaDataEmit2::SaveDelta — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
ms.openlocfilehash: ab2f30c485a755d4788926c13c2608e55a716c5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704269"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="9e388-102">IMetaDataEmit2::SaveDelta — Metoda</span><span class="sxs-lookup"><span data-stu-id="9e388-102">IMetaDataEmit2::SaveDelta Method</span></span>

<span data-ttu-id="9e388-103">Zapisuje zmiany z bieżącej sesji Edit-and-Continue do określonego pliku.</span><span class="sxs-lookup"><span data-stu-id="9e388-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e388-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9e388-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e388-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9e388-105">Parameters</span></span>  

 `szFile`  
 <span data-ttu-id="9e388-106">podczas Nazwa pliku, w którym mają zostać zapisane zmiany.</span><span class="sxs-lookup"><span data-stu-id="9e388-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="9e388-107">podczas Rezerwacj.</span><span class="sxs-lookup"><span data-stu-id="9e388-107">[in] Reserved.</span></span> <span data-ttu-id="9e388-108">Musi być równa zero.</span><span class="sxs-lookup"><span data-stu-id="9e388-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e388-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9e388-109">Requirements</span></span>  

 <span data-ttu-id="9e388-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e388-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e388-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9e388-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e388-112">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9e388-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9e388-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e388-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e388-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9e388-114">See also</span></span>

- [<span data-ttu-id="9e388-115">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9e388-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="9e388-116">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9e388-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
