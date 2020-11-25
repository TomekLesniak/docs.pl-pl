---
title: ICorDebugMDA::GetName — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
ms.openlocfilehash: 516fcf8a97b92eac8dfff9eae34199caa97c2d2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710938"
---
# <a name="icordebugmdagetname-method"></a>ICorDebugMDA::GetName — Metoda

Pobiera ciąg zawierający nazwę zarządzanego asystenta debugowania (MDA) reprezentowanego przez [ICorDebugMDA](icordebugmda-interface.md).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `cchName`  
 podczas Rozmiar `szName` tablicy.  
  
 `pcchName`  
 określoną Wskaźnik do długości nazwy.  
  
 `szName`  
 określoną Tablica, w której ma zostać przechowana nazwa.  
  
## <a name="remarks"></a>Uwagi  

 Nazwy MDA są unikatowymi wartościami. `GetName`Metoda jest wygodną alternatywą wydajności dla pobierania strumienia XML i wyodrębniania nazwy ze strumienia na podstawie schematu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugMDA — Interfejs](icordebugmda-interface.md)
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
