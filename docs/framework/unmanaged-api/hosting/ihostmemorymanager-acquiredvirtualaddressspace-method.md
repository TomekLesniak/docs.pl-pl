---
title: IHostMemoryManager::AcquiredVirtualAddressSpace — Metoda
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
ms.openlocfilehash: 58fce616ae05dcc622369a706f010f91d657389f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700629"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="cdd9b-102">IHostMemoryManager::AcquiredVirtualAddressSpace — Metoda</span><span class="sxs-lookup"><span data-stu-id="cdd9b-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>

<span data-ttu-id="cdd9b-103">Powiadamia hosta, że środowisko uruchomieniowe języka wspólnego (CLR) uzyskało określoną ilość pamięci z systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="cdd9b-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdd9b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cdd9b-104">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdd9b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cdd9b-105">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="cdd9b-106">podczas Adres początkowy pamięci.</span><span class="sxs-lookup"><span data-stu-id="cdd9b-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="cdd9b-107">podczas Rozmiar pamięci (w bajtach).</span><span class="sxs-lookup"><span data-stu-id="cdd9b-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdd9b-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cdd9b-108">Remarks</span></span>  

 <span data-ttu-id="cdd9b-109">`AcquiredVirtualAddressSpace`Metoda jest metodą wywołania zwrotnego i musi być implementowana przez moduł zapisujący aplikacji hostingowej.</span><span class="sxs-lookup"><span data-stu-id="cdd9b-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="cdd9b-110">Jest wywoływana przez środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="cdd9b-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdd9b-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cdd9b-111">Requirements</span></span>  

 <span data-ttu-id="cdd9b-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdd9b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdd9b-113">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cdd9b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cdd9b-114">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cdd9b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cdd9b-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdd9b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd9b-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cdd9b-116">See also</span></span>

- [<span data-ttu-id="cdd9b-117">IHostMemoryManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cdd9b-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
