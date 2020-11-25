---
title: ICorDebugRegisterSet2::GetRegistersAvailable — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
ms.openlocfilehash: cb56ea817d4045c19793a6290d68ae8b6236f14a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712323"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>ICorDebugRegisterSet2::GetRegistersAvailable — Metoda

Pobiera tablicę bajtów, która zawiera mapę bitową dostępnych rejestrów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `numChunks`  
 podczas Rozmiar `availableRegChunks` tablicy.  
  
 `availableRegChunks`  
 określoną Tablica bajtów, z których każdy bit odnosi się do rejestru. Jeśli rejestr jest dostępny, zostanie ustawiony odpowiedni bit rejestru.  
  
## <a name="remarks"></a>Uwagi  

 Wartości wyliczenia CorDebugRegister — określają rejestry różnych mikroprocesorów. Górne pięć bitów każdej wartości jest indeksem w `availableRegChunks` tablicy bajtów. Mniejsze trzy bity każdej wartości określają pozycję bitową w ramach indeksowanego bajtu. Uwzględniając wartość określającą `CorDebugRegister` konkretny rejestr, pozycja rejestru w masce jest określana w następujący sposób:  
  
1. Wyodrębnij indeks wymagany do uzyskania dostępu do poprawnego bajtu w `availableRegChunks` tablicy:  
  
     `CorDebugRegister` wartość >> 3  
  
2. Wyodrębnij pozycję bitową w zaindeksowanym bajcie, gdzie bit zero jest najmniej znaczącym bitem:  
  
     `CorDebugRegister` wartość & 7  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugRegisterSet2 — Interfejs](icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet — Interfejs](icordebugregisterset-interface.md)
