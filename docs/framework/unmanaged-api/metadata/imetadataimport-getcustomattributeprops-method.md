---
title: IMetaDataImport::GetCustomAttributeProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type:
- apiref
ms.openlocfilehash: b92e9ab714e2d8d2c66ed5546deba16352e8e390
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711146"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a>IMetaDataImport::GetCustomAttributeProps — Metoda

Pobiera wartość atrybutu niestandardowego z uwzględnieniem jego tokenu metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `cv`  
 podczas Token metadanych, który reprezentuje atrybut niestandardowy do pobrania.  
  
 `ptkObj`  
 [out, opcjonalne] Token metadanych reprezentujący obiekt, który modyfikuje atrybut niestandardowy. Ta wartość może być dowolnego typu tokenu metadanych z wyjątkiem `mdCustomAttribute` .  
  
 `ptkType`  
 [out, opcjonalne] `mdMethodDef` `mdMemberRef` Token metadanych lub reprezentujący <xref:System.Type> zwrócony atrybut niestandardowy.  
  
 `ppBlob`  
 [out, opcjonalne] Wskaźnik do tablicy danych, która jest wartością atrybutu niestandardowego.  
  
 `pcbSize`  
 [out, opcjonalne] Rozmiar w bajtach danych zwróconych w * `ppBlob` .  
  
## <a name="remarks"></a>Uwagi  

 Atrybut niestandardowy jest przechowywany jako tablica danych, format zrozumiały dla aparatu metadanych.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataImport — Interfejs](imetadataimport-interface.md)
- [IMetaDataImport2 — Interfejs](imetadataimport2-interface.md)
