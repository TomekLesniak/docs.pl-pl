---
title: EmbedResource — Metoda
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
ms.openlocfilehash: 34439b7c01dee7d7789d989b58e8944c6282b71b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676390"
---
# <a name="embedresource-method"></a>EmbedResource — Metoda

Deklaruje zasób osadzony. Ta metoda nie osadza zasobów w rzeczywistości.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `AssemblyID`  
 Identyfikator zestawu.  
  
 `FileToken`  
 Token pliku lub identyfikator zestawu pliku zawierającego zasób.  
  
 `pszResourceName`  
 Nazwa zasobu.  
  
 `dwOffset`  
 Przesunięcie zasobu z adresu RVA.  
  
 `dwFlags`  
 Flagi dostępności, takie jak `mrPublic` i `mrPrivate` . Flagi te mogą być przesyłane do [metody DefineExportedType —](../metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h.  
  
## <a name="see-also"></a>Zobacz także

- [IALink — Interfejs](ialink-interface.md)
- [IALink2 — Interfejs](ialink2-interface.md)
- [ALink — interfejs API](index.md)
