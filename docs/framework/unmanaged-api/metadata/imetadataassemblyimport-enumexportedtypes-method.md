---
title: IMetaDataAssemblyImport::EnumExportedTypes — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: a8b2377c48331ff9f0e69876c51fb78c7190f694
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708897"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a>IMetaDataAssemblyImport::EnumExportedTypes — Metoda

Wylicza eksportowane typy, do których odwołuje się manifest zestawu w bieżącym zakresie metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `phEnum`  
 [in. out] Wskaźnik do modułu wyliczającego. Ta wartość musi być wartością null, gdy `EnumExportedTypes` Metoda jest wywoływana po raz pierwszy.  
  
 `rExportedTypes`  
 określoną Wyliczanie `mdExportedType` tokenów metadanych.  
  
 `cMax`  
 podczas Maksymalna liczba `mdExportedType` tokenów, które mogą zostać umieszczone w `rExportedTypes` tablicy.  
  
 `pcTokens`  
 określoną Liczba `mdExportedType` tokenów, które zostały umieszczone w rzeczywistości `rExportedTypes` .  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|`S_OK`|`EnumExportedTypes` pomyślnie zwrócono.|  
|`S_FALSE`|Brak tokenów do wyliczenia. W tym przypadku `pcTokens` jest ustawiona na zero.|  
  
## <a name="requirements"></a>Wymagania  

 **Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataAssemblyImport — Interfejs](imetadataassemblyimport-interface.md)
