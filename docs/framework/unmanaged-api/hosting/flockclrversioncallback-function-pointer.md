---
title: FLockClrVersionCallback — Wskaźnik funkcji
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: d18702a1bb15d2cc6c7b8577b91ed011e9bd0c05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733675"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="5accc-102">FLockClrVersionCallback — Wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="5accc-102">FLockClrVersionCallback Function Pointer</span></span>

<span data-ttu-id="5accc-103">Wskazuje funkcję, którą wywołuje środowisko uruchomieniowe języka wspólnego (CLR), aby wskazać, że inicjalizacja została uruchomiona lub ukończona.</span><span class="sxs-lookup"><span data-stu-id="5accc-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="5accc-104">Ten wskaźnik funkcji został uznany za przestarzały w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5accc-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5accc-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="5accc-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="5accc-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5accc-106">Remarks</span></span>  

 <span data-ttu-id="5accc-107">Ta funkcja jest implementowana przez hosta.</span><span class="sxs-lookup"><span data-stu-id="5accc-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5accc-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5accc-108">Requirements</span></span>  

 <span data-ttu-id="5accc-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5accc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5accc-110">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5accc-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5accc-111">**Biblioteka:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="5accc-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="5accc-112">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5accc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5accc-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5accc-113">See also</span></span>

- [<span data-ttu-id="5accc-114">LockClrVersion — Funkcja</span><span class="sxs-lookup"><span data-stu-id="5accc-114">LockClrVersion Function</span></span>](lockclrversion-function.md)
- [<span data-ttu-id="5accc-115">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="5accc-115">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
