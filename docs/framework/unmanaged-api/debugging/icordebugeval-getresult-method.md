---
title: ICorDebugEval::GetResult — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 86c017f581c7b980b8b0cb8bd7bdc1b0aa439afe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705829"
---
# <a name="icordebugevalgetresult-method"></a>ICorDebugEval::GetResult — Metoda

Pobiera wyniki tej oceny.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppResult`  
 określoną Wskaźnik na adres obiektu ICorDebugValue, który reprezentuje wyniki tej oceny, jeśli Ocena zakończy się normalnie.  
  
## <a name="remarks"></a>Uwagi  

 `GetResult`Metoda jest prawidłowa tylko po zakończeniu obliczania.  
  
 Jeśli ocena zostanie zakończona normalnie, program `ppResult` określa wyniki. Jeśli zakończy się wyjątek, wynikiem jest zgłaszany wyjątek. Jeśli Ocena dotyczyła nowego obiektu, wynik jest odwołaniem do nowego obiektu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
