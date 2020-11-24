---
title: ISymUnmanagedScope::GetEndOffset — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: 14e747e81e467019d464212e75513bdf98344916
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678366"
---
# <a name="isymunmanagedscopegetendoffset-method"></a>ISymUnmanagedScope::GetEndOffset — Metoda

Pobiera przesunięcie końca dla tego zakresu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parametry  

 `pRetVal`  
 określoną Wskaźnik do elementu `ULONG32` , który odbiera przesunięcie końcowe.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedScope — Interfejs](isymunmanagedscope-interface.md)
- [GetStartOffset, metoda](isymunmanagedscope-getstartoffset-method.md)
