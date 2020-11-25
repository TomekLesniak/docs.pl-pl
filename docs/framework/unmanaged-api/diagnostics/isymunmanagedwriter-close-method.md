---
title: ISymUnmanagedWriter::Close — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 1d684c14f14fcc93040798ae4ee3b8bb1df5354d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733259"
---
# <a name="isymunmanagedwriterclose-method"></a>ISymUnmanagedWriter::Close — Metoda

Zamyka moduł zapisujący symboli po zatwierdzeniu symboli do magazynu symboli.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="remarks"></a>Uwagi  

 Po tym wywołaniu moduł zapisujący symboli jest nieprawidłowy dla dalszych aktualizacji. Aby zamknąć moduł zapisujący symboli bez przekazywania symboli, zamiast tego użyj metody [ISymUnmanagedWriter:: Abort](isymunmanagedwriter-abort-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedWriter — Interfejs](isymunmanagedwriter-interface.md)
