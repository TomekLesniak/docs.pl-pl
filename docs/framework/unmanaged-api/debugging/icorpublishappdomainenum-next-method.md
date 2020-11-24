---
title: ICorPublishAppDomainEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: 00aff9ab4edbbebe4b924d335fa12f92e9840737
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693700"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="2ea66-102">ICorPublishAppDomainEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="2ea66-102">ICorPublishAppDomainEnum::Next Method</span></span>

<span data-ttu-id="2ea66-103">Pobiera określoną liczbę domen aplikacji, które aktualnie istnieją w procesie, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="2ea66-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ea66-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2ea66-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ea66-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2ea66-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="2ea66-106">podczas Liczba elementów, które mają zostać pobrane.</span><span class="sxs-lookup"><span data-stu-id="2ea66-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="2ea66-107">określoną Wskaźnik do tablicy pobranych obiektów [ICorPublishAppDomain](icorpublishappdomain-interface.md) , z których każdy reprezentuje domenę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2ea66-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2ea66-108">określoną Wskaźnik na liczbę domen aplikacji, które faktycznie zostały zwrócone.</span><span class="sxs-lookup"><span data-stu-id="2ea66-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="2ea66-109">Ta wartość może być równa null, jeśli `celt` jest taka.</span><span class="sxs-lookup"><span data-stu-id="2ea66-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ea66-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2ea66-110">Requirements</span></span>  

 <span data-ttu-id="2ea66-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ea66-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ea66-112">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="2ea66-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2ea66-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2ea66-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ea66-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ea66-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea66-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2ea66-115">See also</span></span>

- [<span data-ttu-id="2ea66-116">ICorPublishAppDomainEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2ea66-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
