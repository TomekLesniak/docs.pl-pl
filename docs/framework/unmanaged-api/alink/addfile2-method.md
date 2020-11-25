---
title: AddFile2 — Metoda
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
ms.openlocfilehash: cff6707496c7d9657796deb8bf6fa9165ff295a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717087"
---
# <a name="addfile2-method"></a>AddFile2 — Metoda

Dodaje pliki do zestawu. Może również służyć do tworzenia niezwiązanych modułów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `AssemblyID`  
 Identyfikator zestawu, do którego zostanie dodany plik.  
  
 `pszFilename`  
 Nazwa pliku, który ma zostać dodany.  
  
 `dwFlags`  
 `FileDef`Flagi com+, takie jak `ffContainsNoMetaData` i `ffWriteable` . `dwFlags` jest przenoszona do [metody DefineFile —](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 Interfejs do interfejsu [interfejsu IMetaDataEmit2](../metadata/imetadataemit2-interface.md) .  
  
 `pFileToken`  
 Odbiera identyfikator dodawanego pliku.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h.  
  
## <a name="see-also"></a>Zobacz także

- [IALink2 — Interfejs](ialink2-interface.md)
- [IALink — Interfejs](ialink-interface.md)
- [ALink — interfejs API](index.md)
