---
title: StrongNameGetBlobFromImage — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
ms.openlocfilehash: 3a84221f94bad76d69f0dc67fe695ada3f3862f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732245"
---
# <a name="strongnamegetblobfromimage-function"></a>StrongNameGetBlobFromImage — Funkcja

Pobiera binarną reprezentację obrazu zestawu pod określonym adresem pamięci.  
  
 Ta funkcja jest przestarzała. Zamiast tego użyj metody [ICLRStrongName:: StrongNameGetBlobFromImage —](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pbBase`  
 podczas Adres pamięci mapowanego manifestu zestawu.  
  
 `dwLength`  
 podczas Rozmiar obrazu w bajtach `pbBase` .  
  
 `pbBlob`  
 podczas Bufor zawierający reprezentację binarną obrazu.  
  
 `pcbBlob`  
 [in. out] Żądany maksymalny rozmiar, w bajtach, z `pbBlob` . Po powrocie, rzeczywisty rozmiar, w bajtach, z `pbBlob` .  
  
## <a name="return-value"></a>Wartość zwracana  

 `true` Po pomyślnym zakończeniu; w przeciwnym razie `false` .  
  
## <a name="remarks"></a>Uwagi  

 Jeśli `StrongNameGetBlobFromImage` Funkcja nie zakończy się pomyślnie, wywołaj funkcję [StrongNameErrorInfo —](strongnameerrorinfo-function.md) w celu pobrania ostatniego wygenerowanego błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** StrongName. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [StrongNameGetBlobFromImage, metoda](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [StrongNameGetBlob, metoda](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [ICLRStrongName — Interfejs](../hosting/iclrstrongname-interface.md)
