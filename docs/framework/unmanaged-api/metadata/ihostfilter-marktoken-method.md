---
title: IHostFilter::MarkToken — Metoda
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: b4db3b115517f0a146aeab469f091008d31efc86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718231"
---
# <a name="ihostfiltermarktoken-method"></a>IHostFilter::MarkToken — Metoda

Wskazuje, że określony token metadanych zostanie przetworzony.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `tk`  
 podczas Token metadanych do przetworzenia.  
  
## <a name="remarks"></a>Uwagi  

 Zazwyczaj token ma być przetwarzany, jeśli znajduje się w zakresie metadanych. `MarkToken`Metoda jest przenoszona do aparatu metadanych za pośrednictwem metody [IMetaDataEmit:: sethandlee](imetadataemit-sethandler-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy metadanych](metadata-interfaces.md)
- [IHostFilter — Interfejs](ihostfilter-interface.md)
