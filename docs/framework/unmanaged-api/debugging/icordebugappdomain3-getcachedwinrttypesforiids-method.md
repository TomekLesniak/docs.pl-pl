---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
ms.openlocfilehash: 2aff86fb63b87869ed13028bd7344afe11363f51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723184"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs — Metoda

Pobiera moduł wyliczający dla buforowanych środowisko wykonawcze systemu Windows typów w domenie aplikacji w oparciu o ich identyfikatory interfejsów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `cReqTypes`  
 podczas Liczba wymaganych typów.  
  
 `iidsToResolve`  
 podczas Wskaźnik do tablicy zawierającej identyfikatory interfejsów odpowiadające zarządzanym reprezentacjom typów środowisko wykonawcze systemu Windows do pobrania.  
  
 `ppTypesEnum`  
 określoną Wskaźnik do adresu obiektu interfejsu "ICorDebugTypeEnum", który umożliwia Wyliczenie buforowanych reprezentacji typów środowisko wykonawcze systemu Windows pobranych, opartych na identyfikatorach interfejsu w `iidsToResolve` .  
  
## <a name="remarks"></a>Uwagi  

 Jeśli metoda nie może pobrać informacji o określonym identyfikatorze interfejsu, odpowiadający wpis w kolekcji "ICorDebugTypeEnum" będzie miał typ `ELEMENT_TYPE_END` dla błędów spowodowany problemami z pobieraniem danych lub `ELEMENT_TYPE_VOID` nieznanymi identyfikatorami interfejsów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** środowisko wykonawcze systemu Windows  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugAppDomain3 — Interfejs](icordebugappdomain3-interface.md)
