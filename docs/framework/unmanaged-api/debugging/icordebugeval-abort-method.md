---
title: ICorDebugEval::Abort — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: 6e6ea5e42c5e1b1943a080ae02e1dbf6d702bebc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705855"
---
# <a name="icordebugevalabort-method"></a>ICorDebugEval::Abort — Metoda

Przerywa obliczenia wykonywane przez ten obiekt ICorDebugEval.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a>Uwagi  

 Jeśli ocena jest zagnieżdżona i nie jest to najnowsza z nich, `Abort` Metoda może zakończyć się niepowodzeniem.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
