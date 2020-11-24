---
title: EmitAssemblyCustomAttribute — Metoda
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
ms.openlocfilehash: 2070d1ec2aec80638c20c764eed5086c4a42e0fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676364"
---
# <a name="emitassemblycustomattribute-method"></a>EmitAssemblyCustomAttribute — Metoda

Wywołanie ustawiania atrybutów niestandardowych na poziomie zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `AssemblyID`  
 Identyfikator zestawu.  
  
 `FileToken`  
 Plik, który deplikuje atrybut. Może mieć wartość NULL `AssemblyID` , jeśli nie wskazuje niepowiązanego modułu.  
  
 `tkType`  
 Typ atrybutu niestandardowego.  
  
 `pCustomValue`  
 Dane wartości niestandardowej.  
  
 `cbCustomValue`  
 Długość danych wartości niestandardowych.  
  
 `bSecurity`  
 Ma wartość TRUE, jeśli atrybut niestandardowy jest powiązany z podpisywaniem zestawu.  
  
 `bAllowMulti`  
 Ma wartość TRUE, jeśli wiele atrybutów ma być emitowanych.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h  
  
## <a name="see-also"></a>Zobacz także

- [IALink — Interfejs](ialink-interface.md)
- [IALink2 — Interfejs](ialink2-interface.md)
- [ALink — interfejs API](index.md)
