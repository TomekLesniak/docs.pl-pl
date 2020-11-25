---
title: IMetaDataConverter::GetMetaDataFromTypeInfo — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
ms.openlocfilehash: 1f45310bc65bc8614033182a81db451b79bcf97f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714721"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a>IMetaDataConverter::GetMetaDataFromTypeInfo — Metoda

Pobiera wskaźnik do wystąpienia [IMetaDataImport](imetadataimport-interface.md) , które reprezentuje sygnaturę metadanych biblioteki typów, do której odwołuje się określone `ITypeInfo` wystąpienie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pITI`  
 podczas Wskaźnik do `ITypeInfo` obiektu, który odwołuje się do biblioteki typów.  
  
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
