---
title: ICorDebugModule2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: 2b8e6048dd6b8df71ac3dddcc4397f6d512127c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695884"
---
# <a name="icordebugmodule2-interface"></a>ICorDebugModule2, interfejs

Służy jako logiczne rozszerzenie interfejsu ICorDebugModule.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[ApplyChanges, metoda](icordebugmodule2-applychanges-method.md)|Stosuje zmiany w metadanych i zmiany w kodzie języka pośredniego firmy Microsoft (MSIL) do uruchomionego procesu.|  
|[GetJITCompilerFlags, metoda](icordebugmodule2-getjitcompilerflags-method.md)|Pobiera flagi kontrolujące kompilację just-in-Time (JIT) dla tego elementu `ICorDebugModule2` .|  
|[ResolveAssembly, metoda](icordebugmodule2-resolveassembly-method.md)|Rozwiązuje zestaw, do którego odwołuje się określony token metadanych.|  
|[SetJITCompilerFlags, metoda](icordebugmodule2-setjitcompilerflags-method.md)|Ustawia flagi kontrolujące kompilację JIT dla tego elementu `ICorDebugModule2` .|  
|[SetJMCStatus — Metoda](icordebugmodule2-setjmcstatus-method.md)|Ustawia stan Tylko mój kod (JMC) dla wszystkich metod wszystkich klas w tym `ICorDebugModule2` celu do określonej wartości, z wyjątkiem tych w `pTokens` tablicy, które są ustawiane na wartość odwrotną.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
