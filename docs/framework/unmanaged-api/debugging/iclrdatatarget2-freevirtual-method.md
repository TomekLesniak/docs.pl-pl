---
title: ICLRDataTarget2::FreeVirtual — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
ms.openlocfilehash: 1fb701a40abe2dc6e51443837c07ee5ba05ddfbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723652"
---
# <a name="iclrdatatarget2freevirtual-method"></a>ICLRDataTarget2::FreeVirtual — Metoda

Wywoływane przez usługi dostępu do danych środowiska uruchomieniowego języka wspólnego (CLR) do wolnej pamięci, która została wcześniej przydzielone w przestrzeni adresowej procesu docelowego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `addr`  
 podczas Wartość określająca `CLRDATA_ADDRESS` początkowy adres pamięci, która ma zostać zwolniona.  
  
 `size`  
 podczas Rozmiar (w bajtach) pamięci, która ma zostać zwolniona.  
  
 `typeFlags`  
 podczas Flagi kontrolujące zwalnianie pamięci. Zobacz funkcję Win32 `VirtualFree` .  
  
## <a name="remarks"></a>Uwagi  

 `FreeVirtual`Metoda służy jako otoka logiczna dla `VirtualFree` funkcji Win32.  
  
 Ta metoda jest implementowana przez moduł zapisujący aplikacji debugowania.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** ClrData. idl, ClrData. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRDataTarget2 — Interfejs](iclrdatatarget2-interface.md)
- [AllocVirtual, metoda](iclrdatatarget2-allocvirtual-method.md)
