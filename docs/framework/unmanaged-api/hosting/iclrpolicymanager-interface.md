---
title: ICLRPolicyManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 7092a1c792fee7f6173dcde211b8e807f6ab02a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725589"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="48a33-102">ICLRPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="48a33-102">ICLRPolicyManager Interface</span></span>

<span data-ttu-id="48a33-103">Dostarcza metody, które pozwalają hostowi określić akcje zasad, które mają być podejmowane w przypadku awarii i przekroczeń limitu czasu.</span><span class="sxs-lookup"><span data-stu-id="48a33-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48a33-104">Metody</span><span class="sxs-lookup"><span data-stu-id="48a33-104">Methods</span></span>  
  
|<span data-ttu-id="48a33-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="48a33-105">Method</span></span>|<span data-ttu-id="48a33-106">Opis</span><span class="sxs-lookup"><span data-stu-id="48a33-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48a33-107">SetActionOnFailure, metoda</span><span class="sxs-lookup"><span data-stu-id="48a33-107">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="48a33-108">Określa akcję zasad, która ma być wykonywana przez środowisko uruchomieniowe języka wspólnego (CLR) w przypadku wystąpienia określonego błędu.</span><span class="sxs-lookup"><span data-stu-id="48a33-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="48a33-109">SetActionOnTimeout, metoda</span><span class="sxs-lookup"><span data-stu-id="48a33-109">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="48a33-110">Określa akcję zasad wykonywaną przez środowisko CLR po przełączeniu określonej operacji.</span><span class="sxs-lookup"><span data-stu-id="48a33-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="48a33-111">SetDefaultAction, metoda</span><span class="sxs-lookup"><span data-stu-id="48a33-111">SetDefaultAction Method</span></span>](iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="48a33-112">Określa akcję zasad wykonywaną przez środowisko CLR po wystąpieniu określonej operacji.</span><span class="sxs-lookup"><span data-stu-id="48a33-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="48a33-113">SetTimeout, metoda</span><span class="sxs-lookup"><span data-stu-id="48a33-113">SetTimeout Method</span></span>](iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="48a33-114">Ustawia wartość limitu czasu dla określonej operacji.</span><span class="sxs-lookup"><span data-stu-id="48a33-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="48a33-115">SetTimeoutAndAction, metoda</span><span class="sxs-lookup"><span data-stu-id="48a33-115">SetTimeoutAndAction Method</span></span>](iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="48a33-116">Ustawia wartość limitu czasu dla określonej operacji i określa akcję zasad, którą powinien wykonać środowisko CLR po wystąpieniu operacji.</span><span class="sxs-lookup"><span data-stu-id="48a33-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="48a33-117">SetUnhandledExceptionPolicy, metoda</span><span class="sxs-lookup"><span data-stu-id="48a33-117">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="48a33-118">Określa zachowanie środowiska CLR w przypadku wystąpienia nieobsługiwanego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="48a33-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48a33-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="48a33-119">Requirements</span></span>  

 <span data-ttu-id="48a33-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48a33-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48a33-121">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="48a33-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48a33-122">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48a33-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48a33-123">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48a33-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48a33-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="48a33-124">See also</span></span>

- [<span data-ttu-id="48a33-125">EClrFailure — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="48a33-125">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="48a33-126">EClrOperation — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="48a33-126">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="48a33-127">EPolicyAction — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="48a33-127">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="48a33-128">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="48a33-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
