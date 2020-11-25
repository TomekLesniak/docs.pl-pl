---
title: IMetaDataEmit::DefineProperty — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: d2a4a15126f34666a58021a59e9e193685b15a49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719492"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty — Metoda

Tworzy definicję właściwości określonego typu, z określonymi `get` `set` metodami dostępu, i pobiera token do tej definicji właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DefineProperty (
    [in]  mdTypeDef          td,
    [in]  LPCWSTR            szProperty,
    [in]  DWORD              dwPropFlags,
    [in]  PCCOR_SIGNATURE    pvSig,
    [in]  ULONG              cbSig,
    [in]  DWORD              dwCPlusTypeFlag,
    [in]  void const         *pValue,
    [in]  ULONG              cchValue,
    [in]  mdMethodDef        mdSetter,
    [in]  mdMethodDef        mdGetter,
    [in]  mdMethodDef        rmdOtherMethods[],
    [out] mdProperty         *pmdProp
);  
```  
  
## <a name="parameters"></a>Parametry  

 `td`  
 podczas Token klasy lub interfejsu, w którym właściwość jest zdefiniowana.  
  
 `szProperty`  
 podczas Nazwa właściwości.  
  
 `dwPropFlags`  
 podczas Flagi właściwości.  
  
 `pvSig`  
 podczas Podpis właściwości.  
  
 `cbSig`  
 podczas Liczba bajtów w `pvSig` .  
  
 `dwCPlusTypeFlag`  
 podczas Typ wartości domyślnej właściwości.  
  
 `pValue`  
 podczas Wartość domyślna właściwości.  
  
 `cchValue`  
 podczas Liczba znaków (Unicode) w `pValue` .  
  
 `mdSetter`  
 podczas Metoda, która ustawia wartość właściwości.  
  
 `mdGetter`  
 podczas Metoda, która pobiera wartość właściwości.  
  
 `rmdOtherMethods[]`  
 podczas Tablica innych metod skojarzonych z właściwością. Przerwij tablicę przy użyciu `mdTokenNil` .  
  
 `pmdProp`  
 określoną `mdProperty` Przypisany token.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataEmit — Interfejs](imetadataemit-interface.md)
- [IMetaDataEmit2 — Interfejs](imetadataemit2-interface.md)
