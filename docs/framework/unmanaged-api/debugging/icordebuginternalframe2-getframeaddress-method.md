---
title: ICorDebugInternalFrame2::GetFrameAddress — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: 05a9ab58acb3bf5829fd231ae6d8bcc96ae06da6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724874"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>ICorDebugInternalFrame2::GetFrameAddress — Metoda

Zwraca adres stosu ramki wewnętrznej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a>Parametry  

 `pAddress`  
 określoną Wskaźnik na `CORDB_ADDRESS` ramkę wewnętrzną.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Adres ramki wewnętrznej został pomyślnie zwrócony.|  
|E_FAIL|Nie można zwrócić adresu wewnętrznej ramki.|  
|E_INVALIDARG|`pAddress` to `null`.|  
  
## <a name="remarks"></a>Uwagi  

 Wartość zwrócona w `pAddress` może służyć do określenia lokalizacji wewnętrznej ramki względem innych ramek na stosie. Nawet na komputerach z procesorem IA-64, wewnętrzna ramka znajduje się tylko na stosie i nie istnieje odpowiedni wskaźnik do magazynu zapasowego.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugInternalFrame2 — Interfejs](icordebuginternalframe2-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
