---
title: ICLRDataTarget::GetCurrentThreadID — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
ms.openlocfilehash: 3a355822710394e9351f10be78dea283e2e9907c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703594"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="915f8-102">ICLRDataTarget::GetCurrentThreadID — Metoda</span><span class="sxs-lookup"><span data-stu-id="915f8-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>

<span data-ttu-id="915f8-103">Pobiera identyfikator systemu operacyjnego dla bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="915f8-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="915f8-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="915f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="915f8-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="915f8-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="915f8-106">określoną Wskaźnik do identyfikatora systemu operacyjnego bieżącego wątku dla procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="915f8-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="915f8-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="915f8-107">Remarks</span></span>  

 <span data-ttu-id="915f8-108">Jeśli nie ma bieżącego wątku dla procesu docelowego, `GetCurrentThreadID` Metoda może zakończyć się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="915f8-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="915f8-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="915f8-109">Requirements</span></span>  

 <span data-ttu-id="915f8-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="915f8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="915f8-111">**Nagłówek:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="915f8-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="915f8-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="915f8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="915f8-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="915f8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="915f8-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="915f8-114">See also</span></span>

- [<span data-ttu-id="915f8-115">ICLRDataTarget — Interfejs</span><span class="sxs-lookup"><span data-stu-id="915f8-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
