---
title: IValidator::Validate — Metoda
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
ms.openlocfilehash: 3c59114f78af1aa8705318af093e47d4f03a82ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699147"
---
# <a name="ivalidatorvalidate-method"></a>IValidator::Validate — Metoda

Sprawdza poprawność określonego przenośnego pliku wykonywalnego (PE) lub języka pośredniego firmy Microsoft (MSIL).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `veh`  
 podczas Wskaźnik do `IVEHandler` wystąpienia, które obsługuje błędy walidacji.  
  
 `pAppDomain`  
 podczas Wskaźnik do domeny aplikacji, w której plik zostanie załadowany.  
  
 `ulFlags`  
 podczas Bitowa kombinacja wartości [ValidatorFlags —](validatorflags-enumeration.md) wskazujących, które powinny być wykonywane.  
  
 `ulMaxError`  
 podczas Maksymalna liczba błędów, które należy pozostawić przed wyjściem z walidacji.  
  
 `token`  
 podczas Nieużywane.  
  
 `fileName`  
 podczas Ciąg określający nazwę pliku do zweryfikowania.  
  
 `pe`  
 podczas Wskaźnik do bufora pamięci, w którym przechowywany jest plik.  
  
 `ulSize`  
 podczas Rozmiar pliku, który ma być zweryfikowany w bajtach.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** IValidator. idl, IValidator. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
