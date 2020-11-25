---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod — Metoda
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: af02aba1a0d390c103e8c6108f90b93fe2a98ff3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707155"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a>ISymUnmanagedAsyncMethod::IsAsyncMethod — Metoda

Sprawdza, czy metoda ma informacje asynchroniczne, czy nie.  
  
 Jeśli ta metoda zwróci wartość `FALSE` , jest ona nieprawidłowa do wywołania innych metod w tym interfejsie. Wszystkie zwracają `E_UNEXPECTED` w tym przypadku.  
  
## <a name="syntax"></a>Składnia  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a>Parametry  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca wartość `HRESULT`.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedAsyncMethod — Interfejs](isymunmanagedasyncmethod-interface.md)
