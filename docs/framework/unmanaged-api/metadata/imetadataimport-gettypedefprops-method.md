---
title: IMetaDataImport::GetTypeDefProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: 9dd973fe3e0802c49c220db51a21c223730e5aec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729172"
---
# <a name="imetadataimportgettypedefprops-method"></a>IMetaDataImport::GetTypeDefProps — Metoda

Zwraca informacje o metadanych <xref:System.Type> reprezentowane przez określony token typedef.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `td`  
 podczas Token TypeDef, który reprezentuje typ do zwrócenia metadanych.  
  
 `szTypeDef`  
 określoną Bufor zawierający nazwę typu.  
  
 `cchTypeDef`  
 podczas Rozmiar w postaci znaków dwubajtowych `szTypeDef` .  
  
 `pchTypeDef`  
 określoną Liczba znaków dwubajtowych zwracana w `szTypeDef` .  
  
 `pdwTypeDefFlags`  
 określoną Wskaźnik do każdej flagi modyfikującej definicję typu. Ta wartość jest maska bitowa z wyliczenia [CorTypeAttr —](cortypeattr-enumeration.md) .  
  
 `ptkExtends`  
 określoną Token metadanych TypeDef lub TypeRef reprezentujący typ podstawowy żądanego typu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataImport — Interfejs](imetadataimport-interface.md)
- [IMetaDataImport2 — Interfejs](imetadataimport2-interface.md)
