---
title: ICLRDataTarget::GetThreadContext — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 35b7bff5d4d778a429ddc1dcd0206e6e8970ee4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703502"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>ICLRDataTarget::GetThreadContext — Metoda

Pobiera bieżący kontekst wykonania dla danego wątku w procesie docelowym. Ta metoda jest wywoływana przez usługi dostępu do danych środowiska uruchomieniowego języka wspólnego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `threadID`  
 podczas Identyfikator systemu operacyjnego wątku w procesie docelowym.  
  
 `contextFlags`  
 podczas Flagi określające, które części kontekstu mają być zwracane. Implementacja zwróci co najmniej te części kontekstu.  
  
 `contextSize`  
 podczas Rozmiar kontekstu.  
  
 `context`  
 określoną Wskaźnik do buforu, w którym ma zostać umieszczony kontekst.  
  
 Dane w `context` buforze muszą mieć format `CONTEXT` struktury Win32. Kontekst określa dane rejestru specyficzne dla procesora, dlatego definicja `CONTEXT` struktury Win32 zależy od architektury procesora. Zapoznaj się z plikiem nagłówkowym WinNT. h, aby uzyskać definicję `CONTEXT` struktury Win32.  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda jest implementowana przez moduł zapisujący aplikacji debugowania.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** ClrData. idl, ClrData. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRDataTarget — Interfejs](iclrdatatarget-interface.md)
