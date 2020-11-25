---
title: ICorDebugType::GetFirstTypeParameter — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
ms.openlocfilehash: be69636056d5510b72dbce39917f5e8d3b05cd87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723977"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a>ICorDebugType::GetFirstTypeParameter — Metoda

Pobiera wskaźnik interfejsu do ICorDebugType, który reprezentuje pierwszy <xref:System.Type> parametr typu reprezentowanego przez ten element `ICorDebugType` .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `value`  
 określoną Wskaźnik do adresu `ICorDebugType` obiektu, który reprezentuje pierwszy parametr.  
  
## <a name="remarks"></a>Uwagi  

 `GetFirstTypeParameter` może być wywoływana w przypadkach, gdy dodatkowe informacje o typie obejmują, co najwyżej jeden parametr typu. W szczególności można go użyć, jeśli typ jest ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF lub ELEMENT_TYPE_PTR, zgodnie z opisem przez metodę [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
