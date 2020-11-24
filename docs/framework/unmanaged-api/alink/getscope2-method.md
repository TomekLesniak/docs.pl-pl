---
title: GetScope2 — Metoda
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: e8c6fd7dca13afe7504e447caca9a217c8136c27
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684528"
---
# <a name="getscope2-method"></a>GetScope2 — Metoda

Pobiera zakres importu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;
```  
  
## <a name="parameters"></a>Parametry  

 `AssemblyID`  
 Identyfikator zestawu docelowego.  
  
 `FileToken`  
 Identyfikator pliku, z którego ma zostać zaimportowany.  
  
 `dwScope`  
 Zakres od zera do zaimportowania.  
  
 `ppImportScope`  
 Odbiera wskaźnik do interfejsu [interfejsu IMetaDataImport2](../metadata/imetadataimport2-interface.md) dla wskazanego zakresu.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h.  
  
## <a name="see-also"></a>Zobacz także

- [IALink2 — Interfejs](ialink2-interface.md)
- [IALink — Interfejs](ialink-interface.md)
- [ALink — interfejs API](index.md)
