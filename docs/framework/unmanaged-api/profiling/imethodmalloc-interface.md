---
title: IMethodMalloc — Interfejs
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 8eccdba75b59df505ae72d74cfcd2bc83de2b45a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688175"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc — Interfejs

Udostępnia metodę przydzielania pamięci dla nowej treści funkcji języka pośredniego (MSIL) firmy Microsoft.  
  
> [!NOTE]
> `IMethodMalloc`Interfejs jest prostym alokatorem pamięci. Umożliwia przydzielanie pamięci, ale nie zwalnia.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Alloc, metoda](imethodmalloc-alloc-method.md)|Próbuje przydzielić określoną ilość pamięci dla nowej treści funkcji MSIL.|  
  
## <a name="remarks"></a>Uwagi  

 Każdy Alokator jest specyficzny dla modułu i gwarantuje, że treść funkcji będzie naliczona pozytywnie od podstawy modułu. Pamięć powyżej podstawy modułu może być cenna, więc Alokator powinien być używany do przydzielania pamięci tylko dla treści funkcji.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy profilowania](profiling-interfaces.md)
