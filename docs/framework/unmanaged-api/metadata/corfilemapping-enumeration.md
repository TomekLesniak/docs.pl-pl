---
title: CorFileMapping — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
ms.openlocfilehash: 63e27a62e176a92b03c10b59a55d9da3192918f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726120"
---
# <a name="corfilemapping-enumeration"></a>CorFileMapping — Wyliczenie

Zawiera wartości opisujące typ mapowania plików zwracanego z wywołania metody [IMetaDataInfo:: GetFileMapping —](imetadatainfo-getfilemapping-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`fmFlat`|Plik jest mapowany jako plik danych. Oznacza to, że `SEC_IMAGE` flaga nie została przeniesiona do funkcji Microsoft Win32 `CreateFileMapping` .|  
|`fmExecutableImage`|Plik jest mapowany do wykonania przy użyciu `LoadLibrary` funkcji lub `CreateFileMapping` funkcji z `SEC_IMAGE` flagą.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorHdr. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Wyliczenia metadanych](metadata-enumerations.md)
- [GetFileMapping, metoda](imetadatainfo-getfilemapping-method.md)
