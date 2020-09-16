---
title: ICorProfilerInfo9, interfejs
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f38195b1a7983e23c7f5c20055ea8c2a8bfcb7d8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556853"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="950d1-102">ICorProfilerInfo9, interfejs</span><span class="sxs-lookup"><span data-stu-id="950d1-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="950d1-103">Podklasa elementu [ICorProfilerInfo8](icorprofilerinfo8-interface.md) , która dostarcza metody do wykonywania zapytań o informacje o funkcjach z wieloma natywnymi wersjami kodu.</span><span class="sxs-lookup"><span data-stu-id="950d1-103">A subclass of [ICorProfilerInfo8](icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="950d1-104">Metody</span><span class="sxs-lookup"><span data-stu-id="950d1-104">Methods</span></span>  

| <span data-ttu-id="950d1-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="950d1-105">Method</span></span>|<span data-ttu-id="950d1-106">Opis</span><span class="sxs-lookup"><span data-stu-id="950d1-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="950d1-107">GetNativeCodeStartAddresses, metoda</span><span class="sxs-lookup"><span data-stu-id="950d1-107">GetNativeCodeStartAddresses Method</span></span>](icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="950d1-108">Mając functionId i rejitId, wylicza natywny adres początkowy kodu dla wszystkich wersji trybie JIT tego kodu, który już istnieje.</span><span class="sxs-lookup"><span data-stu-id="950d1-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="950d1-109">GetILToNativeMapping3, metoda</span><span class="sxs-lookup"><span data-stu-id="950d1-109">GetILToNativeMapping3 Method</span></span>](icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="950d1-110">Przy podanym adresie początkowym kodu natywnego program zwraca informacje mapowania natywnego do IL dla tej trybie JIT wersji kodu.</span><span class="sxs-lookup"><span data-stu-id="950d1-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="950d1-111">GetCodeInfo4, metoda</span><span class="sxs-lookup"><span data-stu-id="950d1-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="950d1-112">Przy podanym adresie początkowym kodu natywnego program zwraca bloki pamięci wirtualnej, która przechowuje ten kod.</span><span class="sxs-lookup"><span data-stu-id="950d1-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="950d1-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="950d1-113">Requirements</span></span>  
<span data-ttu-id="950d1-114">**Platformy:** Zobacz [obsługiwane systemy operacyjne .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="950d1-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="950d1-115">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="950d1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="950d1-116">**Wersje .NET:**[!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="950d1-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="950d1-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="950d1-117">See also</span></span>

- [<span data-ttu-id="950d1-118">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="950d1-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
