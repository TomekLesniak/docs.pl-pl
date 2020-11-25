---
title: SetAssemblyFile — Metoda
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 45eed17b91f70d4188d1d89fc91a41455f3e845b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732648"
---
# <a name="setassemblyfile-method"></a>SetAssemblyFile — Metoda

Przypisuje nazwę zestawu, który ma zostać skompilowany. Nie do użycia podczas tworzenia niezwiązanych modułów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `pszFilename`  
 W pełni kwalifikowana nazwa pliku manifestu.  
  
 `pEmitter`  
 Wskaźnik do interfejsu [interfejsu IMetaDataEmit](../metadata/imetadataemit-interface.md) .  
  
 `afFlags`  
 Flagi zgodnie z definicją w [wyliczeniu AssemblyFlags —](../metadata/assemblyflags-enumeration.md).  
  
 `pAssemblyID`  
 Wskaźnik na identyfikator tworzonego zestawu.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h.  
  
## <a name="see-also"></a>Zobacz także

- [IALink — Interfejs](ialink-interface.md)
- [IALink2 — Interfejs](ialink2-interface.md)
- [ALink — interfejs API](index.md)
