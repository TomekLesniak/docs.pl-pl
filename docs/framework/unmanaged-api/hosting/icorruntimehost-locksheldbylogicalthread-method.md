---
title: ICorRuntimeHost::LocksHeldByLogicalThread — Metoda
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
ms.openlocfilehash: 16f34d91861f9fcae51691ab13549bdf1ef333a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671502"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="fe8e4-102">ICorRuntimeHost::LocksHeldByLogicalThread — Metoda</span><span class="sxs-lookup"><span data-stu-id="fe8e4-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>

<span data-ttu-id="fe8e4-103">Pobiera liczbę blokad, które są przechowywane w bieżącym wątku.</span><span class="sxs-lookup"><span data-stu-id="fe8e4-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="fe8e4-104">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="fe8e4-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe8e4-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="fe8e4-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe8e4-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="fe8e4-106">Parameters</span></span>  

 `pCount`  
 <span data-ttu-id="fe8e4-107">określoną Wskaźnik do liczby blokad, które są przechowywane w bieżącym wątku.</span><span class="sxs-lookup"><span data-stu-id="fe8e4-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe8e4-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fe8e4-108">Requirements</span></span>  

 <span data-ttu-id="fe8e4-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe8e4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe8e4-110">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fe8e4-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe8e4-111">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe8e4-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe8e4-112">**.NET Framework wersje:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="fe8e4-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe8e4-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fe8e4-113">See also</span></span>

- [<span data-ttu-id="fe8e4-114">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fe8e4-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
