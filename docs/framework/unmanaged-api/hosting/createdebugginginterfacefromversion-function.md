---
title: CreateDebuggingInterfaceFromVersion — Funkcja
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: b68fbc713374642c9f55d49ee51a88c5785cf4b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727877"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion — Funkcja

Tworzy obiekt [ICorDebug](../debugging/icordebug-interface.md) na podstawie informacji o określonej wersji.  
  
 Ta funkcja jest przestarzała w .NET Framework 4. Zamiast tego, aby uzyskać interfejs środowiska uruchomieniowego języka wspólnego (CLR) 2,0, użyj metody [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) i określ identyfikator klasy CLSID_CLRDebuggingLegacy i identyfikator interfejsu IID_ICorDebug. Aby uzyskać interfejs dla środowiska CLR 4 lub nowszego, wywołaj funkcję [CLRCreateInstance](clrcreateinstance-function.md) i określ identyfikator klasy CLSID_CLRDebugging i identyfikator interfejsu IID_ICLRDebugging.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `iDebuggerVersion`  
 podczas Wersja programu `ICorDebug` oczekiwana przez debuger. Zapoznaj się z wyliczeniem [CorDebugInterfaceVersion —](../debugging/cordebuginterfaceversion-enumeration.md) pod kątem prawidłowych wartości.  
  
 `szDebuggeeVersion`  
 podczas Wersja środowiska uruchomieniowego języka wspólnego skojarzona z aplikacją lub procesem do debugowania. Aby uzyskać informacje na temat pobierania tej wartości, zobacz [GetVersionFromProcess —](getversionfromprocess-function.md) lub [GetRequestedRuntimeVersion —](getrequestedruntimeversion-function.md) .  
  
 `ppCordb`  
 określoną Lokalizacja, która otrzymuje wskaźnik do `ICorDebug` obiektu.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca standardowe kody błędów COM, jak zdefiniowano w pliku WinError. h, a także następujące wartości.  
  
|Kod powrotu|Opis|  
|-----------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|E_INVALIDARG|`szDebuggeeVersion` lub `ppCordb` ma wartość null lub ciąg wersji jest niepoprawny.|  
  
## <a name="remarks"></a>Uwagi  

 `szDebuggeeVersion`Parametr mapuje do odpowiedniej wersji MSCorDbi.dll.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
