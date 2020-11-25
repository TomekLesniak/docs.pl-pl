---
title: Metoda ICorDebugILCode2::GetLocalVarSigToken
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
ms.openlocfilehash: 33533c9e3bfbe78abeddb5ed591f741219826127
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728636"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a>Metoda ICorDebugILCode2::GetLocalVarSigToken

[Obsługiwane w .NET Framework 4.5.2 i nowszych wersjach]  
  
 Pobiera token metadanych lokalnej zmiennej sygnatury dla funkcji reprezentowanej przez to wystąpienie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pmdSig`  
 określoną Wskaźnik do `mdSignature` tokenu dla zmiennej lokalnej dla tej funkcji lub `mdSignatureNil` Jeśli nie ma podpisu (oznacza to, że funkcja nie ma żadnych zmiennych lokalnych).  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejs ICorDebugILCode2](icordebugilcode2-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
