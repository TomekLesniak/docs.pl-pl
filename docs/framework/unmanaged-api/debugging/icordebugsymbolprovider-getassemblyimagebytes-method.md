---
title: 'ICorDebugSymbolProvider:: GetAssemblyImageBytes, Metoda'
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: b52614065d599edf8e556524c33e8bc50b4924ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709183"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a>ICorDebugSymbolProvider:: GetAssemblyImageBytes, Metoda

Odczytuje dane z scalonego zestawu, uwzględniając względny adres wirtualny (RVA) w scalonym zestawie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `rva`  
 podczas Względny adres wirtualny (RVA) w scalonym zestawie.  
  
 `length`  
 Liczba bajtów do odczytania ze scalonego zestawu.  
  
 `ppMemoryBuffer`  
 Wskaźnik do adresu obiektu [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) , który zawiera informacje o buforze pamięci ze scalonymi metadanymi zestawu.  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugSymbolProvider, interfejs](icordebugsymbolprovider-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
