---
title: ICorRuntimeHost::UnloadDomain — Metoda
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
ms.openlocfilehash: 94c84d876e19ec2ff7baba5a5a7420eec68d58c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690112"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="b604f-102">ICorRuntimeHost::UnloadDomain — Metoda</span><span class="sxs-lookup"><span data-stu-id="b604f-102">ICorRuntimeHost::UnloadDomain Method</span></span>

<span data-ttu-id="b604f-103">Zwalnia określoną domenę aplikacji z bieżącego procesu.</span><span class="sxs-lookup"><span data-stu-id="b604f-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b604f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b604f-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b604f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b604f-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="b604f-106">podczas Wskaźnik typu <xref:System._AppDomain?displayProperty=nameWithType> reprezentujący domenę, która ma zostać zwolniona.</span><span class="sxs-lookup"><span data-stu-id="b604f-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b604f-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b604f-107">Return Value</span></span>  
  
|<span data-ttu-id="b604f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b604f-108">HRESULT</span></span>|<span data-ttu-id="b604f-109">Opis</span><span class="sxs-lookup"><span data-stu-id="b604f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b604f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b604f-110">S_OK</span></span>|<span data-ttu-id="b604f-111">Operacja zakończyła się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="b604f-111">The operation was successful.</span></span>|  
|<span data-ttu-id="b604f-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b604f-112">S_FALSE</span></span>|<span data-ttu-id="b604f-113">Nie można ukończyć operacji.</span><span class="sxs-lookup"><span data-stu-id="b604f-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b604f-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b604f-114">E_FAIL</span></span>|<span data-ttu-id="b604f-115">Wystąpił nieznany, Katastrofalny błąd.</span><span class="sxs-lookup"><span data-stu-id="b604f-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b604f-116">Jeśli metoda zwraca E_FAIL, środowisko uruchomieniowe języka wspólnego (CLR) nie jest już możliwe do użycia w procesie.</span><span class="sxs-lookup"><span data-stu-id="b604f-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b604f-117">Kolejne wywołania interfejsów API hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b604f-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b604f-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b604f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b604f-119">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="b604f-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b604f-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b604f-120">Requirements</span></span>  

 <span data-ttu-id="b604f-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b604f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b604f-122">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b604f-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b604f-123">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b604f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b604f-124">**Wersja .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="b604f-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b604f-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b604f-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="b604f-126">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b604f-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
