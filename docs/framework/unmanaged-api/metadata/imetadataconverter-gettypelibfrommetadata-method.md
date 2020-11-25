---
title: IMetaDataConverter::GetTypeLibFromMetaData — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: eed8661f8885ca16492ab336a599b5290057843a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714604"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a>IMetaDataConverter::GetTypeLibFromMetaData — Metoda

Pobiera wskaźnik do `ITypeLib` wystąpienia, które reprezentuje bibliotekę typów, która ma określoną nazwę biblioteki i modułu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `strModule`  
 podczas Nazwa modułu biblioteki typów.  
  
 `strTlbName`  
 podczas Nazwa biblioteki typów.  
  
 `ppITL`  
 określoną Wskaźnik do lokalizacji, która otrzymuje adres `ITypeLib` wystąpienia, które reprezentuje bibliotekę typów.  
  
## <a name="requirements"></a>Wymagania  

 **Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataConverter — Interfejs](imetadataconverter-interface.md)
