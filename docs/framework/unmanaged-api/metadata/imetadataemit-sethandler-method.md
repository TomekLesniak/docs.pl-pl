---
title: IMetaDataEmit::SetHandler — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 9b03dc5460875af3bb3e5e20799a4d26eb74da05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730373"
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler — Metoda

Ustawia metodę przywoływaną przez określony `IUnknown` wskaźnik jako wywołanie zwrotne powiadomienia o ponownym mapowaniu tokenu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pUnk`  
 podczas Procedura obsługi do rejestracji.  
  
## <a name="remarks"></a>Uwagi  

 Aparat metadanych wysyła powiadomienie przy użyciu metody dostarczonej przez `SetHandler` , do kompilatorów, które nie generują rekordów w sposób zoptymalizowany i który chce zoptymalizować zapisane rekordy.  
  
 Jeśli nie podano metody wywołania zwrotnego za pośrednictwem programu `SetHandler` , nie będzie przeprowadzana żadna Optymalizacja przy zapisywaniu, z wyjątkiem sytuacji, gdy kilka zakresów importu zostało scalonych przy użyciu `IMapToken` scalania dla każdego zakresu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataEmit — Interfejs](imetadataemit-interface.md)
- [IMetaDataEmit2 — Interfejs](imetadataemit2-interface.md)
