---
title: ICorDebugHeapValue2::CreateHandle — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: 278120c6e1bc87a061a3f81f71bdb7b89cd421be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726564"
---
# <a name="icordebugheapvalue2createhandle-method"></a>ICorDebugHeapValue2::CreateHandle — Metoda

Tworzy dojście określonego typu dla wartości sterty reprezentowanej przez ten obiekt ICorDebugHeapValue2.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `type`  
 podczas Wartość wyliczenia CorDebugHandleType —, która określa typ dojścia do utworzenia.  
  
 `ppHandle`  
 określoną Wskaźnik do adresu obiektu ICorDebugHandleValue, który reprezentuje nowe dojście dla tej wartości sterty.  
  
## <a name="remarks"></a>Uwagi  

 Dojście zostanie utworzone w domenie aplikacji skojarzonej z wartością sterty i stanie się nieprawidłowe, jeśli domena aplikacji zostanie zwolniona z ładowania.  
  
 Wielokrotne wywołania tej funkcji dla tej samej wartości sterty spowodują utworzenie wielu dojść. Ponieważ uchwyty wpływają na wydajność modułu wyrzucania elementów bezużytecznych, debuger powinien ograniczyć się do stosunkowo niewielkiej liczby dojść (około 256), które są aktywne w danym momencie.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
