---
title: CreateCordbObject — Funkcja
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: eccdfcb60b2d2b5d652ccac948c01c16e7cb828d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725979"
---
# <a name="createcordbobject-function"></a>CreateCordbObject — Funkcja

Tworzy interfejs debugera ([ICorDebug](icordebug-interface.md)), który zapewnia funkcję tworzenia wystąpienia zarządzanej sesji debugowania w procesie zdalnym.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `iDebuggerVersion`  
 podczas Wersja debugera procesu docelowego. Ten parametr musi być CorDebugVersion_2_0 dla zdalnego debugowania.  
  
 `ppCordb`  
 określoną Wskaźnik na wskaźnik do obiektu, który będzie rzutowany do interfejsu [ICorDebug](icordebug-interface.md) i zwrócony.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK  
 Liczba CLRs w procesie została pomyślnie określona, a odpowiednie tablice uchwytów i ścieżek zostały prawidłowo wypełnione.  
  
 E_INVALIDARG  
 `ppCordb` ma wartość null lub `iDebuggerVersion` nie jest CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 Nie można przydzielić wystarczającej ilości pamięci dla `ppCordb`  
  
 E_FAIL (lub inne kody powrotne E_)  
 Inne błędy.  
  
## <a name="remarks"></a>Uwagi  

 Interfejs [ICorDebug](icordebug-interface.md) , który jest zwracany w programie `ppCordb` , jest interfejsem debugowania najwyższego poziomu dla wszystkich zarządzanych usług debugowania.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteka:** mscordbi_macx86.dll  
  
 **.NET Framework wersje:** 3,5 SP1
