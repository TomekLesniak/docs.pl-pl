---
title: ICorDebugCode2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
ms.openlocfilehash: 1e5b92d99d8ae52c88f1517f9c3d7db8e70598ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720805"
---
# <a name="icordebugcode2-interface"></a>ICorDebugCode2, interfejs

Dostarcza metody, które zwiększają możliwości programu "ICorDebugCode".  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetCodeChunks, metoda](icordebugcode2-getcodechunks-method.md)|Pobiera fragmenty kodu, z których składa się ten obiekt kodu.|  
|[GetCompilerFlags, metoda](icordebugcode2-getcompilerflags-method.md)|Pobiera flagi określające warunki, w których ten obiekt kodu był skompilowany lub generowany przy użyciu generatora obrazu natywnego (Ngen.exe).|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugCode3 — Interfejs](icordebugcode3-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
