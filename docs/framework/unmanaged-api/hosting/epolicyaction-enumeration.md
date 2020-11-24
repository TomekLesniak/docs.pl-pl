---
title: EPolicyAction — Wyliczenie
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: 72b371d72b2f055f2840da5595d9022ffd7e2507
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674752"
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction — Wyliczenie

Opisuje akcje zasad, które host może ustawić dla operacji opisanych przez [EClrOperation —](eclroperation-enumeration.md) i błędy opisane przez [EClrFailure —](eclrfailure-enumeration.md).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`eAbortThread`|Określa, że środowisko uruchomieniowe języka wspólnego (CLR) powinno bezpiecznie przerwać wątek. Bezpieczne przerywanie obejmuje próby uruchomienia wszystkich `finally` bloków, wszelkich `catch` bloków związanych z przerwami wątków i finalizatorów.|  
|`eDisableRuntime`|Określa, że środowisko CLR ma wejść w stan wyłączony. Żaden kod zarządzany nie może być wykonywany w odpowiednim procesie, a wątki są blokowane przed wprowadzeniem środowiska CLR.|  
|`eExitProcess`|Określa, że środowisko CLR ma próbować bezpiecznie wyjść z procesu, w tym uruchamiania finalizatorów i wykonywania operacji czyszczenia i rejestrowania.|  
|`eFastExitProcess`|Określa, że środowisko CLR powinno zakończyć proces natychmiast, bez uruchamiania finalizatorów lub wykonywania operacji czyszczenia i rejestrowania. Powiadomienia są jednak wysyłane do debugera.|  
|`eNoAction`|Określa, że żadna akcja nie powinna być wykonywana.|  
|`eRudeAbortThread`|Określa, że środowisko CLR ma wykonać przerwanie wątku prosta. Tylko te `catch` i `finally` bloki oznaczone za pomocą <xref:System.EnterpriseServices.MustRunInClientContextAttribute> są wykonywane.|  
|`eRudeExitProcess`|Określa, że środowisko CLR ma wyjść z procesu bez uruchamiania finalizatorów lub operacji rejestrowania.|  
|`eRudeUnloadAppDomain`|Określa, że środowisko CLR ma wykonać prosta zwolnienie z programu <xref:System.AppDomain> . Tylko finalizatory oznaczone jako with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> są wykonywane. Podobnie wszystkie wątki z tym elementem <xref:System.AppDomain> w ich stosie odbierają `ThreadAbortException` , ale tylko te `catch` i `finally` bloki oznaczone jako with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> są wykonywane.|  
|`eThrowException`|Określa, że wyjątek odpowiedni dla warunku, taki jak braku pamięci, przepełnienie buforu i tak dalej, powinien zostać wygenerowany.|  
|`eUnloadAppDomain`|Określa, że <xref:System.AppDomain> powinny być zwolnione. Środowisko CLR próbuje uruchomić finalizatorów.|  
  
## <a name="remarks"></a>Uwagi  

 Host ustawia akcje zasad przez wywołanie metod interfejsu [ICLRPolicyManager](iclrpolicymanager-interface.md) . Aby uzyskać informacje na temat prosta i łagodnego przerwania, zobacz Wyliczenie [EClrOperation —](eclroperation-enumeration.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [EClrFailure — Wyliczenie](eclrfailure-enumeration.md)
- [ICLRPolicyManager — Interfejs](iclrpolicymanager-interface.md)
- [IHostPolicyManager — Interfejs](ihostpolicymanager-interface.md)
- [Hosting — Wyliczenia](hosting-enumerations.md)
