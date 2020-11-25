---
title: GetCLRIdentityManager — Funkcja
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
ms.openlocfilehash: 9d1196749e033c71b0c8923d0325eb4886122d1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733662"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="0bd50-102">GetCLRIdentityManager — Funkcja</span><span class="sxs-lookup"><span data-stu-id="0bd50-102">GetCLRIdentityManager Function</span></span>

<span data-ttu-id="0bd50-103">Pobiera wskaźnik do interfejsu, który umożliwia środowisko uruchomieniowe języka wspólnego (CLR) do zarządzania tożsamościami.</span><span class="sxs-lookup"><span data-stu-id="0bd50-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="0bd50-104">Ta funkcja jest przestarzała w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0bd50-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bd50-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0bd50-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bd50-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="0bd50-106">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="0bd50-107">podczas A `REFIID` (identyfikator interfejsu), który określa interfejs do pobrania.</span><span class="sxs-lookup"><span data-stu-id="0bd50-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="0bd50-108">Ta wartość musi być równa IID_ICLRAssemblyIdentityManager lub IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="0bd50-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="0bd50-109">określoną Wskaźnik do adresu obiektu [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) lub [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0bd50-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bd50-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0bd50-110">Remarks</span></span>  

 <span data-ttu-id="0bd50-111">Wywołaj funkcję [GetRealProcAddress —](getrealprocaddress-function.md) , aby uzyskać wskaźnik do `GetCLRIdentityManager` funkcji.</span><span class="sxs-lookup"><span data-stu-id="0bd50-111">Call the [GetRealProcAddress](getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bd50-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0bd50-112">Requirements</span></span>  

 <span data-ttu-id="0bd50-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bd50-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bd50-114">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0bd50-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0bd50-115">**Biblioteka:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="0bd50-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="0bd50-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bd50-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd50-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0bd50-117">See also</span></span>

- [<span data-ttu-id="0bd50-118">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="0bd50-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
