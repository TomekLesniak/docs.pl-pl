---
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime — Metoda
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
ms.openlocfilehash: a0b966e85bedcbef622aba2f6b181b98e0950e01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700681"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="912a7-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime — Metoda</span><span class="sxs-lookup"><span data-stu-id="912a7-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>

<span data-ttu-id="912a7-103">Pobiera łączny czas procesora, który był używany przez wszystkie wątki podczas wykonywania w bieżącej domenie aplikacji, od momentu utworzenia domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="912a7-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="912a7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="912a7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="912a7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="912a7-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="912a7-106">podczas Identyfikator żądanej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="912a7-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="912a7-107">określoną Wskaźnik do łącznego czasu procesora, który był używany przez wszystkie wątki podczas wykonywania w bieżącej domenie aplikacji od momentu utworzenia domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="912a7-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="912a7-108">Ten parametr może być `null` .</span><span class="sxs-lookup"><span data-stu-id="912a7-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="912a7-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="912a7-109">Return Value</span></span>  
  
|<span data-ttu-id="912a7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="912a7-110">HRESULT</span></span>|<span data-ttu-id="912a7-111">Opis</span><span class="sxs-lookup"><span data-stu-id="912a7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="912a7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="912a7-112">S_OK</span></span>|<span data-ttu-id="912a7-113">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="912a7-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="912a7-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="912a7-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="912a7-115">Domena aplikacji została zwolniona lub nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="912a7-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="912a7-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="912a7-116">E_FAIL</span></span>|<span data-ttu-id="912a7-117">Monitorowanie zasobów domeny aplikacji nie jest włączone.</span><span class="sxs-lookup"><span data-stu-id="912a7-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="912a7-118">-lub-</span><span class="sxs-lookup"><span data-stu-id="912a7-118">-or-</span></span><br /><br /> <span data-ttu-id="912a7-119">Wszystkie inne błędy.</span><span class="sxs-lookup"><span data-stu-id="912a7-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="912a7-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="912a7-120">Remarks</span></span>  

 <span data-ttu-id="912a7-121">Ta metoda jest niezarządzanym odpowiednikiem właściwości zarządzanej <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="912a7-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="912a7-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="912a7-122">Requirements</span></span>  

 <span data-ttu-id="912a7-123">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="912a7-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="912a7-124">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="912a7-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="912a7-125">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="912a7-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="912a7-126">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="912a7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="912a7-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="912a7-127">See also</span></span>

- [<span data-ttu-id="912a7-128">ICLRAppDomainResourceMonitor — Interfejs</span><span class="sxs-lookup"><span data-stu-id="912a7-128">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="912a7-129">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="912a7-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="912a7-130">Monitorowanie zasobów domeny aplikacji</span><span class="sxs-lookup"><span data-stu-id="912a7-130">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="912a7-131">Hosting</span><span class="sxs-lookup"><span data-stu-id="912a7-131">Hosting</span></span>](index.md)
