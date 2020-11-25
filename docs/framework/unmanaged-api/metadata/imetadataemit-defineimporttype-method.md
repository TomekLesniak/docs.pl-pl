---
title: IMetaDataEmit::DefineImportType — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: 94ce4443be210fdfeb1bab197c3e603255e1cc4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723249"
---
# <a name="imetadataemitdefineimporttype-method"></a>IMetaDataEmit::DefineImportType — Metoda

Tworzy odwołanie do określonego typu, który jest zdefiniowany poza bieżącym zakresem, i definiuje token dla tego odwołania.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DefineImportType (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,
    [in]  IMetaDataImport          *pImport,
    [in]  mdTypeDef                tdImport,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pAssemImport`  
 podczas Interfejs [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) , który reprezentuje zestaw, z którego zaimportowano typ docelowy.  
  
 `pbHashValue`  
 podczas Tablica, która zawiera skrót dla zestawu określonego przez `pAssemImport` .  
  
 `cbHashValue`  
 podczas Liczba bajtów w `pbHashValue` tablicy.  
  
 `pImport`  
 podczas Interfejs [IMetaDataImport](imetadataimport-interface.md) reprezentujący zakres metadanych, z którego jest importowany typ docelowy.  
  
 `tdImport`  
 podczas `mdTypeDef` Token określający typ docelowy.  
  
 `pAssemEmit`  
 podczas Interfejs [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) , który reprezentuje zestaw, do którego zaimportowany jest typ docelowy.  
  
 `ptr`  
 określoną `mdTypeRef` Token, który jest zdefiniowany w bieżącym zakresie dla odwołania do typu.  
  
## <a name="remarks"></a>Uwagi  

 Przed wywołaniem metody [IMetaDataEmit::D efineimportmember](imetadataemit-defineimportmember-method.md) , można użyć `DefineImportType` metody, aby utworzyć odwołanie do typu w bieżącym zakresie dla klasy nadrzędnej lub interfejsu nadrzędnego elementu członkowskiego.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataEmit — Interfejs](imetadataemit-interface.md)
- [IMetaDataEmit2 — Interfejs](imetadataemit2-interface.md)
