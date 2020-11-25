---
title: ICorPublish::EnumProcesses — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 297f672097dd6561a971608f368369c623532907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716918"
---
# <a name="icorpublishenumprocesses-method"></a>ICorPublish::EnumProcesses — Metoda

Pobiera moduł wyliczający dla zarządzanych procesów uruchomionych na tym komputerze.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `Type`  
 Wartość wyliczenia [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) , która określa typ procesu do pobrania. W bieżącej wersji tylko COR_PUB_MANAGEDONLY jest prawidłowy.  
  
 `ppIEnum`  
 Wskaźnik do adresu wystąpienia [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) , który jest modułem wyliczającym procesy.  
  
## <a name="remarks"></a>Uwagi  

 Kolekcja procesów modułu wyliczającego jest oparta na migawce procesów, które są uruchomione, gdy `EnumProcesses` Metoda jest wywoływana. Moduł wyliczający nie będzie zawierać żadnych procesów kończących się przed lub po `EnumProcesses` wywołaniu.  
  
 `EnumProcesses`Metoda może być wywoływana więcej niż raz w tym wystąpieniu [ICorPublish](icorpublish-interface.md) , aby utworzyć nową, aktualną kolekcję procesów. Kolejne wywołania metody nie będą miały wpływ na istniejące kolekcje `EnumProcesses` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorPub. idl, CorPub. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorPublish — Interfejs](icorpublish-interface.md)
