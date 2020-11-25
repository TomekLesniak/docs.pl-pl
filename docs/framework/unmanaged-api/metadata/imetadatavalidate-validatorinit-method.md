---
title: IMetaDataValidate::ValidatorInit — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
ms.openlocfilehash: e2f54e11906cd4ba1440e220530f2ca5b9de769f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708559"
---
# <a name="imetadatavalidatevalidatorinit-method"></a>IMetaDataValidate::ValidatorInit — Metoda

Ustawia flagę określającą typ modułu w bieżącym zakresie metadanych i rejestruje określoną metodę wywołania zwrotnego dla błędów walidacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `dwModule`  
 podczas Wartość wyliczenia [CorValidatorModuleType —](corvalidatormoduletype-enumeration.md) , która określa typ modułu w bieżącym zakresie metadanych.  
  
 `pUnk`  
 podczas Wskaźnik do wystąpienia [IUnknown](/cpp/atl/iunknown) , który służy jako wywołanie zwrotne funkcji dla błędów walidacji.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataValidate — Interfejs](imetadatavalidate-interface.md)
