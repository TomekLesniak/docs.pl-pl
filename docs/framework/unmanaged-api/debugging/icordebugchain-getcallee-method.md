---
title: ICorDebugChain::GetCallee — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
ms.openlocfilehash: a28da34cd3080826f346b8957aa6ba38258b924f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730126"
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee — Metoda

Pobiera łańcuch, który został wywołany przez ten łańcuch.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppChain`  
 określoną Wskaźnik do adresu obiektu ICorDebugChain, który reprezentuje wywołany łańcuch. Jeśli ten łańcuch jest obecnie wykonywany (oznacza to, że jeśli ten łańcuch nie oczekuje na zwrócenie wywołanego łańcucha), `ppChain` będzie miał wartość null.  
  
## <a name="remarks"></a>Uwagi  

 Ten łańcuch będzie czekał na zwrócenie wywoływanego łańcucha przed wznowieniem wykonywania. Wywołany łańcuch może znajdować się w innym wątku w przypadku wywołań zorganizowanych między wątkami.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
