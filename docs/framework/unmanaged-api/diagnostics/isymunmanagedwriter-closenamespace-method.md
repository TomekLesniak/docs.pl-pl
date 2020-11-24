---
title: ISymUnmanagedWriter::CloseNamespace — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
ms.openlocfilehash: 13a433157e0c92653edf234f1f1f885270196ffd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686413"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a>ISymUnmanagedWriter::CloseNamespace — Metoda

Zamyka ostatnio otwartą przestrzeń nazw.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedWriter — Interfejs](isymunmanagedwriter-interface.md)
- [OpenNamespace, metoda](isymunmanagedwriter-opennamespace-method.md)
