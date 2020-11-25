---
title: 'ICorDebugMemoryBuffer:: GetSize — metoda'
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 7f5458dd12ca83c1a5190bbf7fab0f8e5d06a0e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710765"
---
# <a name="icordebugmemorybuffergetsize-method"></a>ICorDebugMemoryBuffer:: GetSize — metoda

Pobiera rozmiar buforu pamięci w bajtach.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pcbBufferLength`  
 określoną Wskaźnik do rozmiaru bufora pamięci.  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugMemoryBuffer, interfejs](icordebugmemorybuffer-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
