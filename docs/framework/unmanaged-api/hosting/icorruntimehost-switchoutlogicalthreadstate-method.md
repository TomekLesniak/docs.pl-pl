---
title: ICorRuntimeHost::SwitchOutLogicalThreadState — Metoda
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
ms.openlocfilehash: e41ead54b50b8b28ebd9ee9c97d15ca6c71e7313
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690125"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="d5ec1-102">ICorRuntimeHost::SwitchOutLogicalThreadState — Metoda</span><span class="sxs-lookup"><span data-stu-id="d5ec1-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>

<span data-ttu-id="d5ec1-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="d5ec1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5ec1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d5ec1-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5ec1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d5ec1-105">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="d5ec1-106">określoną Plik cookie wskazujący, że włókna są przełączane.</span><span class="sxs-lookup"><span data-stu-id="d5ec1-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5ec1-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d5ec1-107">Requirements</span></span>  

 <span data-ttu-id="d5ec1-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5ec1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5ec1-109">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d5ec1-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5ec1-110">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5ec1-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5ec1-111">**Wersja .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="d5ec1-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ec1-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d5ec1-112">See also</span></span>

- [<span data-ttu-id="d5ec1-113">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d5ec1-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
