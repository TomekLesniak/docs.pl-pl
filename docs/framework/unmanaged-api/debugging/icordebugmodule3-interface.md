---
title: ICorDebugModule3 — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
ms.openlocfilehash: 543a1a3c79b6cf3eb799da5844f35286dfa91940
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709560"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="a5ac4-102">ICorDebugModule3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a5ac4-102">ICorDebugModule3 Interface</span></span>

<span data-ttu-id="a5ac4-103">Tworzy czytnik symbolu dla modułu dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="a5ac4-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ac4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a5ac4-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a5ac4-105">Metody</span><span class="sxs-lookup"><span data-stu-id="a5ac4-105">Methods</span></span>  
  
|<span data-ttu-id="a5ac4-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="a5ac4-106">Method</span></span>|<span data-ttu-id="a5ac4-107">Opis</span><span class="sxs-lookup"><span data-stu-id="a5ac4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5ac4-108">ICorDebugModule3::CreateReaderForInMemorySymbols — Metoda</span><span class="sxs-lookup"><span data-stu-id="a5ac4-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="a5ac4-109">Tworzy czytnik symboli (zazwyczaj [interfejs ISymUnmanagedReader](../diagnostics/isymunmanagedreader-interface.md)) dla modułu dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="a5ac4-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5ac4-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a5ac4-110">Remarks</span></span>  

 <span data-ttu-id="a5ac4-111">Ten interfejs logicznie rozszerza interfejsy "ICorDebugModule" i "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="a5ac4-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5ac4-112">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="a5ac4-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5ac4-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a5ac4-113">Requirements</span></span>  

 <span data-ttu-id="a5ac4-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5ac4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5ac4-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a5ac4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5ac4-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a5ac4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5ac4-117">**.NET Framework wersje:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="a5ac4-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a5ac4-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a5ac4-118">See also</span></span>

- [<span data-ttu-id="a5ac4-119">ICorDebugRemoteTarget — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a5ac4-119">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="a5ac4-120">ICorDebug — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a5ac4-120">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="a5ac4-121">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="a5ac4-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
