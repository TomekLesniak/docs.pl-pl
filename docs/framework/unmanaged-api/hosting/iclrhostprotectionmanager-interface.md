---
title: ICLRHostProtectionManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
ms.openlocfilehash: e8ead998907d55b0bfbf82e5f6f4e7c504f657ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714162"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="05df5-102">ICLRHostProtectionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="05df5-102">ICLRHostProtectionManager Interface</span></span>

<span data-ttu-id="05df5-103">Umożliwia hostowi blokowanie określonych zarządzanych klas, metod, właściwości i pól z uruchamiania w częściowo zaufanym kodzie.</span><span class="sxs-lookup"><span data-stu-id="05df5-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05df5-104">Metody</span><span class="sxs-lookup"><span data-stu-id="05df5-104">Methods</span></span>  
  
|<span data-ttu-id="05df5-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="05df5-105">Method</span></span>|<span data-ttu-id="05df5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="05df5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05df5-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="05df5-107">SetEagerSerializeGrantSets</span></span>](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="05df5-108">Zapewnia gwarancję, że niektóre rzadkie sytuacje wyścigu, które mogą spowodować krytyczne błędy środowiska uruchomieniowego języka wspólnego (CLR), nigdy nie będą występowały.</span><span class="sxs-lookup"><span data-stu-id="05df5-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="05df5-109">SetProtectedCategories, metoda</span><span class="sxs-lookup"><span data-stu-id="05df5-109">SetProtectedCategories Method</span></span>](iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="05df5-110">Określa kategorie typów zarządzanych i członków, których uruchamianie ma być blokowane w kodzie częściowo zaufanym.</span><span class="sxs-lookup"><span data-stu-id="05df5-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05df5-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="05df5-111">Requirements</span></span>  

 <span data-ttu-id="05df5-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05df5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05df5-113">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="05df5-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05df5-114">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="05df5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05df5-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05df5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05df5-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="05df5-116">See also</span></span>

- [<span data-ttu-id="05df5-117">EApiCategories — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="05df5-117">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="05df5-118">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="05df5-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
