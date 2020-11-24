---
title: CustomDumpItem — Struktura
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
ms.openlocfilehash: c77e93686c7d121e9fe2a92f03970404ab823dc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673244"
---
# <a name="customdumpitem-structure"></a>CustomDumpItem — Struktura

Opisuje element, który ma zostać dodany do niestandardowego zrzutu w raporcie o błędach.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`itemKind`|Wartość [ECustomDumpItemKind —](ecustomdumpitemkind-enumeration.md) , która wskazuje rodzaj elementu, który ma zostać dodany.|  
|`pReserved`|Obecnie nie jest używany. Wszelkie elementy dodawane do Unii nie mogą być większe niż rozmiar wskaźnika. Jeśli `struct` jest wymagany, należy przydzielić go oddzielnie i wskazać.|  
  
## <a name="remarks"></a>Uwagi  

 [ICLRErrorReportingManager:: BeginCustomDump —](iclrerrorreportingmanager-begincustomdump-method.md) przyjmuje parametr typu `CustomDumpItem` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. idl  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Hosting — Struktury](hosting-structures.md)
