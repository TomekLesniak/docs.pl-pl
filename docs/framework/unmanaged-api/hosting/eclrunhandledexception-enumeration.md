---
title: EClrUnhandledException — Wyliczenie
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: bccd44e1bead4feadf67929dc104557715904577
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686465"
---
# <a name="eclrunhandledexception-enumeration"></a>EClrUnhandledException — Wyliczenie

Opisuje dostępne opcje zarządzania wyjątkami, które nie są obsługiwane w kodzie użytkownika.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|Określa, że występuje zachowanie domyślne. Proces został rozdarty.|  
|`eHostDeterminedPolicy`|Określa, że środowisko uruchomieniowe języka wspólnego (CLR) ignoruje Nieobsłużone wyjątki i umożliwia hostowi określenie dalszych akcji.|  
  
## <a name="remarks"></a>Uwagi  

 Aby określić, że środowisko CLR zachowuje się jak wcześniejsze wersje, użyj `eHostDeterminedPolicy` elementu członkowskiego.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [EClrFailure — Wyliczenie](eclrfailure-enumeration.md)
- [EClrOperation — Wyliczenie](eclroperation-enumeration.md)
- [ICLRPolicyManager — Interfejs](iclrpolicymanager-interface.md)
- [SetUnhandledExceptionPolicy, metoda](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [IHostPolicyManager — Interfejs](ihostpolicymanager-interface.md)
- [Hosting — Wyliczenia](hosting-enumerations.md)
