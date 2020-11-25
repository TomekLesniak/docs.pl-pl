---
title: IApartmentCallback — Interfejs
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
ms.openlocfilehash: 0f38314df766b74164bf5e98d9b2153d2dddbcc1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721741"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="497ae-102">IApartmentCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="497ae-102">IApartmentCallback Interface</span></span>

<span data-ttu-id="497ae-103">Zapewnia metody tworzenia wywołań zwrotnych w obrębie apartamentu.</span><span class="sxs-lookup"><span data-stu-id="497ae-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="497ae-104">*Apartament* jest kontenerem logicznym w ramach procesu dla obiektów, które mają takie same wymagania dotyczące dostępu do wątków.</span><span class="sxs-lookup"><span data-stu-id="497ae-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="497ae-105">Metody</span><span class="sxs-lookup"><span data-stu-id="497ae-105">Methods</span></span>  
  
|<span data-ttu-id="497ae-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="497ae-106">Method</span></span>|<span data-ttu-id="497ae-107">Opis</span><span class="sxs-lookup"><span data-stu-id="497ae-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="497ae-108">DoCallback, metoda</span><span class="sxs-lookup"><span data-stu-id="497ae-108">DoCallback Method</span></span>](iapartmentcallback-docallback-method.md)|<span data-ttu-id="497ae-109">Wykonuje określoną funkcję w obrębie apartamentu.</span><span class="sxs-lookup"><span data-stu-id="497ae-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="497ae-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="497ae-110">Requirements</span></span>  

 <span data-ttu-id="497ae-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="497ae-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="497ae-112">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="497ae-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="497ae-113">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="497ae-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="497ae-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="497ae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="497ae-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="497ae-115">See also</span></span>

- [<span data-ttu-id="497ae-116">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="497ae-116">Hosting Interfaces</span></span>](hosting-interfaces.md)
