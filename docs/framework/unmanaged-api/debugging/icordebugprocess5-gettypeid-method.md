---
title: ICorDebugProcess5::GetTypeID — Metoda
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
ms.openlocfilehash: 3a9ef06f312126319875544caf272903b9f7c716
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701032"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="7cd81-102">ICorDebugProcess5::GetTypeID — Metoda</span><span class="sxs-lookup"><span data-stu-id="7cd81-102">ICorDebugProcess5::GetTypeID Method</span></span>

<span data-ttu-id="7cd81-103">Konwertuje adres obiektu na identyfikator [COR_TYPEID](cor-typeid-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="7cd81-103">Converts an object address to a [COR_TYPEID](cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cd81-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7cd81-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cd81-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7cd81-105">Parameters</span></span>  

 `obj`  
 <span data-ttu-id="7cd81-106">podczas Adres obiektu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="7cd81-107">Wskaźnik do wartości [COR_TYPEID](cor-typeid-structure.md) , która identyfikuje obiekt.</span><span class="sxs-lookup"><span data-stu-id="7cd81-107">A pointer to the [COR_TYPEID](cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cd81-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7cd81-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cd81-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7cd81-109">Requirements</span></span>  

 <span data-ttu-id="7cd81-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cd81-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cd81-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7cd81-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cd81-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7cd81-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cd81-113">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cd81-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd81-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7cd81-114">See also</span></span>

- [<span data-ttu-id="7cd81-115">ICorDebugProcess5 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7cd81-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="7cd81-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="7cd81-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
