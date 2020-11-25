---
title: ICorDebugFrame::GetStackRange — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: 0cfc734e3c2d250bba045a926f5b178b6cbc1ba4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728202"
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange — Metoda

Pobiera bezwzględny zakres adresów tej ramki stosu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pStart`  
 określoną Wskaźnik do `CORDB_ADDRESS` obiektu, który określa adres początkowy ramki stosu reprezentowanej przez ten `ICorDebugFrame` obiekt.  
  
 `pEnd`  
 określoną Wskaźnik do `CORDB_ADDRESS` obiektu, który określa adres końcowy ramki stosu reprezentowanej przez ten `ICorDebugFrame` obiekt.  
  
## <a name="remarks"></a>Uwagi  

 Zakres adresów stosu jest przydatny do zszywania razem z przeplotem śladów stosu zebranych z wielu aparatów debugowania. Zakres liczbowy nie zawiera żadnych informacji o zawartości ramki stosu. Jest to zrozumiałe tylko dla porównania lokalizacji ramek stosu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
