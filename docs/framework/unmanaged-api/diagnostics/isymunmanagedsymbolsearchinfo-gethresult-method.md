---
title: ISymUnmanagedSymbolSearchInfo::GetHRESULT — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
ms.openlocfilehash: a931c15b1c4a9f099d11c43edd324cfcc2793090
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722274"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a>ISymUnmanagedSymbolSearchInfo::GetHRESULT — Metoda

Pobiera wartość HRESULT.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a>Parametry  

 `phr`  
 określoną Wskaźnik do HRESULT.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedSymbolSearchInfo — Interfejs](isymunmanagedsymbolsearchinfo-interface.md)
