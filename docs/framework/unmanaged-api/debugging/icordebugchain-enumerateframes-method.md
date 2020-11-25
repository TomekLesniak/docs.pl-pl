---
title: ICorDebugChain::EnumerateFrames — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: ae6d81e6fdab0f8e3346d8a08a3b5ebc329a542a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730152"
---
# <a name="icordebugchainenumerateframes-method"></a>ICorDebugChain::EnumerateFrames — Metoda

Pobiera moduł wyliczający, który zawiera wszystkie zarządzane ramki stosu w łańcuchu, rozpoczynając od ostatniej ramki.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppFrames`  
 określoną Wskaźnik do adresu obiektu ICorDebugFrameEnum, który jest modułem wyliczającym dla ramek stosu.  
  
## <a name="remarks"></a>Uwagi  

 Łańcuch reprezentuje stos wywołań fizycznych wątku.  
  
 `EnumerateFrames`Metoda powinna być wywoływana tylko dla łańcuchów zarządzanych. Interfejs API debugowania nie udostępnia metod uzyskiwania ramek zawartych w łańcuchach niezarządzanych. Aby uzyskać te informacje, debuger musi użyć innych metod.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
