---
title: ImportTypes2 — Metoda
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
ms.openlocfilehash: 2ec7708edd86b9f2656d0eee434992c3b73200ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705049"
---
# <a name="importtypes2-method"></a>ImportTypes2 — Metoda

Inicjuje importowanie typów. Wywołaj tę metodę, aby rozpocząć importowanie typów z każdego zakresu zaimportowanego za pomocą [metody ImportFile —](importfile-method.md).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `AssemblyID`  
 Identyfikator zestawu do zaimportowania.  
  
 `FileToken`  
 Identyfikator pliku, z którego ma zostać zaimportowany.  
  
 `dwScope`  
 Zakres od zera, z którego ma zostać zaimportowany.  
  
 `phEnum`  
 Odbiera dojście modułu wyliczającego dla typów w danym zakresie.  
  
 `ppImportScope`  
 Opcjonalnie odbiera Interfejs [interfejsu IMetaDataImport2](../metadata/imetadataimport2-interface.md) .  
  
 `pdwCountOfTypes`  
 Opcjonalnie otrzymuje liczbę typów w określonym zakresie.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h  
  
## <a name="see-also"></a>Zobacz także

- [IALink2 — Interfejs](ialink2-interface.md)
- [IALink — Interfejs](ialink-interface.md)
- [ALink — interfejs API](index.md)
