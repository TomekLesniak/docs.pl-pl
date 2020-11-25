---
title: IValidator::FormatEventInfo — Metoda
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
ms.openlocfilehash: c5c89e0eda6e93e34775c00d5ec8fb4ff0940707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701019"
---
# <a name="ivalidatorformateventinfo-method"></a>IValidator::FormatEventInfo — Metoda

Pobiera komunikat o błędzie odpowiadający określonemu błędowi walidacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `hVECode`  
 podczas Wartość HRESULT, która została przeniesiona do procedury obsługi błędów walidacji.  
  
 `Context`  
 podczas `VEContext` Wystąpienie zawierające informacje kontekstu dotyczące błędu walidacji.  
  
 `msg`  
 [in. out] Ciąg, który zawiera zwracany komunikat o błędzie.  
  
 `ulMaxLength`  
 podczas Maksymalna długość komunikatu o błędzie.  
  
 `psa`  
 podczas Bezpieczna tablica zawierająca dodatkowe parametry opisujące błąd.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** IValidator. idl, IValidator. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
