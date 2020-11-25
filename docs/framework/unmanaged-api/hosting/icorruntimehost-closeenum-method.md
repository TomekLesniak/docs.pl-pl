---
title: ICorRuntimeHost::CloseEnum — Metoda
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
ms.openlocfilehash: d3748621474373fee8248496d48414ff67c699d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715700"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="15ea8-102">ICorRuntimeHost::CloseEnum — Metoda</span><span class="sxs-lookup"><span data-stu-id="15ea8-102">ICorRuntimeHost::CloseEnum Method</span></span>

<span data-ttu-id="15ea8-103">Resetuje moduł wyliczający domeny z powrotem do początku listy domen.</span><span class="sxs-lookup"><span data-stu-id="15ea8-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ea8-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="15ea8-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15ea8-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="15ea8-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="15ea8-106">podczas Moduł wyliczający do zresetowania.</span><span class="sxs-lookup"><span data-stu-id="15ea8-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15ea8-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="15ea8-107">Return Value</span></span>  
  
|<span data-ttu-id="15ea8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15ea8-108">HRESULT</span></span>|<span data-ttu-id="15ea8-109">Opis</span><span class="sxs-lookup"><span data-stu-id="15ea8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15ea8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="15ea8-110">S_OK</span></span>|<span data-ttu-id="15ea8-111">Operacja zakończyła się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="15ea8-111">The operation was successful.</span></span>|  
|<span data-ttu-id="15ea8-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="15ea8-112">S_FALSE</span></span>|<span data-ttu-id="15ea8-113">Nie można ukończyć operacji.</span><span class="sxs-lookup"><span data-stu-id="15ea8-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="15ea8-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15ea8-114">E_FAIL</span></span>|<span data-ttu-id="15ea8-115">Wystąpił nieznany, Katastrofalny błąd.</span><span class="sxs-lookup"><span data-stu-id="15ea8-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="15ea8-116">Jeśli metoda zwraca E_FAIL, środowisko uruchomieniowe języka wspólnego (CLR) nie jest już możliwe do użycia w procesie.</span><span class="sxs-lookup"><span data-stu-id="15ea8-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="15ea8-117">Kolejne wywołania interfejsów API hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="15ea8-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="15ea8-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15ea8-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15ea8-119">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="15ea8-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15ea8-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="15ea8-120">Requirements</span></span>  

 <span data-ttu-id="15ea8-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15ea8-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ea8-122">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="15ea8-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15ea8-123">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15ea8-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15ea8-124">**.NET Framework wersje:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="15ea8-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ea8-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="15ea8-125">See also</span></span>

- [<span data-ttu-id="15ea8-126">CorBindToRuntimeEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="15ea8-126">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="15ea8-127">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="15ea8-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
