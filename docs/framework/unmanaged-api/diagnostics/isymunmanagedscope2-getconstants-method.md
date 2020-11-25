---
title: ISymUnmanagedScope2::GetConstants — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: df42e58a9bb3bf00b3fa4df45086dc2219658e25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725849"
---
# <a name="isymunmanagedscope2getconstants-method"></a>ISymUnmanagedScope2::GetConstants — Metoda

Pobiera stałe lokalne zdefiniowane w tym zakresie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a>Parametry  

 `cConstants`  
 podczas Długość buforu, `pcConstants` do którego wskazuje parametr.  
  
 `pcConstants`  
 określoną Wskaźnik do obiektu, `ULONG32` który odbiera rozmiar (w znakach) bufora, który musi zawierać stałe.  
  
 `constants`  
 określoną Bufor przechowujący stałe.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedScope2 — Interfejs](isymunmanagedscope2-interface.md)
