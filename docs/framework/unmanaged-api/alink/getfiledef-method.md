---
title: GetFileDef — Metoda
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
ms.openlocfilehash: 42935813579d7f1d55a9f1daf9d8c6c1241f85be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684710"
---
# <a name="getfiledef-method"></a>GetFileDef — Metoda

Pobiera rzeczywisty token FileDef używany w metadanych (w przeciwieństwie do tokenu przypisanego przez ALink).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `AssemblyID`  
 Identyfikator zestawu.  
  
 `TargetFile`  
 Token dodanego pliku, który został pobrany z metody AddFile lub addimport.  
  
 `pScope`  
 Odbiera token FileDef.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h  
  
## <a name="see-also"></a>Zobacz także

- [IALink2 — Interfejs](ialink2-interface.md)
- [IALink — Interfejs](ialink-interface.md)
- [ALink — interfejs API](index.md)
