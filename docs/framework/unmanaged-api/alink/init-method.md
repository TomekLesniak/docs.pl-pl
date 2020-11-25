---
title: Init — Metoda
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 25a1c29ab94a785304b83d5b1bcb2d7176742a68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726021"
---
# <a name="init-method"></a>Init — Metoda

Przygotowuje obiekty implementujące [interfejs IALink —](ialink-interface.md) do użytku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `pDispenser`  
 Wskaźnik [interfejsu IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) do rozdzielacza metadanych.  
  
 `pErrorHandler`  
 Wskaźnik [interfejsu IMetaDataError](../metadata/imetadataerror-interface.md) do opcjonalnego interfejsu obsługi błędów.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h  
  
## <a name="see-also"></a>Zobacz także

- [IALink — Interfejs](ialink-interface.md)
- [IALink2 — Interfejs](ialink2-interface.md)
- [ALink — interfejs API](index.md)
