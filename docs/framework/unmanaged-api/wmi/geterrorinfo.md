---
title: GetErrorInfo — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja GetErrorInfo pobiera informacje o błędzie z poprzedniego wywołania funkcji.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5da4eaa459c515689b822e4cb537380245e800e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722768"
---
# <a name="geterrorinfo-function"></a>GetErrorInfo — funkcja

Pobiera informacje o błędzie z poprzedniego wywołania funkcji.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Składnia  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) , jeśli wywołanie funkcji zakończy się pomyślnie lub `null` nie powiedzie się.
  
## <a name="remarks"></a>Uwagi

Ta funkcja otacza wywołanie metody [IComThreadingInfo:: GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .

## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** WMINet_Utils. def  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Zobacz także

- [WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)](index.md)
