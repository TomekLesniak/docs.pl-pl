---
title: ICorDebug::Initialize — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
ms.openlocfilehash: 5cdd89ebdbb5abb9b001c1489a54bfb867808c5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723431"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="1d313-102">ICorDebug::Initialize — Metoda</span><span class="sxs-lookup"><span data-stu-id="1d313-102">ICorDebug::Initialize Method</span></span>

<span data-ttu-id="1d313-103">Inicjuje `ICorDebug` obiekt.</span><span class="sxs-lookup"><span data-stu-id="1d313-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d313-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1d313-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1d313-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1d313-105">Remarks</span></span>  

 <span data-ttu-id="1d313-106">Debuger musi wywołać `Initialize` w czasie tworzenia, aby zainicjować usługi debugowania.</span><span class="sxs-lookup"><span data-stu-id="1d313-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="1d313-107">Ta metoda musi być wywoływana przed wywołaniem jakiejkolwiek innej metody dla `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="1d313-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d313-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1d313-108">Requirements</span></span>  

 <span data-ttu-id="1d313-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d313-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d313-110">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1d313-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d313-111">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1d313-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d313-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d313-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d313-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1d313-113">See also</span></span>

- [<span data-ttu-id="1d313-114">ICorDebug — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1d313-114">ICorDebug Interface</span></span>](icordebug-interface.md)
