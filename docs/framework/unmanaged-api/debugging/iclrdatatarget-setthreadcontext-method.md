---
title: ICLRDataTarget::SetThreadContext — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: c135c051637858682c22db58d562e1d50eea562b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723704"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>ICLRDataTarget::SetThreadContext — Metoda

Ustawia bieżący kontekst określonego wątku w procesie docelowym. Ta metoda jest wywoływana przez usługi dostępu do danych środowiska uruchomieniowego języka wspólnego (CLR).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `threadID`  
 podczas Identyfikator systemu operacyjnego wątku w procesie docelowym.  
  
 `contextSize`  
 podczas Rozmiar kontekstu.  
  
 `context`  
 podczas Wskaźnik do buforu zawierającego kontekst.  
  
 Dane w `context` buforze będą w formacie `CONTEXT` struktury Win32. Kontekst określa dane rejestru specyficzne dla procesora, dlatego definicja `CONTEXT` struktury Win32 zależy od architektury procesora. Zapoznaj się z plikiem nagłówkowym WinNT. h, aby uzyskać definicję `CONTEXT` struktury Win32.  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda jest implementowana przez moduł zapisujący aplikacji debugowania.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** ClrData. idl, ClrData. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRDataTarget — Interfejs](iclrdatatarget-interface.md)
