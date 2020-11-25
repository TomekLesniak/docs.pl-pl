---
title: IEnumDefinitionIdentity — Interfejs
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
ms.openlocfilehash: f3872a2b03d3b22d695af1c104e9ae8ba8856990
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729008"
---
# <a name="ienumdefinitionidentity-interface"></a>IEnumDefinitionIdentity — Interfejs

Służy jako moduł wyliczający dla kolekcji `IDefinitionIdentity` obiektów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|Pobiera wskaźnik interfejsu do nowego `IEnumDefinitionIdentity` obiektu, który zawiera te same składowe `IEnumDefinitionIdentity` .|  
|`IEnumDefinitionIdentity::Next`|Pobiera określoną liczbę `IDefinitionIdentity` obiektów, rozpoczynając od bieżącego położenia.|  
|`IEnumDefinitionIdentity::Reset`|Przenosi wskaźnik instrukcji na początek tego elementu `IEnumDefinitionIdentity` .|  
|`IEnumDefinitionIdentity::Skip`|Przesuwa wskaźnik instrukcji do przodu o określoną liczbę elementów, rozpoczynając od bieżącego położenia.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Izolacja. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy łączenia](fusion-interfaces.md)
- [IDefinitionIdentity — Interfejs](idefinitionidentity-interface.md)
