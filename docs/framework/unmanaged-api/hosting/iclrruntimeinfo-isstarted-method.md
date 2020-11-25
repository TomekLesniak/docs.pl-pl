---
title: ICLRRuntimeInfo::IsStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 1dfeb6101a6b8e33ab2fe35f318087d7f1834b6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714890"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="a1f35-102">ICLRRuntimeInfo::IsStarted — Metoda</span><span class="sxs-lookup"><span data-stu-id="a1f35-102">ICLRRuntimeInfo::IsStarted Method</span></span>

<span data-ttu-id="a1f35-103">Wskazuje, czy środowisko uruchomieniowe zostało uruchomione (czyli czy [Metoda ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) została wywołana i została zakończona pomyślnie).</span><span class="sxs-lookup"><span data-stu-id="a1f35-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f35-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a1f35-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1f35-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a1f35-105">Parameters</span></span>  

 `pbStarted`  
 <span data-ttu-id="a1f35-106">[out] `true` w przypadku uruchomienia tego środowiska uruchomieniowego; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="a1f35-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="a1f35-107">określoną Zwraca flagi, które zostały użyte do uruchomienia środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="a1f35-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1f35-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a1f35-108">Return Value</span></span>  

 <span data-ttu-id="a1f35-109">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="a1f35-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a1f35-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1f35-110">HRESULT</span></span>|<span data-ttu-id="a1f35-111">Opis</span><span class="sxs-lookup"><span data-stu-id="a1f35-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1f35-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1f35-112">S_OK</span></span>|<span data-ttu-id="a1f35-113">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="a1f35-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="a1f35-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a1f35-114">E_NOTIMPL</span></span>|<span data-ttu-id="a1f35-115">Wersja środowiska uruchomieniowego języka wspólnego (CLR) jest wcześniejsza niż wersja środowiska CLR w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a1f35-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1f35-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a1f35-116">Remarks</span></span>  

 <span data-ttu-id="a1f35-117">Ta metoda nie działa w przypadku wersji CLR wcześniejszych niż wersja środowiska CLR w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a1f35-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1f35-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a1f35-118">Requirements</span></span>  

 <span data-ttu-id="a1f35-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1f35-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1f35-120">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="a1f35-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a1f35-121">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1f35-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1f35-122">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1f35-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f35-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a1f35-123">See also</span></span>

- [<span data-ttu-id="a1f35-124">ICLRRuntimeInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a1f35-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="a1f35-125">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="a1f35-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a1f35-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="a1f35-126">Hosting</span></span>](index.md)
