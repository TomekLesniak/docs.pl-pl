---
title: ISymUnmanagedVariable::GetName — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
ms.openlocfilehash: f9da3ca8684da3bbc87146b3b52effdc4f91393d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726889"
---
# <a name="isymunmanagedvariablegetname-method"></a>ISymUnmanagedVariable::GetName — Metoda

Pobiera nazwę tej zmiennej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a>Parametry  

 `cchName`  
 podczas Długość buforu, `pcchName` do którego wskazuje parametr.  
  
 `pcchName`  
 określoną Wskaźnik do obiektu, `ULONG32` który odbiera rozmiar (w znakach) bufora, który musi zawierać nazwę, łącznie z zakończeniem o wartości null.  
  
 `szName`  
 określoną Bufor przechowujący nazwę.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedVariable — Interfejs](isymunmanagedvariable-interface.md)
