---
title: ICorRuntimeHost::EnumDomains — Metoda
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
ms.openlocfilehash: f4338429dc24bf5196b92d3f18e73c98442f61e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720665"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="243fc-102">ICorRuntimeHost::EnumDomains — Metoda</span><span class="sxs-lookup"><span data-stu-id="243fc-102">ICorRuntimeHost::EnumDomains Method</span></span>

<span data-ttu-id="243fc-103">Pobiera moduł wyliczający dla domen w bieżącym procesie.</span><span class="sxs-lookup"><span data-stu-id="243fc-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="243fc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="243fc-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="243fc-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="243fc-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="243fc-106">określoną Moduł wyliczający dla domen.</span><span class="sxs-lookup"><span data-stu-id="243fc-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="243fc-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="243fc-107">Return Value</span></span>  
  
|<span data-ttu-id="243fc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="243fc-108">HRESULT</span></span>|<span data-ttu-id="243fc-109">Opis</span><span class="sxs-lookup"><span data-stu-id="243fc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="243fc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="243fc-110">S_OK</span></span>|<span data-ttu-id="243fc-111">Operacja zakończyła się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="243fc-111">The operation was successful.</span></span>|  
|<span data-ttu-id="243fc-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="243fc-112">S_FALSE</span></span>|<span data-ttu-id="243fc-113">Nie można ukończyć operacji.</span><span class="sxs-lookup"><span data-stu-id="243fc-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="243fc-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="243fc-114">E_FAIL</span></span>|<span data-ttu-id="243fc-115">Wystąpił nieznany, Katastrofalny błąd.</span><span class="sxs-lookup"><span data-stu-id="243fc-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="243fc-116">Jeśli metoda zwraca E_FAIL, środowisko uruchomieniowe języka wspólnego (CLR) nie jest już możliwe do użycia w procesie.</span><span class="sxs-lookup"><span data-stu-id="243fc-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="243fc-117">Kolejne wywołania interfejsów API hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="243fc-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="243fc-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="243fc-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="243fc-119">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="243fc-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="243fc-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="243fc-120">Requirements</span></span>  

 <span data-ttu-id="243fc-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="243fc-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="243fc-122">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="243fc-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="243fc-123">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="243fc-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="243fc-124">**Wersja .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="243fc-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="243fc-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="243fc-125">See also</span></span>

- [<span data-ttu-id="243fc-126">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="243fc-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
