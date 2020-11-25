---
title: 'ICorDebugSymbolProvider:: GetMethodParameterSymbols, Metoda'
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
ms.openlocfilehash: 95b7b61087f3d3fddab36b7835a633534c223b72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730841"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a>ICorDebugSymbolProvider:: GetMethodParameterSymbols, Metoda

Pobiera symbole parametrów metody z uwzględnieniem względnego adresu wirtualnego (RVA) tej metody.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `nativeRVA`  
 podczas Natywny względny adres wirtualny metody.  
  
 `cRequestedSymbols`  
 podczas Liczba żądanych symboli lokalnych.  
  
 `pcFetchedSymbols`  
 określoną Wskaźnik do liczby symboli pobranych przez metodę.  
  
 `pcFetchedSymbols`  
 określoną Wskaźnik do tablicy [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) zawierającej symbole lokalne metody.  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [GetMethodLocalSymbols, metoda](icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [ICorDebugSymbolProvider, interfejs](icordebugsymbolprovider-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
