---
title: IMetaDataEmit::SetFieldProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: 0f98fb64b43822c437c39df2f3c51a222ef386b9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730399"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="e5f23-102">IMetaDataEmit::SetFieldProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="e5f23-102">IMetaDataEmit::SetFieldProps Method</span></span>

<span data-ttu-id="e5f23-103">Ustawia lub aktualizuje wartość domyślną dla pola, do którego odwołuje się określony token pola.</span><span class="sxs-lookup"><span data-stu-id="e5f23-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f23-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e5f23-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5f23-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e5f23-105">Parameters</span></span>  

 `fd`  
 <span data-ttu-id="e5f23-106">podczas Token dla pola docelowego.</span><span class="sxs-lookup"><span data-stu-id="e5f23-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="e5f23-107">podczas Atrybuty pola.</span><span class="sxs-lookup"><span data-stu-id="e5f23-107">[in] Field attributes.</span></span> <span data-ttu-id="e5f23-108">To jest maska bitów `CorFieldAttr` wartości.</span><span class="sxs-lookup"><span data-stu-id="e5f23-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="e5f23-109">podczas `ELEMENT_TYPE_` *\** Wartość stałej.</span><span class="sxs-lookup"><span data-stu-id="e5f23-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="e5f23-110">To jest `CorElementType` wartość.</span><span class="sxs-lookup"><span data-stu-id="e5f23-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="e5f23-111">Jeśli stała nie jest zdefiniowana, ustaw tę wartość na `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="e5f23-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="e5f23-112">podczas Stała wartość pola.</span><span class="sxs-lookup"><span data-stu-id="e5f23-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="e5f23-113">podczas Rozmiar, w znakach Unicode, z `pValue` .</span><span class="sxs-lookup"><span data-stu-id="e5f23-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f23-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e5f23-114">Requirements</span></span>  

 <span data-ttu-id="e5f23-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5f23-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f23-116">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e5f23-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5f23-117">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5f23-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5f23-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f23-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f23-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e5f23-119">See also</span></span>

- [<span data-ttu-id="e5f23-120">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e5f23-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e5f23-121">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e5f23-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
