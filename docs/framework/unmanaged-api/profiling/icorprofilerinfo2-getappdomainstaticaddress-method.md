---
title: ICorProfilerInfo2::GetAppDomainStaticAddress — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 271f9f4fd0d85407aedf088ffb524fa6e0398e37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727214"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="28f07-102">ICorProfilerInfo2::GetAppDomainStaticAddress — Metoda</span><span class="sxs-lookup"><span data-stu-id="28f07-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>

<span data-ttu-id="28f07-103">Pobiera adres wskazanej domeny aplikacji — pole statyczne należące do zakresu określonej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="28f07-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f07-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="28f07-104">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28f07-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="28f07-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="28f07-106">podczas Identyfikator klasy klasy, która zawiera wymagane pole domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="28f07-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="28f07-107">podczas Token metadanych dla żądanego pola domeny aplikacji — statycznej.</span><span class="sxs-lookup"><span data-stu-id="28f07-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="28f07-108">podczas Identyfikator domeny aplikacji, która jest zakresem żądanego pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="28f07-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="28f07-109">określoną Wskaźnik do adresu pola statycznego znajdującego się w określonej domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="28f07-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28f07-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="28f07-110">Remarks</span></span>  

 <span data-ttu-id="28f07-111">`GetAppDomainStaticAddress`Metoda może zwracać jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="28f07-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="28f07-112">CORPROF_E_DATAINCOMPLETE HRESULT, jeśli podane pole statyczne nie ma przypisanego adresu w określonym kontekście.</span><span class="sxs-lookup"><span data-stu-id="28f07-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="28f07-113">Adresy obiektów, które mogą znajdować się w stercie wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="28f07-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="28f07-114">Te adresy mogą stać się nieprawidłowe po wyrzucaniu elementów bezużytecznych, więc po wybraniu elementów bezużytecznych nie należy zakładać, że są one poprawne.</span><span class="sxs-lookup"><span data-stu-id="28f07-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="28f07-115">Przed ukończeniem konstruktora klasy klasy `GetAppDomainStaticAddress` zwraca CORPROF_E_DATAINCOMPLETE dla wszystkich pól statycznych, chociaż niektóre pola statyczne mogą już być zainicjowane i główne obiekty wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="28f07-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28f07-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="28f07-116">Requirements</span></span>  

 <span data-ttu-id="28f07-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28f07-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28f07-118">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="28f07-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28f07-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="28f07-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28f07-120">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28f07-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f07-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="28f07-121">See also</span></span>

- [<span data-ttu-id="28f07-122">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="28f07-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="28f07-123">ICorProfilerInfo2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="28f07-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
