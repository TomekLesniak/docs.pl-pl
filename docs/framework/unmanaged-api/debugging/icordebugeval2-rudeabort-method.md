---
title: ICorDebugEval2::RudeAbort — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
ms.openlocfilehash: 478772925dfb7ca7389b5267433f9b06ace3d5a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729619"
---
# <a name="icordebugeval2rudeabort-method"></a>ICorDebugEval2::RudeAbort — Metoda

Przerywa obliczenia, które `ICorDebugEval2` jest aktualnie wykonywane.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a>Uwagi  

 `RudeAbort` nie zwalnia żadnych blokad, które są przechowywane przez ewaluatora, dlatego sesja debugowania jest pozostawiana w stanie niebezpiecznym. Wywołaj tę metodę z największą ostrożnością.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
