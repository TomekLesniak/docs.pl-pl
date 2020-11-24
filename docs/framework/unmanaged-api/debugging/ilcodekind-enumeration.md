---
title: Wyliczenie ILCodeKind
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
ms.openlocfilehash: 7e9cf760ec609786804a05177349ee2eacd79eaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692244"
---
# <a name="ilcodekind-enumeration"></a>Wyliczenie ILCodeKind

[Obsługiwane w .NET Framework 4.5.2 i nowszych wersjach]  
  
 Zawiera wartości, które określają, czy debuger może uzyskać dostęp do zmiennych lokalnych lub kodu dodanego w instrumentacji profilera ReJIT.  
  
## <a name="syntax"></a>Składnia  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Nazwa elementu członkowskiego|Opis|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|Debuger nie ma dostępu do informacji z Instrumentacji ReJIT.|  
|`ILCODE_REJIT_IL`|Debuger ma dostęp do informacji z Instrumentacji ReJIT.|  
  
## <a name="remarks"></a>Uwagi  

 Element członkowski `ILCodeKind` wyliczenia można przesłać do metod [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) i [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) , aby określić, czy debuger może uzyskać dostęp do zmiennych dodanych w Instrumentacji ReJIT profilera, oraz do metody [GetCodeEx](icordebugilframe4-getcodeex-method.md) , aby określić, czy debuger może uzyskać dostęp do instrumentu Il.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — wyliczenia](debugging-enumerations.md)
- [Interfejs ICorDebugILFrame4](icordebugilframe4-interface.md)
- [ReJIT: Przewodnik How-To](/archive/blogs/davbr/rejit-a-how-to-guide)
