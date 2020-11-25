---
title: DacpReJitData, struktura
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 46708acc77dad00727ee35e7d06e4228eacbd502
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723041"
---
# <a name="dacprejitdata-structure"></a>DacpReJitData, struktura

Definiuje podstawowe informacje o danej metodzie Instrumentacji.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Składnia

```cpp
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a>Elementy członkowskie

| Członek           | Opis                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | Numer poprawki ReJit dla metody.                                                          |
| `flags`          | Flaga wskazująca bieżący stan Instrumentacji ReJit metody dla danej wersji. |
| `NativeCodeAddr` | Adres podstawowy implementacji rejitted metody.                                         |

## <a name="remarks"></a>Uwagi

Ta struktura jest w czasie wykonywania i nie jest udostępniana za pomocą żadnych plików nagłówkowych ani bibliotek. Aby go użyć, Zdefiniuj strukturę zgodnie z powyższym opisem. Strukturę należy również zdefiniować przy użyciu `ms_struct` pakowania, jeśli nie używa kompilatorów firmy Microsoft.

## <a name="requirements"></a>Wymagania

**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
**Nagłówek:** Dawaj  
**Biblioteka:** Dawaj  
**.NET Framework wersje:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Zobacz także

- [Debugowanie](index.md)
- [Struktury debugowania](debugging-structures.md)
