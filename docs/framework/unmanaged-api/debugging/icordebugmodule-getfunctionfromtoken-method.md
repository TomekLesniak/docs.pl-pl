---
title: ICorDebugModule::GetFunctionFromToken — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
ms.openlocfilehash: bf2acd897c9c45e445b864f85550ed7ed6e00886
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710158"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>ICorDebugModule::GetFunctionFromToken — Metoda

Pobiera funkcję określoną przez token metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `methodDef`  
 podczas `mdMethodDef` Token metadanych, który odwołuje się do metadanych funkcji.  
  
 `ppFunction`  
 określoną Wskaźnik do adresu obiektu interfejsu ICorDebugFunction, który reprezentuje funkcję.  
  
## <a name="remarks"></a>Uwagi  

 `GetFunctionFromToken`Metoda zwraca CORDBG_E_FUNCTION_NOT_IL HRESULT, jeśli przeniesiona wartość nie `methodDef` odwołuje się do metody MSIL (Microsoft pośredni Language).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
