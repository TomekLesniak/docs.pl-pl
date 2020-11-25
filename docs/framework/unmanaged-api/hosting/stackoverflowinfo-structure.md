---
title: StackOverflowInfo — Struktura
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: a8a57cfcaf36949d4d10c6ec267a5f55a2aee5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729931"
---
# <a name="stackoverflowinfo-structure"></a>StackOverflowInfo — Struktura

Przechowuje typ przepełnienia, który wystąpił, i informacje o wyjątku, który został zgłoszony z powodu przepełnienia.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`soType`|Wartość wyliczenia [StackOverflowType —](stackoverflowtype-enumeration.md) , która określa typ przepełnienia.|  
|`pExceptionInfo`|Wskaźnik do `EXCEPTION_POINTERS` obiektu Win32, który zawiera rekord wyjątku z niezależnym od maszyny opisem wyjątku i rekordu kontekstu z opisem zależnym od maszyny w momencie wystąpienia wyjątku.|  
  
## <a name="remarks"></a>Uwagi  

 `StackOverflowInfo`Obiekt jest przesyłany do metody [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) dla `Event_StackOverflow` zdarzeń.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. idl  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Hosting — Struktury](hosting-structures.md)
