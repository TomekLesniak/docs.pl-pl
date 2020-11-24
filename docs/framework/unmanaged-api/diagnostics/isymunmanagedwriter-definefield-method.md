---
title: ISymUnmanagedWriter::DefineField — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
ms.openlocfilehash: 5683c10938873821cbe998dbf13937a6a7d24d7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675090"
---
# <a name="isymunmanagedwriterdefinefield-method"></a>ISymUnmanagedWriter::DefineField — Metoda

Definiuje pojedynczą zmienną, która nie znajduje się w metodzie. Ta metoda jest używana w przypadku niektórych pól klas, pól bitowych i tak dalej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parametry  

 `parent`  
 podczas Typ metadanych lub token metody.  
  
 `name`  
 podczas Nazwa pola.  
  
 `attributes`  
 podczas Atrybuty pola.  
  
 `cSig`  
 podczas `ULONG32` Jest to rozmiar (w znakach) bufora, który musi zawierać sygnaturę pola.  
  
 `signature`  
 podczas Tablica sygnatur pól.  
  
 `addrKind`  
 podczas Typ adresu.  
  
 `addr1`  
 podczas Pierwszy adres dla specyfikacji pola.  
  
 `addr2`  
 podczas Drugi adres dla specyfikacji pola.  
  
 `addr3`  
 podczas Trzeci adres dla specyfikacji pola.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedWriter — Interfejs](isymunmanagedwriter-interface.md)
