---
title: 'ICorDebugVariableSymbol:: GetName — Metoda'
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: aa3f335516f7fa22a77b786cd870f2a5064aeff5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727630"
---
# <a name="icordebugvariablesymbolgetname-method"></a>ICorDebugVariableSymbol:: GetName — Metoda

Pobiera nazwę zmiennej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `cchName`  
 podczas Liczba znaków w `szName` buforze.  
  
 `pcchName`  
 określoną Wskaźnik do liczby znaków rzeczywiście zapisywana w `szName` buforze.  
  
 `szName`  
 Wskaźnik do tablicy znaków, która zawiera nazwę zmiennej.  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugVariableSymbol, interfejs](icordebugvariablesymbol-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
