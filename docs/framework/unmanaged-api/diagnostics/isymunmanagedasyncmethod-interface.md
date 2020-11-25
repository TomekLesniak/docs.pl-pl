---
title: ISymUnmanagedAsyncMethod — Interfejs
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 02b1866f2b9e89cdc8c8795f399ecc0c733c7202
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707168"
---
# <a name="isymunmanagedasyncmethod-interface"></a>ISymUnmanagedAsyncMethod — Interfejs

Ten interfejs jest uzupełnieniem odczytu do [interfejsu ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
## <a name="syntax"></a>Składnia  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a>Metody  

 Ten interfejs zawiera następujące metody:  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetAsyncStepInfo, metoda](isymunmanagedasyncmethod-getasyncstepinfo-method.md)|Zobacz [DefineAsyncStepInfo —](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).|  
|[GetAsyncStepInfoCount, metoda](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|Zobacz [DefineAsyncStepInfo —](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).|  
|[GetCatchHandlerILOffset, metoda](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|Zobacz [DefineCatchHandlerILOffset —](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).|  
|[GetKickoffMethod, metoda](isymunmanagedasyncmethod-getkickoffmethod-method.md)|Zobacz [DefineKickoffMethod —](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).|  
|[HasCatchHandlerILOffset, metoda](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|Zobacz [DefineCatchHandlerILOffset —](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).|  
|[IsAsyncMethod, metoda](isymunmanagedasyncmethod-isasyncmethod-method.md)|Sprawdza, czy metoda ma informacje asynchroniczne, czy nie.<br /><br /> Jeśli ta metoda zwróci wartość `FALSE` , jest ona nieprawidłowa do wywołania innych metod w tym interfejsie. Wszystkie zwracają `E_UNEXPECTED` w tym przypadku.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy magazynu symboli diagnostycznych](diagnostics-symbol-store-interfaces.md)
