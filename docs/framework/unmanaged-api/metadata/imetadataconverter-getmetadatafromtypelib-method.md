---
title: IMetaDataConverter::GetMetaDataFromTypeLib — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
ms.openlocfilehash: ed0902824bdbb4d057bf5a7920db4b1d18eb7347
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714669"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a>IMetaDataConverter::GetMetaDataFromTypeLib — Metoda

Pobiera wskaźnik interfejsu do wystąpienia [IMetaDataImport](imetadataimport-interface.md) , które reprezentuje sygnaturę metadanych biblioteki typów reprezentowanej przez określone `ITypeLib` wystąpienie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pITL`  
 podczas Wskaźnik do `ITypeLib` obiektu, który reprezentuje bibliotekę typów.  
  
 `ppMDI`  
 określoną Wskaźnik do lokalizacji, która otrzymuje adres `IMetaDataImport` wystąpienia, które reprezentuje sygnaturę metadanych.  
  
## <a name="requirements"></a>Wymagania  

 **Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataEmit — Interfejs](imetadataemit-interface.md)
- [IMetaDataImport — Interfejs](imetadataimport-interface.md)
