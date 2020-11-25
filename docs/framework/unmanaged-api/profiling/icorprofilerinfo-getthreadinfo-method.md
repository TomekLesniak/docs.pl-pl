---
title: ICorProfilerInfo::GetThreadInfo — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
ms.openlocfilehash: 516a12b7a4457a0f67da24294ad96fb79d1aa5aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707519"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="a3c8c-102">ICorProfilerInfo::GetThreadInfo — Metoda</span><span class="sxs-lookup"><span data-stu-id="a3c8c-102">ICorProfilerInfo::GetThreadInfo Method</span></span>

<span data-ttu-id="a3c8c-103">Pobiera bieżącą tożsamość wątku Win32 dla określonego wątku.</span><span class="sxs-lookup"><span data-stu-id="a3c8c-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3c8c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a3c8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3c8c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a3c8c-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="a3c8c-106">podczas Identyfikator wątku, dla którego ma zostać pobrany bieżący identyfikator Win32.</span><span class="sxs-lookup"><span data-stu-id="a3c8c-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="a3c8c-107">określoną Wskaźnik do bieżącego identyfikatora wątku Win32 określonego wątku.</span><span class="sxs-lookup"><span data-stu-id="a3c8c-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3c8c-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a3c8c-108">Requirements</span></span>  

 <span data-ttu-id="a3c8c-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3c8c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3c8c-110">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="a3c8c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3c8c-111">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a3c8c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3c8c-112">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3c8c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c8c-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a3c8c-113">See also</span></span>

- [<span data-ttu-id="a3c8c-114">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a3c8c-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
