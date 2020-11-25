---
title: CodeChunkInfo, struktura
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
ms.openlocfilehash: 11197246662a93f6a8b57c6e61e49505a9999d00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727435"
---
# <a name="codechunkinfo-structure"></a>CodeChunkInfo, struktura

Reprezentuje pojedynczy fragment kodu w pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`startAddr`|Wartość określająca `CORDB_ADDRESS` początkowy adres fragmentu.|  
|`length`|Rozmiar fragmentu, w bajtach.|  
  
## <a name="remarks"></a>Uwagi  

 Pojedynczy fragment kodu jest regionem kodu natywnego, który jest częścią obiektu kodu, takiego jak funkcja.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [GetCodeChunks, metoda](icordebugcode2-getcodechunks-method.md)
- [Struktury debugowania](debugging-structures.md)
- [Debugowanie](index.md)
