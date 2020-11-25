---
title: INotifyConnection2::RegisterNotifySource — Metoda
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
ms.openlocfilehash: 1286dd970e437af0a8b607ed050ab4838f73a41f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720051"
---
# <a name="inotifyconnection2registernotifysource-method"></a>INotifyConnection2::RegisterNotifySource — Metoda

Instaluje określone źródło powiadomień.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `in_pNotifySource`  
 podczas Określa obiekt, który ma być używany jako źródło powiadomienia.  
  
 `out_ppNotifySink`  
 określoną Odbiera obiekt, który ma być używany jako ujścia powiadomień.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Zobacz także

- [INotifyConnection2 — Interfejs](inotifyconnection2-interface.md)
- [INotifySource2 — Interfejs](inotifysource2-interface.md)
- [INotifySink2 — Interfejs](inotifysink2-interface.md)
- [UnregisterNotifySource, metoda](inotifyconnection2-unregisternotifysource-method.md)
