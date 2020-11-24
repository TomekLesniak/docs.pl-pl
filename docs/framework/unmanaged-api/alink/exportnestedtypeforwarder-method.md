---
title: ExportNestedTypeForwarder — Metoda
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: 45adda6551e1cec994f59acbb0e8d2b5c56c4df6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684814"
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder — Metoda

Dodaje funkcję przesyłania dalej typu dla typu zagnieżdżonego do tabeli typów danego zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `AssemblyID`  
 Identyfikator zestawu do wyeksportowania.  
  
 `FileToken`  
 Token pliku lub identyfikator zestawu, który definiuje typ.  
  
 `TypeToken`  
 Token dla tego typu.  
  
 `ParentType`  
 Token typu nadrzędnego.  
  
 `pszTypename`  
 W pełni kwalifikowana nazwa typu do eksportowania.  
  
 `dwFlags`  
 `ComType` flagi takie jak `tdPublic` lub `tdNested` .  
  
 `pType`  
 Odbiera token typu eksportu. Jest to konieczne tylko w przypadku emitowania typów zagnieżdżonych.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h  
  
## <a name="see-also"></a>Zobacz także

- [IALink — Interfejs](ialink-interface.md)
- [IALink2 — Interfejs](ialink2-interface.md)
- [ALink — interfejs API](index.md)
