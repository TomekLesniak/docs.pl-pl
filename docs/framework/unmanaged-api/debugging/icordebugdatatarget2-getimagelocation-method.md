---
title: Metoda ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: c909b46a9bb70d23d1cd3a769ac24fcf58479308
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713798"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a>Metoda ICorDebugDataTarget2::GetImageLocation

Zwraca ścieżkę modułu z adresu podstawowego modułu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `baseAddress`  
 podczas Wartość [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , która reprezentuje adres podstawowy modułu.  
  
 `cchName`  
 podczas Liczba znaków w buforze, która ma otrzymać ścieżkę modułu.  
  
 `pcchName`  
 określoną Wskaźnik do liczby znaków zapisanych w `szName` buforze.  
  
 `szName`  
 określoną Ścieżka modułu.  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejs ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
