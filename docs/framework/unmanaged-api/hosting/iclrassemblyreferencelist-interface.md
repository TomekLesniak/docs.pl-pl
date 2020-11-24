---
title: ICLRAssemblyReferenceList — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
ms.openlocfilehash: a75235cd0ac0e55412f0ba58881796e3ebc801f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679242"
---
# <a name="iclrassemblyreferencelist-interface"></a>ICLRAssemblyReferenceList — Interfejs

Zarządza listą zestawów, które są ładowane przez środowisko uruchomieniowe języka wspólnego (CLR), a nie przez hosta.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[IsAssemblyReferenceInList, metoda](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|Pobiera wartość wskazującą, czy dostarczony wskaźnik odwołuje się do zestawu na liście.|  
|[IsStringAssemblyReferenceInList, metoda](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|Pobiera wartość wskazującą, czy podana nazwa jest zgodna z nazwą zestawu znajdującego się na liście.|  
  
## <a name="remarks"></a>Uwagi  

 Wywołaj metodę [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList —](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) , aby uzyskać wskaźnik do wystąpienia `ICLRAssemblyReferenceList` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRAssemblyIdentityManager — Interfejs](iclrassemblyidentitymanager-interface.md)
- [IHostAssemblyStore — Interfejs](ihostassemblystore-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
