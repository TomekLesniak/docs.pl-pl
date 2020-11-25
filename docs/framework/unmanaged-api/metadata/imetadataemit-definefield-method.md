---
title: IMetaDataEmit::DefineField — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 2bc2b983171dc41d5ac37eda0359f1aaee4ebd6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725758"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField — Metoda

Tworzy definicję dla pola z określonym podpisem metadanych i pobiera token do tej definicji pola.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a>Parametry  

 `td`  
 podczas `mdTypeDef` Token dla otaczającej klasy lub interfejsu.  
  
 `szName`  
 podczas Nazwa pola w formacie Unicode.  
  
 `dwFieldFlags`  
 podczas Atrybuty pola. To jest maska bitów `CorFieldAttr` wartości.  
  
 `pvSigBlob`  
 podczas Podpis pola jako obiekt BLOB.  
  
 `cbSigBlob`  
 podczas Liczba bajtów w `pvSigBlob` .  
  
 `dwCPlusTypeFlag`  
 podczas `ELEMENT_TYPE_` *\** Wartość stałej. To jest `CorElementType` wartość. Jeśli nie definiuje wartości stałej dla pola, użyj `ELEMENT_TYPE_END` .  
  
 `pValue`  
 podczas Stała wartość pola.  
  
 `cchValue`  
 podczas Znaki w formacie (Unicode) `pValue` .  
  
 `pmd`  
 określoną `mdFieldDef` Przypisany token.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataEmit — Interfejs](imetadataemit-interface.md)
- [IMetaDataEmit2 — Interfejs](imetadataemit2-interface.md)
