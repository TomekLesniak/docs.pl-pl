---
title: ICorRuntimeHost::SwitchInLogicalThreadState — Metoda
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: a4590bcd96226a713ff5535a8bc802c2116f862a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690138"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="43622-102">ICorRuntimeHost::SwitchInLogicalThreadState — Metoda</span><span class="sxs-lookup"><span data-stu-id="43622-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>

<span data-ttu-id="43622-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="43622-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43622-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="43622-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43622-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="43622-105">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="43622-106">podczas Plik cookie wskazujący włókna do użycia.</span><span class="sxs-lookup"><span data-stu-id="43622-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43622-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="43622-107">Requirements</span></span>  

 <span data-ttu-id="43622-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43622-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43622-109">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="43622-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43622-110">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43622-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43622-111">**Wersja .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="43622-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43622-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="43622-112">See also</span></span>

- [<span data-ttu-id="43622-113">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="43622-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
