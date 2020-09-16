---
title: IMetaDataDispenserEx::OpenScopeOnITypeInfo — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
ms.openlocfilehash: 8e119093800ea0a0119ba25ba38cf2eaf9afe96b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540865"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="acaec-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo — Metoda</span><span class="sxs-lookup"><span data-stu-id="acaec-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="acaec-103">Ta metoda nie jest zaimplementowana.</span><span class="sxs-lookup"><span data-stu-id="acaec-103">This method is not implemented.</span></span> <span data-ttu-id="acaec-104">Jeśli zostanie wywołana, zwraca E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="acaec-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acaec-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="acaec-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acaec-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="acaec-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="acaec-107">podczas Wskaźnik do interfejsu [Metoda ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) , który zawiera informacje o typie, na którym należy otworzyć zakres.</span><span class="sxs-lookup"><span data-stu-id="acaec-107">[in] Pointer to an [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="acaec-108">podczas Flagi trybu otwartego.</span><span class="sxs-lookup"><span data-stu-id="acaec-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="acaec-109">podczas Żądany interfejs.</span><span class="sxs-lookup"><span data-stu-id="acaec-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="acaec-110">określoną Wskaźnik na wskaźnik do zwracanego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="acaec-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acaec-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="acaec-111">Requirements</span></span>  
 <span data-ttu-id="acaec-112">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acaec-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acaec-113">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="acaec-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="acaec-114">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acaec-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="acaec-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acaec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acaec-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="acaec-116">See also</span></span>

- [<span data-ttu-id="acaec-117">IMetaDataDispenserEx — Interfejs</span><span class="sxs-lookup"><span data-stu-id="acaec-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="acaec-118">IMetaDataDispenser — Interfejs</span><span class="sxs-lookup"><span data-stu-id="acaec-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
