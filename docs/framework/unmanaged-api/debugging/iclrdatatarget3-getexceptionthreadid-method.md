---
title: Metoda ICLRDataTarget3::GetExceptionThreadID
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
ms.openlocfilehash: 0a8b7a90cd909379f870f6a501a940386d2e1451
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723600"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a>Metoda ICLRDataTarget3::GetExceptionThreadID

Wywoływane przez usługi dostępu do danych środowiska uruchomieniowego języka wspólnego (CLR), aby uzyskać identyfikator wątku, który wywołał wyjątek.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `threadID`  
 określoną Identyfikator wątku, który wywołał wyjątek.  
  
## <a name="return-value"></a>Wartość zwracana  

 Wartość zwracana jest `S_OK` w przypadku powodzenia lub `HRESULT` Kod błędu w przypadku niepowodzenia. `HRESULT`Kody mogą zawierać, ale nie są ograniczone do następujących:  
  
|Kod powrotu|Opis|  
|-----------------|-----------------|  
|`S_OK`|Metoda powiodła się.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Nie można znaleźć prawidłowego identyfikatora wątku dla wyjątku.|  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda jest implementowana przez moduł zapisujący aplikacji debugowania.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** ClrData. idl, ClrData. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRDataTarget3 — Interfejs](iclrdatatarget3-interface.md)
- [GetExceptionContextRecord, metoda](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [GetExceptionRecord, metoda](iclrdatatarget3-getexceptionrecord-method.md)
