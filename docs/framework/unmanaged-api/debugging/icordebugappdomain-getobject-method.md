---
title: ICorDebugAppDomain::GetObject — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
ms.openlocfilehash: a163667ea7eca1ed817d642efdb8fc4efa2a0651
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676065"
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject — Metoda

Pobiera wskaźnik interfejsu do domeny aplikacji środowiska uruchomieniowego języka wspólnego (CLR).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppObject`  
 określoną Wskaźnik do adresu obiektu interfejsu ICorDebugValue, który reprezentuje domenę aplikacji CLR.  
  
## <a name="return-value"></a>Wartość zwracana  

 Jeśli obiekt zarządzany <xref:System.AppDomain?displayProperty=nameWithType> nie został skonstruowany dla tej domeny aplikacji, metoda zwraca `S_FALSE` i umieszcza `NULL` w `*ppObject` .  
  
## <a name="remarks"></a>Uwagi  

 Każda domena aplikacji w procesie może mieć <xref:System.AppDomain?displayProperty=nameWithType> obiekt zarządzany w czasie wykonywania, który go reprezentuje. Ta funkcja pobiera obiekt interfejsu ICorDebugValue, który odpowiada obiektowi zarządzanemu <xref:System.AppDomain?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
