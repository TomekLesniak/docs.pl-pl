---
title: ICorDebugAppDomain, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
ms.openlocfilehash: 98273a5d4602c023863758045bdb2a6a502ba7a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687232"
---
# <a name="icordebugappdomain-interface"></a>ICorDebugAppDomain, interfejs

Dostarcza metody do debugowania domen aplikacji. Ten interfejs jest podklasą elementu ICorDebugController.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Attach, metoda](icordebugappdomain-attach-method.md)|Dołącza debuger do domeny aplikacji.|  
|[EnumerateAssemblies, metoda](icordebugappdomain-enumerateassemblies-method.md)|Pobiera moduł wyliczający dla zestawów w domenie aplikacji.|  
|[EnumerateBreakpoints, metoda](icordebugappdomain-enumeratebreakpoints-method.md)|Pobiera moduł wyliczający dla wszystkich aktywnych punktów przerwania w domenie aplikacji.|  
|[EnumerateSteppers, metoda](icordebugappdomain-enumeratesteppers-method.md)|Pobiera moduł wyliczający dla wszystkich aktywnych współdziałań w domenie aplikacji.|  
|[GetId —, Metoda](icordebugappdomain-getid-method.md)|Pobiera unikatowy identyfikator domeny aplikacji.|  
|[GetModuleFromMetaDataInterface, metoda](icordebugappdomain-getmodulefrommetadatainterface-method.md)|Pobiera obiekt ICorDebugModule z danym interfejsem metadanych.|  
|[GetName — Metoda](icordebugappdomain-getname-method.md)|Pobiera nazwę domeny aplikacji.|  
|[GetObject — Metoda](icordebugappdomain-getobject-method.md)|Pobiera wskaźnik interfejsu do domeny aplikacji środowiska uruchomieniowego języka wspólnego (CLR).|  
|[GetProcess — Metoda](icordebugappdomain-getprocess-method.md)|Pobiera proces zawierający domenę aplikacji.|  
|[IsAttached, metoda](icordebugappdomain-isattached-method.md)|Określa, czy debuger jest dołączony do domeny aplikacji.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
