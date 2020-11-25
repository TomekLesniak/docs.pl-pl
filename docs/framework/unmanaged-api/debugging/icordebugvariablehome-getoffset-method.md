---
title: 'ICorDebugVariableHome:: GetOffset — Metoda'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: c5d491b66e4ec64dffa4e19dabff876c9c473036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711796"
---
# <a name="icordebugvariablehomegetoffset-method"></a>ICorDebugVariableHome:: GetOffset — Metoda

Pobiera przesunięcie z rejestru podstawowego dla zmiennej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pOffset`  
 określoną Przesunięcie od podstawowego rejestru.  
  
## <a name="return-value"></a>Wartość zwracana  

 Metoda zwraca następujące wartości:  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`S_OK`|Zmienna znajduje się w lokalizacji pamięci względnej do rejestracji.|  
|`E_FAIL`|Zmienna nie znajduje się w lokalizacji pamięci względnej do rejestracji.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugVariableHome, interfejs](icordebugvariablehome-interface.md)
