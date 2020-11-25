---
title: ICorDebugFunction::GetILCode — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
ms.openlocfilehash: b7d3fbafaab6d43fa89d45855628dbd6b9ab81e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696222"
---
# <a name="icordebugfunctiongetilcode-method"></a>ICorDebugFunction::GetILCode — Metoda

Pobiera wystąpienie ICorDebugCode, które reprezentuje kod języka pośredniego firmy Microsoft (MSIL) skojarzony z tym obiektem ICorDebugFunction.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppCode`  
 określoną Wskaźnik do `ICorDebugCode` wystąpienia lub wartość null, jeśli funkcja nie została skompilowana do MSIL.  
  
## <a name="remarks"></a>Uwagi  

 Jeśli funkcja Edytuj i Kontynuuj jest dozwolona dla tej funkcji, `GetILCode` metoda pobierze kod MSIL odpowiadający edytowanej wersji kodu w środowisku uruchomieniowym języka wspólnego (CLR).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
