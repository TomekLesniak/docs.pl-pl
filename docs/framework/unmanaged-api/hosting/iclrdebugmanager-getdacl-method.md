---
title: ICLRDebugManager::GetDacl — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.GetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type:
- apiref
ms.openlocfilehash: 8a7de5a900bc1af219924b6a83f83cf7e2ef6150
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726148"
---
# <a name="iclrdebugmanagergetdacl-method"></a>ICLRDebugManager::GetDacl — Metoda

Ta metoda nie jest zaimplementowana.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppacl`  
 określoną Wskaźnik interfejsu do listy Access Control (ACL).  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|E_NOTIMPL|Metoda nie jest zaimplementowana.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRControl — Interfejs](iclrcontrol-interface.md)
- [ICLRDebugManager — Interfejs](iclrdebugmanager-interface.md)
- [SetDacl, metoda](iclrdebugmanager-setdacl-method.md)
- [IHostControl — Interfejs](ihostcontrol-interface.md)
