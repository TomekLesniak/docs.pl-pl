---
title: IMetaDataEmit::Merge — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: e64d644b511f7c3249c48b9642bfd3163142af3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722014"
---
# <a name="imetadataemitmerge-method"></a>IMetaDataEmit::Merge — Metoda

Dodaje określony zaimportowany zakres do listy zakresów, które mają zostać scalone.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pImport`  
 podczas Wskaźnik do obiektu [IMetaDataImport](imetadataimport-interface.md) , który identyfikuje importowany zakres do scalenia.  
  
 `pIMap`  
 podczas Wskaźnik do obiektu [IMapToken](imaptoken-interface.md) , który określa ponowne mapowanie tokenu.  
  
 `pHandler`  
 podczas Wskaźnik do obiektu [IUnknown](/cpp/atl/iunknown) , który określa błędy.  
  
## <a name="remarks"></a>Uwagi  

 Wywołanie [IMetaDataEmit:: MergeEnd —](imetadataemit-mergeend-method.md) w celu wyzwolenia fuzji metadanych w pojedynczym zakresie.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataEmit — Interfejs](imetadataemit-interface.md)
- [IMetaDataEmit2 — Interfejs](imetadataemit2-interface.md)
