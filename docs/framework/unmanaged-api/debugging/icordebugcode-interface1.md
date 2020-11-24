---
title: ICorDebugCode, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
ms.openlocfilehash: 03cbc1a598ba6c0166f72ff404c239763956c996
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687609"
---
# <a name="icordebugcode-interface"></a>ICorDebugCode, interfejs

Reprezentuje segment kodu języka pośredniego firmy Microsoft (MSIL) lub kodu natywnego.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[CreateBreakpoint — Metoda](icordebugcode-createbreakpoint-method.md)|Tworzy punkt przerwania w określonym przesunięciu.|  
|[GetAddress — Metoda](icordebugcode-getaddress-method.md)|Pobiera względny adres wirtualny (RVA) segmentu kodu, który `ICorDebugCode` reprezentuje.|  
|[GetCode, metoda](icordebugcode-getcode-method.md)|Pobiera cały kod dla określonej funkcji, sformatowany pod kątem demontażu. Ta metoda jest przestarzała; Zamiast tego użyj [ICorDebugCode2:: GetCodeChunks —](icordebugcode2-getcodechunks-method.md) .|  
|[GetEnCRemapSequencePoints, metoda](icordebugcode-getencremapsequencepoints-method.md)|Nie zaimplementowano.|  
|[GetFunction, metoda](icordebugcode-getfunction-method.md)|Pobiera wartość "ICorDebugFunction" skojarzoną z tym elementem `ICorDebugCode` .|  
|[GetILToNativeMapping, metoda](icordebugcode-getiltonativemapping-method.md)|Pobiera tablicę wystąpień "COR_DEBUG_IL_TO_NATIVE_MAP", które reprezentują mapowania z przesunięć MSIL do natywnych przesunięć.|  
|[GetSize — Metoda](icordebugcode-getsize-method.md)|Pobiera rozmiar (w bajtach) kodu binarnego reprezentowanego przez ten element `ICorDebugCode` .|  
|[GetVersionNumber — Metoda](icordebugcode-getversionnumber-method.md)|Pobiera jednostronicowy numer identyfikujący wersję kodu, który `ICorDebugCode` reprezentuje.|  
|[IsIL, metoda](icordebugcode-isil-method.md)|Pobiera wartość wskazującą, czy jest ona `ICorDebugCode` kompilowana w MSIL.|  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugCode` może reprezentować kod MSIL lub natywny. Obiekt "ICorDebugFunction", który reprezentuje kod MSIL, może mieć `ICorDebugCode` skojarzone z nim zero lub jeden obiekt. Obiekt "ICorDebugFunction" reprezentujący kod natywny może zawierać dowolną liczbę `ICorDebugCode` obiektów skojarzonych z nim.  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugCode3 — Interfejs](icordebugcode3-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
