---
title: ICorDebugMDA::GetFlags — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
ms.openlocfilehash: 38a5c2da900530b6bf78f24e224714496ceaa62c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710964"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="0a08e-102">ICorDebugMDA::GetFlags — Metoda</span><span class="sxs-lookup"><span data-stu-id="0a08e-102">ICorDebugMDA::GetFlags Method</span></span>

<span data-ttu-id="0a08e-103">Pobiera flagi skojarzone z zarządzanym asystentem debugowania (MDA) reprezentowane przez [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0a08e-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a08e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0a08e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a08e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0a08e-105">Parameters</span></span>  

 `pFlags`  
 <span data-ttu-id="0a08e-106">podczas Bitowa kombinacja wartości wyliczenia [CorDebugMDAFlags —](cordebugmdaflags-enumeration.md) , które określają ustawienia flag dla tego MDA.</span><span class="sxs-lookup"><span data-stu-id="0a08e-106">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a08e-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0a08e-107">Requirements</span></span>  

 <span data-ttu-id="0a08e-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a08e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a08e-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="0a08e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a08e-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0a08e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a08e-111">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a08e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a08e-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0a08e-112">See also</span></span>

- [<span data-ttu-id="0a08e-113">ICorDebugMDA — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0a08e-113">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="0a08e-114">Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="0a08e-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
