---
title: ICLRDataTarget — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
ms.openlocfilehash: 0d3e6a95d8fd71a67b97923dac53c1f615dfe666
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703424"
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget — Interfejs

Zapewnia metody interakcji z elementem docelowym środowiska uruchomieniowego języka wspólnego (CLR).  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetCurrentThreadID, metoda](iclrdatatarget-getcurrentthreadid-method.md)|Pobiera identyfikator systemu operacyjnego dla bieżącego wątku.|  
|[GetImageBase, metoda](iclrdatatarget-getimagebase-method.md)|Pobiera adres pamięci bazowej dla określonego obrazu.|  
|[GetMachineType, metoda](iclrdatatarget-getmachinetype-method.md)|Pobiera identyfikator rodzaju instrukcji, która jest używana przez proces docelowy.|  
|[GetPointerSize, metoda](iclrdatatarget-getpointersize-method.md)|Pobiera rozmiar wskaźnika do bieżącego elementu docelowego w bajtach.|  
|[GetThreadContext, metoda](iclrdatatarget-getthreadcontext-method.md)|Pobiera wskaźnik do kontekstu wątku o określonym identyfikatorze.|  
|[GetTLSValue, metoda](iclrdatatarget-gettlsvalue-method.md)|Pobiera wartość w magazynie lokalnym wątku (TLS) o określonym indeksie dla określonego wątku.|  
|[ReadVirtual, metoda](iclrdatatarget-readvirtual-method.md)|Odczytuje dane z określonego adresu pamięci wirtualnej do określonego buforu.|  
|[Request, metoda](iclrdatatarget-request-method.md)|Wywoływane przez usługi dostępu do danych środowiska uruchomieniowego języka wspólnego (CLR) do żądania operacji zgodnie z definicją w implementacji.|  
|[SetThreadContext, metoda](iclrdatatarget-setthreadcontext-method.md)|Ustawia bieżący kontekst określonego wątku w procesie docelowym.|  
|[SetTLSValue, metoda](iclrdatatarget-settlsvalue-method.md)|Ustawia wartość w ramach wątku lokalnego magazynu (TLS) określonego wątku w procesie docelowym.|  
|[WriteVirtual, metoda](iclrdatatarget-writevirtual-method.md)|Zapisuje dane z określonego buforu na określonym adresie pamięci wirtualnej.|  
  
## <a name="remarks"></a>Uwagi  

 Klient interfejsu API (czyli debuger) musi zaimplementować ten interfejs zgodnie z potrzebami dla określonego elementu docelowego. Na przykład żywy proces miałby inną implementację od tej ze zrzutu pamięci.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** ClrData. idl, ClrData. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRDataTarget2 — Interfejs](iclrdatatarget2-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
