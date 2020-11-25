---
title: CLRRuntimeHost — Klasa coclass
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
ms.openlocfilehash: 7c77cb2e89cb8fd87bf219780b9460649de19c9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731771"
---
# <a name="clrruntimehost-coclass"></a>CLRRuntimeHost — Klasa coclass

Udostępnia interfejsy umożliwiające zarządzanie wykonywaniem kodu przez środowisko uruchomieniowe.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a>Interfejsy  
  
|Interfejs|Opis|  
|---------------|-----------------|  
|[ICLRRuntimeHost — Interfejs](iclrruntimehost-interface.md)|Zapewnia metody kontrolowania wykonywania aplikacji przez środowisko uruchomieniowe.|  
|[ICLRValidator — Interfejs](iclrvalidator-interface.md)|Zapewnia metody weryfikacji przenośnych obrazów wykonywalnych i szczegółowe raportowanie błędów walidacji.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. idl  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Współklasy hostingu](hosting-coclasses.md)
