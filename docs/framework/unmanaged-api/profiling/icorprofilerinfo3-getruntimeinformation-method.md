---
title: ICorProfilerInfo3::GetRuntimeInformation — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
ms.openlocfilehash: fdb2b1601e0164de19bcc1e8f60856346aeaacb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698016"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="ec891-102">ICorProfilerInfo3::GetRuntimeInformation — Metoda</span><span class="sxs-lookup"><span data-stu-id="ec891-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>

<span data-ttu-id="ec891-103">Zawiera informacje o wersji dotyczące PROFILOWANEGO środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="ec891-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec891-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ec891-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec891-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ec891-105">Parameters</span></span>  

 `pClrInstanceId`  
 <span data-ttu-id="ec891-106">określoną Identyfikator reprezentatywny uruchomionego wystąpienia środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="ec891-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="ec891-107">Jest to takie samo, jak `ClrInstanceID` raport zdarzenia uruchamiania śledzenie zdarzeń systemu Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="ec891-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="ec891-108">określoną Typ środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="ec891-108">[out] The runtime type.</span></span> <span data-ttu-id="ec891-109">Ten parametr zwraca `COR_PRF_DESKTOP_CLR` dla wersji klasycznej środowiska CLR lub `COR_PRF_CORE_CLR` dla podstawowej wersji środowiska CLR używanej w technologii Silverlight.</span><span class="sxs-lookup"><span data-stu-id="ec891-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="ec891-110">określoną Numer wersji głównej środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="ec891-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="ec891-111">określoną Numer wersji pomocniczej środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="ec891-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="ec891-112">określoną Numer wersji kompilacji środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="ec891-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="ec891-113">określoną Numer wersji środowiska CLR skojarzonego z aktualizacją oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="ec891-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="ec891-114">podczas Długość (w znakach) bufora, który `szVersionString` wskazuje.</span><span class="sxs-lookup"><span data-stu-id="ec891-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="ec891-115">określoną Długość, w znakach, z `szVersionString` .</span><span class="sxs-lookup"><span data-stu-id="ec891-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="ec891-116">określoną Ciąg wersji środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="ec891-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec891-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ec891-117">Remarks</span></span>  

 <span data-ttu-id="ec891-118">Dla dowolnego parametru można przekazać wartość null.</span><span class="sxs-lookup"><span data-stu-id="ec891-118">You may pass null for any parameter.</span></span> <span data-ttu-id="ec891-119">Jednak `pcchVersionString` nie może mieć wartości null, chyba że `szVersionString` ma również wartość null.</span><span class="sxs-lookup"><span data-stu-id="ec891-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec891-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ec891-120">Requirements</span></span>  

 <span data-ttu-id="ec891-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec891-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec891-122">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="ec891-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec891-123">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ec891-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec891-124">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec891-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec891-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ec891-125">See also</span></span>

- [<span data-ttu-id="ec891-126">ICorProfilerInfo3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ec891-126">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="ec891-127">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="ec891-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="ec891-128">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="ec891-128">Profiling</span></span>](index.md)
