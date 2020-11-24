---
title: ICeeGen::TruncateSection — Metoda
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
ms.openlocfilehash: 3005db62bba4089c669a00f62e3c1e62f9e1dae9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685711"
---
# <a name="iceegentruncatesection-method"></a>ICeeGen::TruncateSection — Metoda

Obcina określoną sekcję kodu o określoną długość.  
  
 Ta metoda jest przestarzała i nie powinna być używana.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `section`  
 podczas Sekcja do obcięcia.  
  
 `len`  
 podczas Długość w bajtach, przez którą ma zostać obcięta sekcja.  
  
## <a name="remarks"></a>Uwagi  

 Wywołanie `TruncateSection` tylko wtedy, gdy istnieją specjalne wymagania sekcji, które nie są obsługiwane przez inne metody.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICeeGen — Interfejs](iceegen-interface.md)
