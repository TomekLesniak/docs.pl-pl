---
title: IDENTITY_ATTRIBUTE — Struktura
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
ms.openlocfilehash: da4b1d6f2a7079ef33859fce29c9555ac06fcfc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725654"
---
# <a name="identity_attribute-structure"></a>IDENTITY_ATTRIBUTE — Struktura

Zawiera informacje o atrybucie metadanych dotyczące wystąpienia [IDefinitionIdentity —](idefinitionidentity-interface.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`pszNamespace`|Wskaźnik do ciągu znaków zakończonych znakiem null, który zawiera przestrzeń nazw, w której znajduje się atrybut.|  
|`pszName`|Wskaźnik do ciągu znaków zakończonych znakiem null, który zawiera nazwę atrybutu.|  
|`pszValue`|Wskaźnik do ciągu znaków zakończonych znakiem null, który zawiera wartość atrybutu.|  
  
## <a name="remarks"></a>Uwagi  

 `IDENTITY_ATTRIBUTE`Struktura zawiera trzy wskaźniki do ciągów znaków zakończonych znakiem null. Te trzy ciągi opisują jeden atrybut.  
  
 Wystąpienie `IDENTITY_ATTRIBUTE` struktury jest skojarzone z wystąpieniem struktury [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) . `IDENTITY_ATTRIBUTE`Struktura zawiera rzeczywiste ciągi, a odpowiednia `IDENTITY_ATTRIBUTE_BLOB` Struktura zawiera listę przesunięć do trzech ciągów wymienionych w `IDENTITY_ATTRIBUTE` strukturze.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Izolacja. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IDefinitionIdentity — Interfejs](idefinitionidentity-interface.md)
- [IDENTITY_ATTRIBUTE_BLOB — Struktura](identity-attribute-blob-structure.md)
- [Łączenie — Struktury](fusion-structures.md)
