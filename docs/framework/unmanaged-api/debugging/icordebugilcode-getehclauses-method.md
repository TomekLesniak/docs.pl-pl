---
title: Metoda ICorDebugILCode::GetEHClauses
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
ms.openlocfilehash: 38936a57944e9a0920c374f473c4cbe8e8d70abb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728670"
---
# <a name="icordebugilcodegetehclauses-method"></a>Metoda ICorDebugILCode::GetEHClauses

[Obsługiwane w .NET Framework 4.5.2 i nowszych wersjach]  
  
 Zwraca wskaźnik do listy klauzul obsługi wyjątków (EH), które są zdefiniowane dla tego języka pośredniego (IL).  
  
## <a name="syntax"></a>Składnia  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
## <a name="parameters"></a>Parametry  

 `cClauses`  
 podczas Pojemność magazynu `clauses` macierzy. Zobacz sekcję Spostrzeżenia, aby uzyskać więcej informacji.  
  
 `pcClauses`  
 określoną Liczba klauzul, na których informacje są zapisywane w `clauses` tablicy.  
  
 warunki  
 określoną Tablica obiektów [CorDebugEHClause](cordebugehclause-structure.md) , które zawierają informacje na temat klauzul obsługi wyjątków zdefiniowane dla tego Il.  
  
## <a name="remarks"></a>Uwagi  

 Jeśli wartość `cClauses` jest równa 0 i `pcClauses` ma wartość różną od **null**, `pcClauses` jest ustawiona na liczbę dostępnych klauzul obsługi wyjątków. Jeśli `cClauses` jest różna od zera, reprezentuje pojemność magazynu `clauses` tablicy. Gdy metoda zwraca, `clauses` zawiera maksimum `cClauses` elementów i `pcClauses` jest ustawiona na liczbę klauzul faktycznie zapisywana w `clauses` tablicy.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejs ICorDebugILCode](icordebugilcode-interface.md)
- [Struktura CorDebugEHClause](cordebugehclause-structure.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
