---
title: 'ICorDebugSymbolProvider:: GetInstanceFieldSymbols, Metoda'
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 1a74b355b695f65166d0fe63bbdd41d789db5cfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730867"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a>ICorDebugSymbolProvider:: GetInstanceFieldSymbols, Metoda

Pobiera symbole pól wystąpienia, które odpowiadają sygnaturze elementu TypeSpec.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `cbSignature`  
 podczas Liczba bajtów w `typeSig` tablicy.  
  
 `typeSig`  
 podczas Tablica bajtów, która zawiera `typespec` sygnaturę.  
  
 `cRequestedSymbols`  
 podczas Żądana liczba symboli.  
  
 `pcFetchedSymbols`  
 określoną Wskaźnik do liczby symboli pobranych przez metodę.  
  
 `pSymbols`  
 określoną Wskaźnik do tablicy [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) , która zawiera żądane symbole pola wystąpienia.  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [GetStaticFieldSymbols, metoda](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [ICorDebugSymbolProvider, interfejs](icordebugsymbolprovider-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
