---
title: ICLRErrorReportingManager::BeginCustomDump — Metoda
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
ms.openlocfilehash: 199c130d70cfbf0d383c2e0dc148ffe3dc1242d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673566"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="cae06-102">ICLRErrorReportingManager::BeginCustomDump — Metoda</span><span class="sxs-lookup"><span data-stu-id="cae06-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>

<span data-ttu-id="cae06-103">Określa konfigurację niestandardowych zrzutów sterty dla raportowania błędów.</span><span class="sxs-lookup"><span data-stu-id="cae06-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae06-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cae06-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cae06-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cae06-105">Parameters</span></span>  

 `dwFlavor`  
 <span data-ttu-id="cae06-106">podczas Wartość [ECustomDumpFlavor —](ecustomdumpflavor-enumeration.md) , która wskazuje rodzaj zrzutu sterty, na którym ma zostać skompilowany zrzut sterty niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="cae06-106">[in] A [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="cae06-107">podczas Długość `items` tablicy.</span><span class="sxs-lookup"><span data-stu-id="cae06-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="cae06-108">Jeśli `dwFlavor` nie jest DUMP_FLAVOR_Mini, `dwNumItems` powinna być równa zero.</span><span class="sxs-lookup"><span data-stu-id="cae06-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="cae06-109">podczas Tablica wystąpień [CustomDumpItem —](customdumpitem-structure.md) , określająca elementy, które mają zostać dodane do mini zrzutu.</span><span class="sxs-lookup"><span data-stu-id="cae06-109">[in] An array of [CustomDumpItem](customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="cae06-110">Jeśli `dwFlavor` nie jest DUMP_FLAVOR_Mini, `items` powinna mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="cae06-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="cae06-111">podczas Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="cae06-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cae06-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="cae06-112">Return Value</span></span>  
  
|<span data-ttu-id="cae06-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cae06-113">HRESULT</span></span>|<span data-ttu-id="cae06-114">Opis</span><span class="sxs-lookup"><span data-stu-id="cae06-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cae06-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="cae06-115">S_OK</span></span>|<span data-ttu-id="cae06-116">Metoda została pomyślnie zwrócona.</span><span class="sxs-lookup"><span data-stu-id="cae06-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="cae06-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cae06-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cae06-118">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="cae06-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cae06-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cae06-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cae06-120">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="cae06-120">The call timed out.</span></span>|  
|<span data-ttu-id="cae06-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cae06-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cae06-122">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="cae06-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cae06-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cae06-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cae06-124">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="cae06-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cae06-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cae06-125">E_FAIL</span></span>|<span data-ttu-id="cae06-126">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="cae06-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cae06-127">Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="cae06-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cae06-128">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cae06-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cae06-129">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cae06-129">Remarks</span></span>  

 <span data-ttu-id="cae06-130">`BeginCustomDump`Metoda ustawia niestandardową konfigurację zrzutu sterty.</span><span class="sxs-lookup"><span data-stu-id="cae06-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="cae06-131">Metoda [EndCustomDump —](iclrerrorreportingmanager-endcustomdump-method.md) czyści konfigurację zrzutu sterty niestandardowej i zwalnia wszystkie skojarzone Stany.</span><span class="sxs-lookup"><span data-stu-id="cae06-131">The [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="cae06-132">Powinien być wywoływany po zakończeniu niestandardowego zrzutu sterty.</span><span class="sxs-lookup"><span data-stu-id="cae06-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="cae06-133">Niepowodzenie wywołania `EndCustomDump` powoduje przeciek pamięci.</span><span class="sxs-lookup"><span data-stu-id="cae06-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cae06-134">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cae06-134">Requirements</span></span>  

 <span data-ttu-id="cae06-135">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cae06-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cae06-136">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cae06-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cae06-137">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cae06-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cae06-138">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cae06-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae06-139">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cae06-139">See also</span></span>

- [<span data-ttu-id="cae06-140">CustomDumpItem — Struktura</span><span class="sxs-lookup"><span data-stu-id="cae06-140">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="cae06-141">ECustomDumpFlavor — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="cae06-141">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="cae06-142">ICLRErrorReportingManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cae06-142">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
