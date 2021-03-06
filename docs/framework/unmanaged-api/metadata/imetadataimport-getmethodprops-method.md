---
title: IMetaDataImport::GetMethodProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 0eb4e9d713581cf32cec18bb02a6bd13542e517a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733189"
---
# <a name="imetadataimportgetmethodprops-method"></a>IMetaDataImport::GetMethodProps — Metoda

Pobiera metadane skojarzone z metodą przywoływaną przez określony token MethodDef.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `mb`  
 podczas Token MethodDef reprezentujący metodę zwrócenia metadanych dla.  
  
 `pClass`  
 określoną Wskaźnik do tokenu TypeDef, który reprezentuje typ implementujący metodę.  
  
 `szMethod`  
 określoną Wskaźnik do buforu, który ma nazwę metody.  
  
 `cchMethod`  
 podczas Żądany rozmiar `szMethod` .  
  
 `pchMethod`  
 określoną Wskaźnik do rozmiaru w postaci znaków dwubajtowych `szMethod` lub w przypadku obcinania, rzeczywista liczba znaków dwubajtowych w nazwie metody.  
  
 `pdwAttr`  
 określoną Wskaźnik do wszystkich flag skojarzonych z metodą.  
  
 `ppvSigBlob`  
 określoną Wskaźnik do binarnego podpisu metadanych metody.  
  
 `pcbSigBlob`  
 określoną Wskaźnik do rozmiaru w bajtach `ppvSigBlob` .  
  
 `pulCodeRVA`  
 określoną Wskaźnik do względnego adresu wirtualnego metody.  
  
 `pdwImplFlags`  
 określoną Wskaźnik do dowolnych flag implementacji dla metody.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataImport — Interfejs](imetadataimport-interface.md)
- [IMetaDataImport2 — Interfejs](imetadataimport2-interface.md)
