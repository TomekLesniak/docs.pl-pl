---
title: IMetaDataDispenserEx::FindAssembly — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
ms.openlocfilehash: c11a4498610c3e82590a0ff9be1247173e70be76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713395"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="0ddc2-102">IMetaDataDispenserEx::FindAssembly — Metoda</span><span class="sxs-lookup"><span data-stu-id="0ddc2-102">IMetaDataDispenserEx::FindAssembly Method</span></span>

<span data-ttu-id="0ddc2-103">Ta metoda nie jest zaimplementowana.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-103">This method is not implemented.</span></span> <span data-ttu-id="0ddc2-104">Jeśli zostanie wywołana, zwraca E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ddc2-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0ddc2-105">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ddc2-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="0ddc2-106">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="0ddc2-107">podczas Nieużywane.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="0ddc2-108">podczas Nieużywane.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="0ddc2-109">podczas Nieużywane.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="0ddc2-110">podczas Zestaw, który ma zostać znaleziony.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="0ddc2-111">określoną Prosta nazwa zestawu.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0ddc2-112">podczas Rozmiar, w bajtach, z `szName` .</span><span class="sxs-lookup"><span data-stu-id="0ddc2-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="0ddc2-113">określoną Liczba znaków, które faktycznie zostały zwrócone `szName` .</span><span class="sxs-lookup"><span data-stu-id="0ddc2-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ddc2-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0ddc2-114">Requirements</span></span>  

 <span data-ttu-id="0ddc2-115">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ddc2-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ddc2-116">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0ddc2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ddc2-117">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ddc2-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ddc2-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ddc2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddc2-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0ddc2-119">See also</span></span>

- [<span data-ttu-id="0ddc2-120">IMetaDataDispenserEx — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0ddc2-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="0ddc2-121">IMetaDataDispenser — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0ddc2-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
