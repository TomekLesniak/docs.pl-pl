---
title: Metoda ICorDebugILFrame4::GetCodeEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: 06a0a4c788155d6fb909e4537b980f0ba740f21a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554817"
---
# <a name="icordebugilframe4getcodeex-method"></a>Metoda ICorDebugILFrame4::GetCodeEx
[Obsługiwane w .NET Framework 4.5.2 i nowszych wersjach]  
  
 Pobiera wskaźnik do kodu, który jest wykonywany przez tę ramkę stosu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `flags`  
 podczas Element członkowski wyliczenia [ILCodeKind](ilcodekind-enumeration.md) , który określa, czy język pośredni (IL) zdefiniowany przez żądanie ReJIT profilera zostanie uwzględniony w ramce.  
  
 `ppCode`  
 określoną Wskaźnik do adresu obiektu "ICorDebugCode", który reprezentuje kod, który jest wykonywany przez tę ramkę stosu.  
  
## <a name="remarks"></a>Uwagi  
 Ta metoda jest podobna do metody [ICorDebugFrame:: GetCode](icordebugframe-getcode-method.md) , z tą różnicą, że opcjonalnie uzyskuje dostęp do kodu zdefiniowanego przez żądanie ReJIT profilera. Wywołanie tej metody z `flags` wartością `ILCODE_ORIGINAL_IL` jest równoznaczne z wywołaniem metody [GetCode](icordebugframe-getcode-method.md); Jeśli metoda ma instrumentację, jej kod IL nie będzie dostępny. `ILCODE_REJIT_IL` zezwala debugerowi na dostęp do IL zdefiniowanego przez żądanie ReJIT profilera. Jeśli IL nie ma instrumentacji, `ppCode` ma **wartość null**, a metoda zwraca `S_OK` .  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejs ICorDebugILFrame4](icordebugilframe4-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [ReJIT: Przewodnik po poradniku](/archive/blogs/davbr/rejit-a-how-to-guide)
