---
title: ICorProfilerInfo::GetFunctionFromIP — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
ms.openlocfilehash: 4a7e21ae60253c741b57674212e0ecabdd844d2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722565"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="7d1a7-102">ICorProfilerInfo::GetFunctionFromIP — Metoda</span><span class="sxs-lookup"><span data-stu-id="7d1a7-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>

<span data-ttu-id="7d1a7-103">Mapuje wskaźnik zarządzanej instrukcji kodu na `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="7d1a7-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d1a7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7d1a7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d1a7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7d1a7-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="7d1a7-106">\[in] wskaźnik instrukcji w kodzie zarządzanym.</span><span class="sxs-lookup"><span data-stu-id="7d1a7-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="7d1a7-107">\[out] zwrócony identyfikator funkcji.</span><span class="sxs-lookup"><span data-stu-id="7d1a7-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d1a7-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7d1a7-108">Requirements</span></span>  

 <span data-ttu-id="7d1a7-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d1a7-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d1a7-110">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="7d1a7-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7d1a7-111">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7d1a7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d1a7-112">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d1a7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1a7-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7d1a7-113">See also</span></span>

- [<span data-ttu-id="7d1a7-114">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7d1a7-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
