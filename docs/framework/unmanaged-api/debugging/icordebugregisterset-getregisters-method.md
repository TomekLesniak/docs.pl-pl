---
title: ICorDebugRegisterSet::GetRegisters — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 315e4cc3b93fc78e11a4fb399bbe6f8a9f55ac84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705010"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters — Metoda

Pobiera wartość każdego rejestru (na komputerze, który aktualnie wykonuje kod), który jest określony przez maskę bitową.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `mask`  
 podczas Maska bitów określająca, które wartości rejestru mają być pobierane. Każdy bit odnosi się do rejestru. Jeśli bit jest ustawiony na jeden, zostanie pobrana wartość rejestru. w przeciwnym razie wartość rejestru nie zostanie pobrana.  
  
 `regCount`  
 podczas Liczba wartości rejestru do pobrania.  
  
 `regBuffer`  
 określoną Tablica `CORDB_REGISTER` obiektów, z których każdy otrzymuje wartość rejestru.  
  
## <a name="remarks"></a>Uwagi  

 Rozmiar tablicy musi być równy liczbie bitów ustawionych dla jednej w masce bitów. `regCount`Parametr określa liczbę elementów w buforze, które będą otrzymywać wartości rejestru. Jeśli `regCount` wartość jest za mała dla liczby rejestrów wskazanych przez maskę, te rejestry o wyższych numerach zostaną obcięte z zestawu. Jeśli `regCount` wartość jest zbyt duża, nieużywane `regBuffer` elementy będą niemodyfikowane.  
  
 Jeśli Maska bitów określa rejestr, który jest niedostępny, `GetRegisters` zwraca wartość nieokreśloną dla tego rejestru.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugRegisterSet — Interfejs](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 — Interfejs](icordebugregisterset2-interface.md)
