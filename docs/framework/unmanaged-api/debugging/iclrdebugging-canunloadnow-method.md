---
title: ICLRDebugging::CanUnloadNow — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
ms.openlocfilehash: e89d936c528ea7482487a8629dbd882f6f67483e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723574"
---
# <a name="iclrdebuggingcanunloadnow-method"></a>ICLRDebugging::CanUnloadNow — Metoda

Określa, czy biblioteka, która została dostarczona przez interfejs [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) , jest nadal używana, czy może zostać zwolniona.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a>Parametry  

 `hmodule`  
 podczas Adres podstawowy modułu w procesie docelowym.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Moduł, do którego odwołuje się program, `hmodule` może zostać zwolniony.|  
|S_FALSE|Moduł, do którego się odwołuje, `hmodule` jest nadal używany.|  
|COR_E_NOT_CLR|Wskazany moduł nie jest modułem CLR.|  
  
## <a name="exceptions"></a>Wyjątki  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda sprawdza, czy wydano wszystkie wystąpienia `ICorDebug*` interfejsów i czy żaden wątek nie znajduje się obecnie w wywołaniu metody [ICLRDebugging:: OpenVirtualProcess —](iclrdebugging-openvirtualprocess-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
