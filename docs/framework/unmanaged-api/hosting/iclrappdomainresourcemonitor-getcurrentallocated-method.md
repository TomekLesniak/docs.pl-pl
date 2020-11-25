---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated — Metoda
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
ms.openlocfilehash: d3bd948dfe4a5cf97e3e3e430f551e7bc6404690
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700798"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="f8033-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated — Metoda</span><span class="sxs-lookup"><span data-stu-id="f8033-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>

<span data-ttu-id="f8033-103">Pobiera łączny rozmiar (w bajtach) wszystkich alokacji pamięci wykonanych przez domenę aplikacji od momentu utworzenia, bez odejmowania pamięci, która została zebrana jako elementy bezużyteczne.</span><span class="sxs-lookup"><span data-stu-id="f8033-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8033-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f8033-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8033-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f8033-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="f8033-106">podczas Identyfikator żądanej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f8033-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="f8033-107">określoną Wskaźnik do całkowitego rozmiaru wszystkich alokacji pamięci.</span><span class="sxs-lookup"><span data-stu-id="f8033-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8033-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f8033-108">Return Value</span></span>  

 <span data-ttu-id="f8033-109">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="f8033-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f8033-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8033-110">HRESULT</span></span>|<span data-ttu-id="f8033-111">Opis</span><span class="sxs-lookup"><span data-stu-id="f8033-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8033-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8033-112">S_OK</span></span>|<span data-ttu-id="f8033-113">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="f8033-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="f8033-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="f8033-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="f8033-115">Domena aplikacji została zwolniona lub nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="f8033-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8033-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f8033-116">Remarks</span></span>  

 <span data-ttu-id="f8033-117">Ta metoda jest niezarządzanym odpowiednikiem właściwości zarządzanej <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f8033-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8033-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f8033-118">Requirements</span></span>  

 <span data-ttu-id="f8033-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8033-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8033-120">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="f8033-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f8033-121">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f8033-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8033-122">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8033-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8033-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f8033-123">See also</span></span>

- [<span data-ttu-id="f8033-124">ICLRAppDomainResourceMonitor — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f8033-124">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="f8033-125">Monitorowanie zasobów domeny aplikacji</span><span class="sxs-lookup"><span data-stu-id="f8033-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="f8033-126">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="f8033-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="f8033-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="f8033-127">Hosting</span></span>](index.md)
