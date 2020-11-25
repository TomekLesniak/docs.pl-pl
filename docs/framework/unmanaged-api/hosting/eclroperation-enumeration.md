---
title: EClrOperation — Wyliczenie
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
ms.openlocfilehash: c24e4557695d26666682ee385131abaab707a24d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720714"
---
# <a name="eclroperation-enumeration"></a>EClrOperation — Wyliczenie

Opisuje zestaw operacji, dla których host może stosować akcje zasad.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|Host może określać akcje zasad, które mają zostać podjęte, gdy <xref:System.AppDomain> zostanie zwolniony w sposób niebezpieczny (prosta).|  
|`OPR_AppDomainUnload`|Host może określać akcje zasad, które mają zostać wykonane po <xref:System.AppDomain> zakończeniu ładowania.|  
|`OPR_FinalizerRun`|Host może określać akcje zasad, które mają być podejmowane po uruchomieniu finalizatorów.|  
|`OPR_ProcessExit`|Host może określić akcje zasad, które mają zostać wykonane po zakończeniu procesu.|  
|`OPR_ThreadAbort`|Host może określać akcje zasad, które mają być podejmowane w przypadku przerwania wątku.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Host może określać akcje zasad, które mają być podejmowane w przypadku przerwania wątku prosta w krytycznym regionie kodu.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Host może określać akcje zasad, które mają być podejmowane po przerwaniu wątku prosta w niekrytycznym regionie kodu.|  
  
## <a name="remarks"></a>Uwagi  

 Infrastruktura niezawodności aparatu plików wykonywalnych języka wspólnego (CLR) odróżnia między przerwami a błędami alokacji zasobów, które występują w krytycznych regionach kodu i tych, które występują w niekrytycznych regionach kodu. Ta różnica została zaprojektowana tak, aby umożliwić hostom Ustawianie różnych zasad w zależności od tego, gdzie wystąpi błąd w kodzie.  
  
 *Krytyczny region kodu* jest dowolnym miejscem, w którym środowisko CLR nie może zagwarantować, że przerywanie zadania lub niepowodzenie żądania dla zasobów będzie wpływać tylko na bieżące zadanie. Na przykład, jeśli zadanie utrzymuje blokadę i otrzymuje wynik HRESULT wskazujący błąd podczas tworzenia żądania alokacji pamięci, to nie wystarczy po prostu przerwać to zadanie, aby zapewnić stabilność <xref:System.AppDomain> , ponieważ <xref:System.AppDomain> może zawierać inne zadania oczekujące na tę samą blokadę. Aby porzucić bieżące zadanie, może spowodować, że te inne zadania przestaną odpowiadać. W takim przypadku host musi mieć możliwość zwolnienia całości, <xref:System.AppDomain> a nie ryzyka potencjalnej niestabilności.  
  
 *Niekrytyczny region kodu*, z drugiej strony, to region, w którym środowisko CLR może zagwarantować, że przerwanie lub awaria będzie wpływać tylko na zadanie, na którym wystąpi błąd.  
  
 Środowisko CLR rozróżnia również łagodne i niebezpieczne przerwania (prosta). Ogólnie rzecz biorąc, normalne lub bezpieczne przerwanie podejmuje wszelkie wysiłki, aby uruchomić procedury obsługi wyjątków i finalizatory przed przerwaniem zadania, podczas gdy przerwanie prosta nie daje takich gwarancji.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [EClrFailure — Wyliczenie](eclrfailure-enumeration.md)
- [EPolicyAction — Wyliczenie](epolicyaction-enumeration.md)
- [ICLRPolicyManager — Interfejs](iclrpolicymanager-interface.md)
- [IHostPolicyManager — Interfejs](ihostpolicymanager-interface.md)
- [Hosting — Wyliczenia](hosting-enumerations.md)
