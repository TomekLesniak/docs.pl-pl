---
title: ICorPublishProcessEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: 9965a468f788efead0477bb7574ef3bf156fd869
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692478"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="2a46c-102">ICorPublishProcessEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="2a46c-102">ICorPublishProcessEnum::Next Method</span></span>

<span data-ttu-id="2a46c-103">Pobiera określoną liczbę procesów z kolekcji, rozpoczynając od bieżącego położenia kursora.</span><span class="sxs-lookup"><span data-stu-id="2a46c-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a46c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2a46c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a46c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2a46c-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="2a46c-106">podczas Liczba procesów, które mają zostać pobrane.</span><span class="sxs-lookup"><span data-stu-id="2a46c-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="2a46c-107">określoną Wskaźnik do tablicy pobranych obiektów [ICorPublishProcess](icorpublishprocess-interface.md) , z których każdy reprezentuje proces.</span><span class="sxs-lookup"><span data-stu-id="2a46c-107">[out] A pointer to the array of retrieved [ICorPublishProcess](icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2a46c-108">określoną Wskaźnik do liczby aktualnie zwróconych procesów.</span><span class="sxs-lookup"><span data-stu-id="2a46c-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="2a46c-109">Ta wartość może być równa null, jeśli `celt` jest taka.</span><span class="sxs-lookup"><span data-stu-id="2a46c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a46c-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2a46c-110">Requirements</span></span>  

 <span data-ttu-id="2a46c-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a46c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a46c-112">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="2a46c-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2a46c-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2a46c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a46c-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a46c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a46c-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2a46c-115">See also</span></span>

- [<span data-ttu-id="2a46c-116">ICorPublishProcessEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2a46c-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)
