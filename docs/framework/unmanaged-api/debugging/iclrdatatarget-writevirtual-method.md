---
title: ICLRDataTarget::WriteVirtual — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
ms.openlocfilehash: df9315d4e007305fb38153e116dde02ba7f3a1b7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723677"
---
# <a name="iclrdatatargetwritevirtual-method"></a>ICLRDataTarget::WriteVirtual — Metoda

Zapisuje dane z określonego buforu na określonym adresie pamięci wirtualnej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `address`  
 podczas CLRDATA_ADDRESS, w którym jest przechowywany adres pamięci wirtualnej.  
  
 `buffer`  
 podczas Wskaźnik do buforu, który przechowuje dane do zapisania.  
  
 `bytesRequested`  
 podczas Liczba bajtów do zapisania.  
  
 `bytesWritten`  
 określoną Wskaźnik do rzeczywistej liczby zapisanych bajtów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** ClrData. idl, ClrData. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRDataTarget — Interfejs](iclrdatatarget-interface.md)
