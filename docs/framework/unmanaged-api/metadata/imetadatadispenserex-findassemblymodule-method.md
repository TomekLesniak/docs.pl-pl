---
title: IMetaDataDispenserEx::FindAssemblyModule — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
ms.openlocfilehash: 5bc622c013e62fa9c03476cc5927133682020426
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700616"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="e9d4d-102">IMetaDataDispenserEx::FindAssemblyModule — Metoda</span><span class="sxs-lookup"><span data-stu-id="e9d4d-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>

<span data-ttu-id="e9d4d-103">Ta metoda nie jest zaimplementowana.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-103">This method is not implemented.</span></span> <span data-ttu-id="e9d4d-104">Jeśli zostanie wywołana, zwraca E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d4d-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="e9d4d-105">Syntax</span></span>  
  
```cpp  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9d4d-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="e9d4d-106">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="e9d4d-107">podczas Nieużywane.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="e9d4d-108">podczas Nieużywane.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="e9d4d-109">podczas Nieużywane.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="e9d4d-110">podczas Nazwa modułu.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="e9d4d-111">podczas Zestaw, który ma zostać znaleziony.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="e9d4d-112">określoną Prosta nazwa zestawu.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e9d4d-113">podczas Rozmiar, w bajtach, z `szName` .</span><span class="sxs-lookup"><span data-stu-id="e9d4d-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="e9d4d-114">określoną Liczba znaków, które faktycznie zostały zwrócone `szName` .</span><span class="sxs-lookup"><span data-stu-id="e9d4d-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9d4d-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e9d4d-115">Requirements</span></span>  

 <span data-ttu-id="e9d4d-116">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9d4d-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d4d-117">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9d4d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9d4d-118">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9d4d-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9d4d-119">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d4d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d4d-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e9d4d-120">See also</span></span>

- [<span data-ttu-id="e9d4d-121">IMetaDataDispenserEx — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e9d4d-121">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="e9d4d-122">IMetaDataDispenser — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e9d4d-122">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
