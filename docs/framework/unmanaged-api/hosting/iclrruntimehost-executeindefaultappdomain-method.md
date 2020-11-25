---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: df0b2d96963ad03e04bd8770d8a8078c6c20b8ff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728871"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="0616e-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain — Metoda</span><span class="sxs-lookup"><span data-stu-id="0616e-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>

<span data-ttu-id="0616e-103">Wywołuje określoną metodę określonego typu w określonym zarządzanym zestawie.</span><span class="sxs-lookup"><span data-stu-id="0616e-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0616e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0616e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0616e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0616e-105">Parameters</span></span>  

 `pwzAssemblyPath`  
 <span data-ttu-id="0616e-106">podczas Ścieżka do <xref:System.Reflection.Assembly> definiująca, <xref:System.Type> której metody ma być wywoływana.</span><span class="sxs-lookup"><span data-stu-id="0616e-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="0616e-107">podczas Nazwa <xref:System.Type> , która definiuje metodę do wywołania.</span><span class="sxs-lookup"><span data-stu-id="0616e-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="0616e-108">podczas Nazwa metody do wywołania.</span><span class="sxs-lookup"><span data-stu-id="0616e-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="0616e-109">podczas Parametr ciągu, który ma zostać przekazany do metody.</span><span class="sxs-lookup"><span data-stu-id="0616e-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="0616e-110">określoną Wartość całkowita zwrócona przez wywołaną metodę.</span><span class="sxs-lookup"><span data-stu-id="0616e-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0616e-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="0616e-111">Return Value</span></span>  
  
|<span data-ttu-id="0616e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0616e-112">HRESULT</span></span>|<span data-ttu-id="0616e-113">Opis</span><span class="sxs-lookup"><span data-stu-id="0616e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0616e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0616e-114">S_OK</span></span>|<span data-ttu-id="0616e-115">`ExecuteInDefaultAppDomain` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="0616e-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="0616e-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0616e-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0616e-117">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="0616e-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0616e-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0616e-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0616e-119">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="0616e-119">The call timed out.</span></span>|  
|<span data-ttu-id="0616e-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0616e-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0616e-121">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="0616e-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0616e-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0616e-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0616e-123">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="0616e-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0616e-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0616e-124">E_FAIL</span></span>|<span data-ttu-id="0616e-125">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="0616e-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0616e-126">Jeśli metoda zwraca E_FAIL, lista CRL nie będzie już można używać w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="0616e-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="0616e-127">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0616e-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0616e-128">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0616e-128">Remarks</span></span>  

 <span data-ttu-id="0616e-129">Wywołana metoda musi mieć następujący podpis:</span><span class="sxs-lookup"><span data-stu-id="0616e-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="0616e-130">gdzie `pwzMethodName` reprezentuje nazwę wywołanej metody i `pwzArgument` reprezentuje wartość ciągu przekazaną jako parametr do tej metody.</span><span class="sxs-lookup"><span data-stu-id="0616e-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="0616e-131">Jeśli wartość HRESULT jest ustawiona na S_OK, `pReturnValue` jest ustawiona na wartość całkowitą zwracaną przez wywołaną metodę.</span><span class="sxs-lookup"><span data-stu-id="0616e-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="0616e-132">W przeciwnym razie `pReturnValue` nie jest ustawiona.</span><span class="sxs-lookup"><span data-stu-id="0616e-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0616e-133">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0616e-133">Requirements</span></span>  

 <span data-ttu-id="0616e-134">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0616e-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0616e-135">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0616e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0616e-136">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0616e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0616e-137">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0616e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0616e-138">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0616e-138">See also</span></span>

- [<span data-ttu-id="0616e-139">ICLRRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0616e-139">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
