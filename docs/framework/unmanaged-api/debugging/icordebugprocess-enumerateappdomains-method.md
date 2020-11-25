---
title: ICorDebugProcess::EnumerateAppDomains — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
ms.openlocfilehash: 408658a0abcba9daf4c3046476e21fd4325c7144
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695143"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="1a774-102">ICorDebugProcess::EnumerateAppDomains — Metoda</span><span class="sxs-lookup"><span data-stu-id="1a774-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>

<span data-ttu-id="1a774-103">Wylicza wszystkie domeny aplikacji w tym procesie.</span><span class="sxs-lookup"><span data-stu-id="1a774-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a774-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1a774-104">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a774-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="1a774-105">Parameters</span></span>  

 `ppAppDomains`  
 <span data-ttu-id="1a774-106">określoną Wskaźnik na adres elementu [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) , który jest modułem wyliczającym dla domen aplikacji w tym procesie.</span><span class="sxs-lookup"><span data-stu-id="1a774-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a774-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1a774-107">Remarks</span></span>  

 <span data-ttu-id="1a774-108">Tej metody można użyć przed wywołaniem zwrotnym [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1a774-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a774-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1a774-109">Requirements</span></span>  

 <span data-ttu-id="1a774-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a774-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a774-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1a774-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a774-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1a774-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a774-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a774-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
