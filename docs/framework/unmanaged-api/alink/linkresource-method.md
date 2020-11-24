---
title: LinkResource — Metoda
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
ms.openlocfilehash: 4f2f13976dfd4e5601bf8b54bed7b851884fbb9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690450"
---
# <a name="linkresource-method"></a>LinkResource — Metoda

Linki w zasobie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `AssemblyID`  
 Identyfikator zestawu.  
  
 `pszFileName`  
 Nazwa pliku.  
  
 `pszNewLocation`  
 Opcjonalna nazwa nowego pliku. Jeśli wartość nie jest równa NULL, `pszFileName` zostanie skopiowana do pszNewLocation.  
  
 `pszResourceName`  
 Nazwa zasobu.  
  
 `dwFlags`  
 Flagi dostępności, takie jak `mrPublic` i `mrPrivate` . Ten parametr może być przesłany do [metody DefineManifestResource —](../metadata/imetadataassemblyemit-definemanifestresource-method.md).  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h.  
  
## <a name="see-also"></a>Zobacz także

- [IALink — Interfejs](ialink-interface.md)
- [IALink2 — Interfejs](ialink2-interface.md)
- [ALink — interfejs API](index.md)
