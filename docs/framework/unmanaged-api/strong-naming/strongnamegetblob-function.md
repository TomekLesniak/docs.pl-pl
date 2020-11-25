---
title: StrongNameGetBlob — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
ms.openlocfilehash: 8f5cb89294004dfb1f020627ceb1edb58735f72c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732284"
---
# <a name="strongnamegetblob-function"></a>StrongNameGetBlob — Funkcja

Wypełnia określony bufor reprezentacją binarną pliku wykonywalnego pod określonym adresem.  
  
 Ta funkcja jest przestarzała. Zamiast tego użyj metody [ICLRStrongName:: StrongNameGetBlob —](../hosting/iclrstrongname-strongnamegetblob-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `wszFilePath`  
 podczas Prawidłowa ścieżka do pliku wykonywalnego, który ma zostać załadowany.  
  
 `pbBlob`  
 podczas Bufor, do którego ma zostać załadowany plik wykonywalny.  
  
 `pcbBlob`  
 [in. out] Żądany maksymalny rozmiar, w bajtach, z `pbBlob` . Po powrocie, rzeczywisty rozmiar, w bajtach, z `pbBlob` .  
  
## <a name="return-value"></a>Wartość zwracana  

 `true` Po pomyślnym zakończeniu; w przeciwnym razie `false` .  
  
## <a name="remarks"></a>Uwagi  

 Jeśli `StrongNameGetBlob` Funkcja nie zakończy się pomyślnie, wywołaj funkcję [StrongNameErrorInfo —](strongnameerrorinfo-function.md) w celu pobrania ostatniego wygenerowanego błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** StrongName. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [StrongNameGetBlob, metoda](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [StrongNameGetBlobFromImage, metoda](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [ICLRStrongName — Interfejs](../hosting/iclrstrongname-interface.md)
