---
title: COR_NATIVE_LINK — Struktura
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
ms.openlocfilehash: 15f573ebc07bcf08a1ab8f5a5bbb88e940c5c8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724172"
---
# <a name="cor_native_link-structure"></a>COR_NATIVE_LINK — Struktura

Zawiera informacje, które są używane do łączenia kodu natywnego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`m_linkType`|Typ, który ma być połączony w kodzie natywnym. Ta wartość jest jedną z wartości [CorNativeLinkType —](cornativelinktype-enumeration.md) .|  
|`m_flags`|Flagi używane przez konsolidator podczas łączenia kodu natywnego. Ta wartość jest jedną z wartości [CorNativeLinkFlags —](cornativelinkflags-enumeration.md) .|  
|`m_entryPoint`|Token metadanych elementu MemberRef reprezentujący punkt wejścia. Format to `lib:entrypoint` .|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Metadane — Struktury](metadata-structures.md)
- [CorNativeLinkType — Wyliczenie](cornativelinktype-enumeration.md)
- [CorNativeLinkFlags — Wyliczenie](cornativelinkflags-enumeration.md)
