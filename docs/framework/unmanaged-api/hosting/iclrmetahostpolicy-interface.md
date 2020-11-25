---
title: ICLRMetaHostPolicy — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 515b73b019c683bd3e5aa3b895ee5623e75e4ad0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707610"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy — Interfejs

Udostępnia metodę [GetRequestedRuntime —](iclrmetahostpolicy-getrequestedruntime-method.md) , która zwraca wskaźnik do interfejsu środowiska uruchomieniowego języka wspólnego (CLR) na podstawie kryteriów zasad, zestawu zarządzanego, wersji i pliku konfiguracji.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetRequestedRuntime, metoda](iclrmetahostpolicy-getrequestedruntime-method.md)|Udostępnia preferowany interfejs CLR na podstawie kryteriów zasad, zestawu zarządzanego, wersji i pliku konfiguracji.|  
  
## <a name="remarks"></a>Uwagi  

 Odwołanie do tego interfejsu można uzyskać, wywołując funkcję [CLRCreateInstance](clrcreateinstance-function.md) , jak pokazano w poniższym kodzie:  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> Ten interfejs nie ładuje ani nie aktywuje środowiska CLR, ale po prostu zwraca preferowaną wersję środowiska CLR na podstawie dostępnych wersji zainstalowanych lub załadowanych.  
  
 Interfejs API hostingu .NET Framework 4 konsoliduje zasady tak, aby hosty z konkretnymi potrzebami mogły korzystać z podstawowych funkcji bez ponoszenia niezamierzonych kar. Na przykład wiele eksportów MSCorEE.dll zostanie powiązana z określonym środowiskiem CLR, chociaż Metoda może nie być logicznie wymagana. Wyliczenie [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) zawiera zasady powiązań, które są wspólne dla większości hostów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy hostingu środowiska CLR dodane w programie .NET Framework 4 i 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
- [Hosting](index.md)
