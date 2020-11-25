---
title: ICorDebugClass::GetStaticFieldValue — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
ms.openlocfilehash: dd1608badf553650b05b7de98d9bbcd76b2f3edf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728436"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a>ICorDebugClass::GetStaticFieldValue — Metoda

Pobiera wartość określonego pola statycznego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `fieldDef`  
 podczas Token pola `Def` , który odwołuje się do pola, które ma zostać pobrane.  
  
 `pFrame`  
 podczas Wskaźnik do obiektu ICorDebugFrame, który reprezentuje ramkę, która ma zostać użyta do rozróżnienia między elementem statycznym, kontekstowym lub domeną aplikacji.  
  
 Jeśli pole statyczne jest powiązane z wątkiem, kontekstem lub domeną aplikacji, ramka będzie określać odpowiednią wartość.  
  
 `ppValue`  
 określoną Wskaźnik do adresu obiektu ICorDebugValue, który reprezentuje wartość pola statycznego.  
  
## <a name="remarks"></a>Uwagi  

 W przypadku typów sparametryzowanych wartość pola statycznego jest określana względem konkretnego wystąpienia. W związku z tym, jeśli Konstruktor klasy przyjmuje parametry typu <xref:System.Type> , należy wywołać [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) zamiast `ICorDebugClass::GetStaticFieldValue` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
