---
title: ICorDebugDataTarget::ReadVirtual — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
ms.openlocfilehash: 8fb0cfc72867653eaff65f3183dacf9191604290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679731"
---
# <a name="icordebugdatatargetreadvirtual-method"></a>ICorDebugDataTarget::ReadVirtual — Metoda

Pobiera blok ciągłej pamięci zaczynający się od określonego adresu i zwraca go w dostarczonym buforze.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a>Parametry  

 `address`  
 podczas Adres początkowy żądanej pamięci.  
  
 `pbuffer`  
 określoną Bufor, w którym będzie przechowywana pamięć.  
  
 `bytesRequested`  
 podczas Liczba bajtów pobieranych z adresu docelowego.  
  
 `pBytesRead`  
 określoną Liczba bajtów faktycznie odczytywanych z adresu docelowego. Może to być mniejsze niż `bytesRequested` .  
  
## <a name="remarks"></a>Uwagi  

 W przypadku odczytywania pierwszego bajtu (na określonym adresie początkowym) wywołanie powinno zwrócić sukces (w celu zapewnienia obsługi wydajnego odczytu struktur danych z unikatową długością, na przykład w przypadku ciągów zakończonych znakiem null).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugDataTarget — Interfejs](icordebugdatatarget-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
