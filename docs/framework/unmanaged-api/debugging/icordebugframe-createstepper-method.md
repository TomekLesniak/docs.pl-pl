---
title: ICorDebugFrame::CreateStepper — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 5dfb64d0c440cbd2c8a8a65b2c18d78f02a7615e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679718"
---
# <a name="icordebugframecreatestepper-method"></a>ICorDebugFrame::CreateStepper — Metoda

Pobiera stepper, który umożliwia debugerowi wykonywanie operacji krokowych względem tego ICorDebugFrame.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppStepper`  
 określoną Wskaźnik do adresu obiektu ICorDebugStepper, który umożliwia debugerowi wykonywanie operacji krokowe względem bieżącej ramki.  
  
## <a name="remarks"></a>Uwagi  

 Jeśli ramka nie jest aktywna, obiekt stepper zazwyczaj będzie musiał powrócić do ramki przed ukończeniem kroku.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
