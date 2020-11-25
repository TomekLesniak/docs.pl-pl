---
title: IMetaDataEmit::DefineUserString — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
ms.openlocfilehash: ed3c20fe8272ca3205079d26df0b7bde12e58307
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732700"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="3e549-102">IMetaDataEmit::DefineUserString — Metoda</span><span class="sxs-lookup"><span data-stu-id="3e549-102">IMetaDataEmit::DefineUserString Method</span></span>

<span data-ttu-id="3e549-103">Pobiera token metadanych dla określonego ciągu literału.</span><span class="sxs-lookup"><span data-stu-id="3e549-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e549-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3e549-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e549-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3e549-105">Parameters</span></span>  

 `szString`  
 <span data-ttu-id="3e549-106">podczas Ciąg użytkownika do zapisania.</span><span class="sxs-lookup"><span data-stu-id="3e549-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="3e549-107">podczas Liczba znaków dwubajtowych w `szString` .</span><span class="sxs-lookup"><span data-stu-id="3e549-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="3e549-108">określoną Przypisany token ciągu.</span><span class="sxs-lookup"><span data-stu-id="3e549-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e549-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3e549-109">Requirements</span></span>  

 <span data-ttu-id="3e549-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e549-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e549-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3e549-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e549-112">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e549-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e549-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e549-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e549-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3e549-114">See also</span></span>

- [<span data-ttu-id="3e549-115">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3e549-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3e549-116">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3e549-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
