---
title: ICLRRuntimeInfo::GetInterface — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
ms.openlocfilehash: 192163ed8af680e39f7f3a03aee3f46546bc7450
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732076"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="1b599-102">ICLRRuntimeInfo::GetInterface — Metoda</span><span class="sxs-lookup"><span data-stu-id="1b599-102">ICLRRuntimeInfo::GetInterface Method</span></span>

<span data-ttu-id="1b599-103">Ładuje środowisko CLR do bieżącego procesu i zwraca wskaźniki interfejsu środowiska uruchomieniowego, takie jak [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md)i [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1b599-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md), and [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="1b599-104">Ta metoda zastępuje wszystkie `CorBindTo` \* funkcje w sekcji [przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="1b599-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b599-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="1b599-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b599-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="1b599-106">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="1b599-107">podczas Interfejs CLSID dla klasy coclass.</span><span class="sxs-lookup"><span data-stu-id="1b599-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="1b599-108">podczas Identyfikator IID żądanego `rclsid` interfejsu.</span><span class="sxs-lookup"><span data-stu-id="1b599-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="1b599-109">określoną Wskaźnik do zapytania do interfejsu.</span><span class="sxs-lookup"><span data-stu-id="1b599-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b599-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="1b599-110">Return Value</span></span>  

 <span data-ttu-id="1b599-111">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="1b599-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1b599-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b599-112">HRESULT</span></span>|<span data-ttu-id="1b599-113">Opis</span><span class="sxs-lookup"><span data-stu-id="1b599-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b599-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b599-114">S_OK</span></span>|<span data-ttu-id="1b599-115">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="1b599-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="1b599-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1b599-116">E_POINTER</span></span>|<span data-ttu-id="1b599-117">`ppUnk` ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="1b599-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="1b599-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1b599-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1b599-119">Za mało dostępnej pamięci, aby obsłużyć żądanie.</span><span class="sxs-lookup"><span data-stu-id="1b599-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="1b599-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="1b599-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="1b599-121">Inne środowisko uruchomieniowe zostało już powiązane ze starszymi zasadami aktywacji środowiska CLR w wersji 2.</span><span class="sxs-lookup"><span data-stu-id="1b599-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b599-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1b599-122">Remarks</span></span>  

 <span data-ttu-id="1b599-123">Ta metoda powoduje załadowanie środowiska CLR, ale nie jego inicjalizację.</span><span class="sxs-lookup"><span data-stu-id="1b599-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="1b599-124">W poniższej tabeli przedstawiono obsługiwane kombinacje dla programów `rclsid` i `riid` .</span><span class="sxs-lookup"><span data-stu-id="1b599-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="1b599-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="1b599-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="1b599-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="1b599-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="1b599-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="1b599-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="1b599-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="1b599-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="1b599-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="1b599-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="1b599-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="1b599-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="1b599-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="1b599-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="1b599-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="1b599-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="1b599-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="1b599-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="1b599-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="1b599-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="1b599-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="1b599-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="1b599-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="1b599-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="1b599-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="1b599-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="1b599-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="1b599-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b599-139">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1b599-139">Requirements</span></span>  

 <span data-ttu-id="1b599-140">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b599-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b599-141">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="1b599-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1b599-142">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b599-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b599-143">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b599-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b599-144">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1b599-144">See also</span></span>

- [<span data-ttu-id="1b599-145">ICLRRuntimeInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1b599-145">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="1b599-146">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="1b599-146">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="1b599-147">Hosting</span><span class="sxs-lookup"><span data-stu-id="1b599-147">Hosting</span></span>](index.md)
