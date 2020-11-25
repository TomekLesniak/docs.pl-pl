---
title: IMetaDataEmit::DeletePinvokeMap — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
ms.openlocfilehash: 6fc6cf9b7333dd4caad3c5a4b081fecb060c8f86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722092"
---
# <a name="imetadataemitdeletepinvokemap-method"></a>IMetaDataEmit::DeletePinvokeMap — Metoda

Niszczy metadane mapowania PInvoke dla obiektu, do którego odwołuje się określony token.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a>Parametry  

 `tk`  
 podczas `mdFieldDef` Token lub `mdMethodDef` reprezentujący obiekt, dla którego mają zostać usunięte metadane mapowania PInvoke.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataEmit — Interfejs](imetadataemit-interface.md)
- [IMetaDataEmit2 — Interfejs](imetadataemit2-interface.md)
