---
title: ICorRuntimeHost::Start — Metoda
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: bc647ad025b5e22187b476383ed0128761cb632f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721039"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="cd30f-102">ICorRuntimeHost::Start — Metoda</span><span class="sxs-lookup"><span data-stu-id="cd30f-102">ICorRuntimeHost::Start Method</span></span>

<span data-ttu-id="cd30f-103">Uruchamia środowisko uruchomieniowe języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="cd30f-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd30f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cd30f-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="cd30f-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="cd30f-105">Return Value</span></span>  
  
|<span data-ttu-id="cd30f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd30f-106">HRESULT</span></span>|<span data-ttu-id="cd30f-107">Opis</span><span class="sxs-lookup"><span data-stu-id="cd30f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd30f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd30f-108">S_OK</span></span>|<span data-ttu-id="cd30f-109">Operacja zakończyła się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="cd30f-109">The operation was successful.</span></span>|  
|<span data-ttu-id="cd30f-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="cd30f-110">S_FALSE</span></span>|<span data-ttu-id="cd30f-111">Nie można ukończyć operacji.</span><span class="sxs-lookup"><span data-stu-id="cd30f-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="cd30f-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd30f-112">E_FAIL</span></span>|<span data-ttu-id="cd30f-113">Wystąpił nieznany, Katastrofalny błąd.</span><span class="sxs-lookup"><span data-stu-id="cd30f-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="cd30f-114">Jeśli metoda zwraca E_FAIL, środowisko CLR nie będzie już możliwe do użycia w procesie.</span><span class="sxs-lookup"><span data-stu-id="cd30f-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="cd30f-115">Kolejne wywołania interfejsów API hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cd30f-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cd30f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cd30f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cd30f-117">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="cd30f-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd30f-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cd30f-118">Remarks</span></span>  

 <span data-ttu-id="cd30f-119">Zazwyczaj nie jest konieczne wywoływanie `Start` metody, ponieważ środowisko CLR jest uruchamiane automatycznie przy pierwszym żądaniu uruchomienia kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="cd30f-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd30f-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cd30f-120">Requirements</span></span>  

 <span data-ttu-id="cd30f-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd30f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd30f-122">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cd30f-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd30f-123">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd30f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd30f-124">**.NET Framework wersje:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="cd30f-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd30f-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cd30f-125">See also</span></span>

- [<span data-ttu-id="cd30f-126">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cd30f-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
