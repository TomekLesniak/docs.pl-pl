---
title: ISymUnmanagedVariable::GetAddressField3 — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
ms.openlocfilehash: 13746c4ac6322a401e547c1c7acc99c0eda9accf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723340"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a>ISymUnmanagedVariable::GetAddressField3 — Metoda

Pobiera trzecie pole adresu dla tej zmiennej. Jego znaczenie zależy od rodzaju adresu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parametry  

 `pRetVal`  
 określoną Wskaźnik do elementu `ULONG32` , który odbiera trzecie pole adresu.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedVariable — Interfejs](isymunmanagedvariable-interface.md)
- [GetAddressField1, metoda](isymunmanagedvariable-getaddressfield1-method.md)
- [GetAddressField2, metoda](isymunmanagedvariable-getaddressfield2-method.md)
- [GetAddressKind, metoda](isymunmanagedvariable-getaddresskind-method.md)
