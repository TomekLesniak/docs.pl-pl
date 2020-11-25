---
title: ICorDebugEval::NewObject — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
ms.openlocfilehash: a4d6dd0df9f38561ab5014d7ab65fde6793c9846
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729749"
---
# <a name="icordebugevalnewobject-method"></a>ICorDebugEval::NewObject — Metoda

Przydziela nowe wystąpienie obiektu i wywołuje określoną metodę konstruktora.  
  
 Ta metoda jest przestarzała w .NET Framework w wersji 2,0. Zamiast tego użyj [ICorDebugEval2:: NewParameterizedObject —](icordebugeval2-newparameterizedobject-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pConstructor`  
 podczas Konstruktor, który ma zostać wywołany.  
  
 `nArgs`  
 podczas Rozmiar `ppArgs` tablicy.  
  
 `ppArgs`  
 podczas Tablica obiektów ICorDebugValue, z których każdy reprezentuje argument, który ma zostać przesłany do konstruktora.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:** 1,1, 1,0  
  
## <a name="see-also"></a>Zobacz także

- [NewParameterizedObject, metoda](icordebugeval2-newparameterizedobject-method.md)
