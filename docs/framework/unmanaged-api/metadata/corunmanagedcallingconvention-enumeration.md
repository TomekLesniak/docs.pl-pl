---
title: CorUnmanagedCallingConvention — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: 9d35f6b1928d714216b669704ec28e53895f6549
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699069"
---
# <a name="corunmanagedcallingconvention-enumeration"></a>CorUnmanagedCallingConvention — Wyliczenie

Określa konwencje wywoływania dla niezarządzanego kodu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|Konwencja wywoływania języka C.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|Standardowa Konwencja wywoływania.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|Konwencja wywoływania "This".|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|Konwencja wywoływania "Fast".|  
|`IMAGE_CEE_CS_CALLCONV_C`|Nie używany.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|Nie używany.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|Nie używany.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|Nie używany.|  
  
## <a name="remarks"></a>Uwagi  

 Środowisko CLR nie obsługuje konwencji wywoływania "Fast" w .NET Framework w wersji 1,0.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorHdr. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Wyliczenia metadanych](metadata-enumerations.md)
