---
title: IMetaDataAssemblyImport::GetManifestResourceProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: 585a9e39f529294841cd11389f03d763968a0f5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723821"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>IMetaDataAssemblyImport::GetManifestResourceProps — Metoda

Pobiera zestaw właściwości zasobu manifestu z określonym podpisem metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `mdmr`  
 podczas `mdManifestResource` Token reprezentujący zasób, dla którego mają zostać pobrane właściwości.  
  
 `szName`  
 określoną Nazwa zasobu.  
  
 `cchName`  
 podczas Rozmiar, w postaci szerokich znaków, z `szName` .  
  
 `pchName`  
 określoną Wskaźnik do liczby znaków dwubajtowych faktycznie zwróconych w `szName` .  
  
 `ptkImplementation`  
 określoną Wskaźnik do `mdFile` tokenu lub `mdAssemblyRef` tokenu, który reprezentuje odpowiednio plik lub zestaw, który zawiera zasób.  
  
 `pdwOffset`  
 określoną Wskaźnik do wartości, która określa przesunięcie do początku zasobu w pliku.  
  
 `pdwResourceFlags`  
 określoną Wskaźnik do flag, które opisują metadane zastosowane do zasobu. Wartość flags jest kombinacją co najmniej jednej wartości [CorManifestResourceFlags —](cormanifestresourceflags-enumeration.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataAssemblyImport — Interfejs](imetadataassemblyimport-interface.md)
