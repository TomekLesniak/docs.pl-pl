---
title: AddFile — Metoda
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 53ca4005f5681cfc5d550301d8aad1406aceb3a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717204"
---
# <a name="addfile-method"></a>AddFile — Metoda

Dodaje pliki do zestawu. Może również służyć do tworzenia niezwiązanych modułów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `AssemblyID`  
 Unikatowy identyfikator zestawu, który ma zostać rozszerzony.  
  
 `pszFilename`  
 W pełni kwalifikowana nazwa pliku, który ma zostać dodany.  
  
 `dwFlags`  
 Flagi FileDef modelu COM+, takie jak `ffContainsNoMetaData` i `ffWriteable` . `dwFlags` jest przenoszona do [metody DefineFile —](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 Interfejs [interfejsu IMetaDataEmit](../metadata/imetadataemit-interface.md) , który ma być używany do emitowania metadanych, w razie potrzeby.  
  
 `pFileToken`  
 Wskaźnik do lokalizacji, w której będzie przechowywany unikatowy identyfikator dodanego pliku.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h.  
  
## <a name="see-also"></a>Zobacz także

- [IALink — Interfejs](ialink-interface.md)
- [IALink2 — Interfejs](ialink2-interface.md)
- [ALink — interfejs API](index.md)
