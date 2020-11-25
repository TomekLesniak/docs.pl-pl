---
title: ICorDebugChain::GetCaller — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
ms.openlocfilehash: 0f616b3bae48a972c0fc8935c35add7d844a7364
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730113"
---
# <a name="icordebugchaingetcaller-method"></a>ICorDebugChain::GetCaller — Metoda

Pobiera łańcuch, który wywołał ten łańcuch.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppChain`  
 określoną Wskaźnik do adresu obiektu ICorDebugChain, który reprezentuje łańcuch wywoływania.  
  
 Jeśli ten łańcuch został wywołany spontanicznie (tak jak w przypadku, gdy ten łańcuch lub debuger zainicjował stos wywołań), `ppChain` będzie miał wartość null.  
  
## <a name="remarks"></a>Uwagi  

 Łańcuch wywołujący może znajdować się w innym wątku, jeśli wywołanie zostało zorganizowane między wątkami.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
