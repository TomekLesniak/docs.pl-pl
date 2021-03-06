---
title: ICLRStrongName::StrongNameSignatureVerificationEx — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
ms.openlocfilehash: 9caeb72c57260012ae2b459950bf19d907da1d98
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671554"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a>ICLRStrongName::StrongNameSignatureVerificationEx — Metoda

Pobiera wartość wskazującą, czy manifest zestawu w podanej ścieżce zawiera podpis silnej nazwy.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `wszFilePath`  
 podczas Ścieżka do przenośnego pliku wykonywalnego (. exe lub. dll) dla zestawu, który ma zostać zweryfikowany.  
  
 `fForceVerification`  
 [w] `true` Aby przeprowadzić weryfikację, nawet jeśli konieczne jest przesłonięcie ustawień rejestru; w przeciwnym razie `false` .  
  
 `pfWasVerified`  
 [out] `true` Jeśli podpis silnej nazwy został zweryfikowany; w przeciwnym razie `false` . `pfWasVerified` jest również ustawiony na `false` , Jeśli weryfikacja zakończyła się pomyślnie z powodu ustawień rejestru.  
  
## <a name="return-value"></a>Wartość zwracana  

 `S_OK` Jeśli weryfikacja zakończyła się pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).  
  
## <a name="remarks"></a>Uwagi  

 Metoda [ICLRStrongName:: StrongNameSignatureVerificationEx —](iclrstrongname-strongnamesignatureverificationex-method.md) zapewnia możliwość podobną do metody [ICLRStrongName:: StrongNameSignatureVerification —](iclrstrongname-strongnamesignatureverification-method.md) . Jednak drugi parametr wejściowy i parametr wyjściowy dla [ICLRStrongName:: StrongNameSignatureVerificationEx —](iclrstrongname-strongnamesignatureverificationex-method.md) są typu `BOOLEAN` zamiast `DWORD` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [StrongNameSignatureVerification, metoda](iclrstrongname-strongnamesignatureverification-method.md)
- [ICLRStrongName — Interfejs](iclrstrongname-interface.md)
