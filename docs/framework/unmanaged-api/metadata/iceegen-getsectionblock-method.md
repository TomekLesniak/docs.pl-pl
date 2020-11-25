---
title: ICeeGen::GetSectionBlock — Metoda
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: 9ce3afded5f914ecf970d8db738becc7f5cfff84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723145"
---
# <a name="iceegengetsectionblock-method"></a>ICeeGen::GetSectionBlock — Metoda

Pobiera blok sekcji bazy kodu.  
  
 Ta metoda jest przestarzała i nie powinna być używana.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a>Parametry  

 `section`  
 podczas Sekcja, z której ma zostać pobrany blok bazy kodu.  
  
 `len`  
 podczas Długość bloku do pobrania.  
  
 `align`  
 podczas Bajt względem początku sekcji, za pomocą którego ma zostać wyrównany pierwszy bajt bloku. To jest pozycja bloku w sekcji.  
  
 `ppBytes`  
 określoną Wskaźnik do lokalizacji, która otrzymuje adres pobranego bloku.  
  
## <a name="remarks"></a>Uwagi  

 Wywołanie `GetSectionBlock` tylko wtedy, gdy istnieją specjalne wymagania sekcji, które nie są obsługiwane przez inne metody.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICeeGen — Interfejs](iceegen-interface.md)
