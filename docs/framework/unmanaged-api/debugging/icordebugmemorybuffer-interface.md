---
title: ICorDebugMemoryBuffer, interfejs
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 2765852309401d2aa30f91b506ba55156cd8a3e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710747"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="95ee6-102">ICorDebugMemoryBuffer, interfejs</span><span class="sxs-lookup"><span data-stu-id="95ee6-102">ICorDebugMemoryBuffer Interface</span></span>

<span data-ttu-id="95ee6-103">Reprezentuje bufor w pamięci.</span><span class="sxs-lookup"><span data-stu-id="95ee6-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95ee6-104">Metody</span><span class="sxs-lookup"><span data-stu-id="95ee6-104">Methods</span></span>  
  
|<span data-ttu-id="95ee6-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="95ee6-105">Method</span></span>|<span data-ttu-id="95ee6-106">Opis</span><span class="sxs-lookup"><span data-stu-id="95ee6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95ee6-107">GetSize — Metoda</span><span class="sxs-lookup"><span data-stu-id="95ee6-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="95ee6-108">Pobiera rozmiar buforu pamięci w bajtach.</span><span class="sxs-lookup"><span data-stu-id="95ee6-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="95ee6-109">GetStartAddress, metoda</span><span class="sxs-lookup"><span data-stu-id="95ee6-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="95ee6-110">Pobiera początkowy adres bufora pamięci.</span><span class="sxs-lookup"><span data-stu-id="95ee6-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95ee6-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="95ee6-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95ee6-112">Ten interfejs jest dostępny tylko dla .NET Native.</span><span class="sxs-lookup"><span data-stu-id="95ee6-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="95ee6-113">W przypadku zaimplementowania tego interfejsu dla scenariuszy ICorDebug poza .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.</span><span class="sxs-lookup"><span data-stu-id="95ee6-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95ee6-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="95ee6-114">Requirements</span></span>  

 <span data-ttu-id="95ee6-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95ee6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95ee6-116">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="95ee6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95ee6-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="95ee6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95ee6-118">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95ee6-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ee6-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="95ee6-119">See also</span></span>

- [<span data-ttu-id="95ee6-120">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="95ee6-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="95ee6-121">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="95ee6-121">Debugging</span></span>](index.md)
