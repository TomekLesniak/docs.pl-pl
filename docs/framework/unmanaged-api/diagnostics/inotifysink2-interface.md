---
title: INotifySink2 — Interfejs
ms.date: 03/30/2017
api_name:
- INotifySink2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2
helpviewer_keywords:
- INotifySink2 interface [.NET Framework debugging]
ms.assetid: c1018789-4206-455d-aacc-2d876fc0d0bb
topic_type:
- apiref
ms.openlocfilehash: 255fe51f86157842a5807145bf7c58ae1ff5ba8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720025"
---
# <a name="inotifysink2-interface"></a>INotifySink2 — Interfejs

Deklaruje metody powiadamiania o ujściach.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[OnSyncCallEnter, metoda](inotifysink2-onsynccallenter-method.md)|Wywoływana podczas wprowadzania wywołania.|  
|[OnSyncCallExit, metoda](inotifysink2-onsynccallexit-method.md)|Wywoływany podczas kończenia wywołania.|  
|[OnSyncCallOut, metoda](inotifysink2-onsynccallout-method.md)|Wywoływana, gdy wywołanie jest wychodzące.|  
|[OnSyncCallReturn, metoda](inotifysink2-onsynccallreturn-method.md)|Wywoływany, gdy wywołanie zwraca wartość.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Zobacz także

- [INotifyConnection2 — Interfejs](inotifyconnection2-interface.md)
- [INotifySource2 — Interfejs](inotifysource2-interface.md)
- [Interfejsy magazynu symboli diagnostycznych](diagnostics-symbol-store-interfaces.md)
