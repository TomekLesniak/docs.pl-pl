---
title: 'ICorDebugSymbolProvider:: GetMethodLocalSymbols, Metoda'
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: c5a21436c939ddfca0219618efe64d9e0e40aef4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730854"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a>ICorDebugSymbolProvider:: GetMethodLocalSymbols, Metoda

Pobiera symbole lokalne metody z uwzględnieniem względnego adresu wirtualnego (RVA) tej metody.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
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

- [GetMethodParameterSymbols, metoda](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [ICorDebugSymbolProvider, interfejs](icordebugsymbolprovider-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
