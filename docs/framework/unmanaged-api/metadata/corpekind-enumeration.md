---
title: CorPEKind — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 001be0c5e8897bacf76d2a044fb9400768473052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673536"
---
# <a name="corpekind-enumeration"></a>CorPEKind — Wyliczenie

Zawiera wartości opisujące przenośny plik wykonywalny (PE), który jest zwracany przez wywołanie [IMetaDataImport2:: GetPEKind —](imetadataimport2-getpekind-method.md).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`peNot`|Wskazuje, że nie jest to plik PE.|  
|`peILOnly`|Wskazuje, że ten plik PE zawiera tylko kod zarządzany.|  
|`pe32BitRequired`|Wskazuje, że ten plik PE wykonuje wywołania Win32.|  
|`pe32Plus`|Wskazuje, że ten plik PE działa na platformie 64-bitowej.|  
|`pe32Unmanaged`|Wskazuje, że ten plik PE jest kodem natywnym.|  
|pe32BitPreferred|Wskazuje, że ten plik PE jest niezależny od platformy i preferowany do załadowania w środowisku 32-bitowym.|  
  
## <a name="remarks"></a>Uwagi  

 Te wartości mogą być używane w kombinacjach bitowych.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorHdr. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Wyliczenia metadanych](metadata-enumerations.md)
