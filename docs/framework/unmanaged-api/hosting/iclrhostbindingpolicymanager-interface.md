---
title: ICLRHostBindingPolicyManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 49d1ee4dd0965d4ae5b54b53208809cfbdf7e718
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725636"
---
# <a name="iclrhostbindingpolicymanager-interface"></a>ICLRHostBindingPolicyManager — Interfejs

Dostarcza metody dla hosta do szacowania bieżących zasad powiązań i przekazywania zmian zasad dla określonego zestawu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[EvaluatePolicy, metoda](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|Oblicza zasady powiązań w imieniu hosta.|  
|[ModifyApplicationPolicy, metoda](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|Modyfikuje zasady powiązań dla określonego zestawu i tworzy nową wersję zasad.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRAssemblyIdentityManager — Interfejs](iclrassemblyidentitymanager-interface.md)
- [IHostAssemblyStore — Interfejs](ihostassemblystore-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
