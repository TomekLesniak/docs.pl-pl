---
title: StackOverflowType — Wyliczenie
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: bbdc68721378e6bbb09f5e4eade08e2e6e03b097
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729918"
---
# <a name="stackoverflowtype-enumeration"></a>StackOverflowType — Wyliczenie

Zawiera wartości wskazujące podstawową przyczynę zdarzenia przepełnienia stosu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`SO_ClrEngine`|Przepełnienie stosu zostało spowodowane przez aparat wykonywania.|  
|`SO_Managed`|Przepełnienie stosu zostało spowodowane przez kod zarządzany.|  
|`SO_Other`|Przepełnienie stosu zostało spowodowane przez kod niezarządzany.|  
  
## <a name="remarks"></a>Uwagi  

 Te informacje są przesyłane do hosta za pomocą wywołania metody [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Hosting — Wyliczenia](hosting-enumerations.md)
