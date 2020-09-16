---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: ca1643dfa980fa647164accf6432082428124acb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541242"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="19ba6-102">ICorProfilerInfo9:: GetNativeCodeStartAddresses, Metoda</span><span class="sxs-lookup"><span data-stu-id="19ba6-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="19ba6-103">Mając functionId i rejitId, wylicza natywny adres początkowy kodu dla wszystkich wersji trybie JIT tego kodu, który już istnieje.</span><span class="sxs-lookup"><span data-stu-id="19ba6-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="19ba6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="19ba6-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="19ba6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="19ba6-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="19ba6-106">\[in] identyfikator funkcji, której adresy początkowe kodu natywnego powinny zostać zwrócone.</span><span class="sxs-lookup"><span data-stu-id="19ba6-106">\[in] The ID of the function whose native code start addresses should be returned.</span></span>

- `reJitId`

  <span data-ttu-id="19ba6-107">\[in) tożsamość funkcji ponownie skompilowanej JIT.</span><span class="sxs-lookup"><span data-stu-id="19ba6-107">\[in] The identity of the JIT-recompiled function.</span></span>

- `cCodeStartAddresses`

  <span data-ttu-id="19ba6-108">\[w] maksymalny rozmiar `codeStartAddresses` tablicy.</span><span class="sxs-lookup"><span data-stu-id="19ba6-108">\[in] The maximum size of the `codeStartAddresses` array.</span></span>

- `pcCodeStartAddresses`

  <span data-ttu-id="19ba6-109">\[out] Liczba dostępnych adresów.</span><span class="sxs-lookup"><span data-stu-id="19ba6-109">\[out] The number of available addresses.</span></span>

- `codeStartAddresses`

  <span data-ttu-id="19ba6-110">\[out] tablica, z `UINT_PTR` której każdy jest adresem początkowym dla określonej funkcji.</span><span class="sxs-lookup"><span data-stu-id="19ba6-110">\[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="19ba6-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="19ba6-111">Remarks</span></span>

<span data-ttu-id="19ba6-112">Gdy kompilacja warstwowa jest włączona, funkcja może mieć więcej niż jedną treść kodu natywnego.</span><span class="sxs-lookup"><span data-stu-id="19ba6-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="19ba6-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="19ba6-113">Requirements</span></span>

<span data-ttu-id="19ba6-114">**Platformy:** Zobacz [obsługiwane systemy operacyjne .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="19ba6-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="19ba6-115">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="19ba6-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="19ba6-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="19ba6-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="19ba6-117">**Wersje .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19ba6-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="19ba6-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="19ba6-118">See also</span></span>

- [<span data-ttu-id="19ba6-119">ICorProfilerInfo9, interfejs</span><span class="sxs-lookup"><span data-stu-id="19ba6-119">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
