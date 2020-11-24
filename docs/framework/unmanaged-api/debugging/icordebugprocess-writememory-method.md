---
title: ICorDebugProcess::WriteMemory — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
ms.openlocfilehash: 18416954517c3cac09d013b8075bd097305a1dca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673972"
---
# <a name="icordebugprocesswritememory-method"></a>ICorDebugProcess::WriteMemory — Metoda

Zapisuje dane w obszarze pamięci w tym procesie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a>Parametry  

 `address`  
 podczas `CORDB_ADDRESS` Wartość, która jest adresem podstawowym obszaru pamięci, do którego zapisywane są dane. Przed przeprowadzeniem transferu danych system weryfikuje, czy obszar pamięci o określonym rozmiarze, zaczynając od adresu podstawowego, jest dostępny do zapisu. Jeśli nie jest dostępny, Metoda kończy się niepowodzeniem.  
  
 `size`  
 podczas Liczba bajtów do zapisania w obszarze pamięci.  
  
 `buffer`  
 podczas Bufor zawierający dane do zapisania.  
  
 `written`  
 określoną Wskaźnik do zmiennej, która odbiera liczbę bajtów zapisywanych w obszarze pamięci w tym procesie. Jeśli `written` ma wartość null, ten parametr jest ignorowany.  
  
## <a name="remarks"></a>Uwagi  

 Dane są automatycznie zapisywane za dowolnymi punktami przerwania. W .NET Framework w wersji 2,0 debugery natywne nie powinny używać tej metody do dodawania punktów przerwania do strumienia instrukcji. Zamiast tego użyj [ICorDebugProcess2:: SetUnmanagedBreakpoint —](icordebugprocess2-setunmanagedbreakpoint-method.md) .  
  
 `WriteMemory`Metoda powinna być używana tylko poza kodem zarządzanym. Ta metoda może uszkodzić środowisko uruchomieniowe, jeśli jest używane nieprawidłowo.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
