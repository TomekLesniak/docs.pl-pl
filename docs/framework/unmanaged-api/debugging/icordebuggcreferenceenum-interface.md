---
title: ICorDebugGCReferenceEnum — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: 12ce800cb83ef4f79710aa441b50be860526023c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728124"
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum — Interfejs

Dostarcza moduł wyliczający dla obiektów, które zostaną usunięte jako elementy bezużyteczne.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Next, metoda](icordebuggcreferenceenum-next-method.md)|Pobiera określoną liczbę wystąpień [COR_GC_REFERENCE](cor-gc-reference-structure.md) , które zawierają informacje o obiektach, które będą zbierane jako elementy bezużyteczne.|  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugGCReferenceEnum`Interfejs implementuje interfejs "ICorDebugEnum".  
  
 `ICorDebugGCReferenceEnum`Wystąpienie jest wypełniane wystąpieniami [COR_GC_REFERENCE](cor-gc-reference-structure.md) , wywołując metodę [ICorDebugProcess5:: EnumerateGCReferences —](icordebugprocess5-enumerategcreferences-method.md) . [COR_GC_REFERENCE](cor-gc-reference-structure.md) obiektów można wyliczyć, wywołując metodę [ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md) .  
  
 Obiekty [COR_GC_REFERENCE](cor-gc-reference-structure.md) w kolekcji wypełnione przez tę metodę reprezentują trzy rodzaje obiektów:  
  
- Obiekty ze wszystkich zarządzanych stosów. Obejmuje to dynamiczne odwołania w kodzie zarządzanym oraz obiekty utworzone przez środowisko uruchomieniowe języka wspólnego.  
  
- Obiekty z tabeli uchwytów. Obejmuje to ścisłe odwołania ( `HNDTYPE_STRONG` i `HNDTYPE_REFCOUNT` ) oraz zmienne statyczne w module.  
  
- Obiekty z kolejki finalizatora. Obiekty główne kolejki finalizatora do momentu uruchomienia finalizatora.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
