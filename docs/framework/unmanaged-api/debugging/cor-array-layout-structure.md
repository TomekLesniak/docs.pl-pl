---
title: COR_ARRAY_LAYOUT — Struktury
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
ms.openlocfilehash: 2ca6c89a671c4d7882e7cefdb820d07ac5636530
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727409"
---
# <a name="cor_array_layout-structure"></a><span data-ttu-id="8c062-102">COR_ARRAY_LAYOUT — Struktury</span><span class="sxs-lookup"><span data-stu-id="8c062-102">COR_ARRAY_LAYOUT Structure</span></span>

<span data-ttu-id="8c062-103">Zawiera informacje o układzie obiektu tablicy w pamięci.</span><span class="sxs-lookup"><span data-stu-id="8c062-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c062-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8c062-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;
    ULONG32 rankSize;
    ULONG32 numRanks;
    ULONG32 rankOffset;
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="8c062-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="8c062-105">Members</span></span>  
  
|<span data-ttu-id="8c062-106">Członek</span><span class="sxs-lookup"><span data-stu-id="8c062-106">Member</span></span>|<span data-ttu-id="8c062-107">Opis</span><span class="sxs-lookup"><span data-stu-id="8c062-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="8c062-108">Identyfikator typu obiektów, które zawiera tablica.</span><span class="sxs-lookup"><span data-stu-id="8c062-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="8c062-109">Wartość wyliczenia CorElementType —, która wskazuje, czy składnik jest odwołaniem do wyrzucania elementów bezużytecznych, klasą wartości lub elementem pierwotnym.</span><span class="sxs-lookup"><span data-stu-id="8c062-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="8c062-110">Przesunięcie do pierwszego elementu w tablicy.</span><span class="sxs-lookup"><span data-stu-id="8c062-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="8c062-111">Rozmiar każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="8c062-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="8c062-112">Przesunięcie do liczby elementów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="8c062-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="8c062-113">Rozmiar rangi w bajtach.</span><span class="sxs-lookup"><span data-stu-id="8c062-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="8c062-114">Liczba rangi w tablicy.</span><span class="sxs-lookup"><span data-stu-id="8c062-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="8c062-115">Przesunięcie, od którego są uruchamiane Range.</span><span class="sxs-lookup"><span data-stu-id="8c062-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c062-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8c062-116">Remarks</span></span>  

 <span data-ttu-id="8c062-117">`rankSize`Pole określa rozmiar rangi w tablicy wielowymiarowej.</span><span class="sxs-lookup"><span data-stu-id="8c062-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="8c062-118">Jest to dokładne dla tablic jednowymiarowych.</span><span class="sxs-lookup"><span data-stu-id="8c062-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="8c062-119">Wartość jest równa `numRanks` 1 dla jednowymiarowej tablicy i `N` dla wielowymiarowej tablicy `N` wymiarów.</span><span class="sxs-lookup"><span data-stu-id="8c062-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c062-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8c062-120">Requirements</span></span>  

 <span data-ttu-id="8c062-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c062-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c062-122">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8c062-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c062-123">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8c062-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c062-124">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c062-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c062-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8c062-125">See also</span></span>

- [<span data-ttu-id="8c062-126">Struktury debugowania</span><span class="sxs-lookup"><span data-stu-id="8c062-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="8c062-127">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="8c062-127">Debugging</span></span>](index.md)
