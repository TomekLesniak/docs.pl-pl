---
title: ICorDebugFrame::GetCallee — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
ms.openlocfilehash: 6347e0109f256dc46eb0140ffd1f51977c205b51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678808"
---
# <a name="icordebugframegetcallee-method"></a>ICorDebugFrame::GetCallee — Metoda

Pobiera wskaźnik do obiektu ICorDebugFrame w bieżącym łańcuchu, dla którego ta ramka została wywołana.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppFrame`  
 określoną Wskaźnik do adresu `ICorDebugFrame` obiektu, który reprezentuje wywoływaną ramkę. Ta wartość jest równa null, jeśli wywoływana ramka jest wewnętrzna ramką w bieżącym łańcuchu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
