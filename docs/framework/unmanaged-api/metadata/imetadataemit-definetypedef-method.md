---
title: IMetaDataEmit::DefineTypeDef — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 2e75b6322e40fe010e9e0a3412a99c0d3460afae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719362"
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef — Metoda

Tworzy definicję typu dla typu środowiska uruchomieniowego języka wspólnego i pobiera token metadanych dla tej definicji typu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `szTypeDef`  
 podczas Nazwa typu w formacie Unicode.  
  
 `dwTypeDefFlags`  
 [w] `TypeDef` Attributes. To jest maska bitów `CoreTypeAttr` wartości.  
  
 `tkExtends`  
 podczas Token klasy bazowej. Musi być albo `mdTypeDef` `mdTypeRef` tokenem.  
  
 `rtkImplements`  
 podczas Tablica tokenów określająca interfejsy, które implementuje Ta klasa lub interfejs.  
  
 `ptd`  
 określoną `mdTypeDef` Przypisany token.  
  
## <a name="remarks"></a>Uwagi  

 Flaga w `dwTypeDefFlags` określa, czy tworzony typ jest typem referencyjnym systemu typu wspólnego (Class lub Interface) czy typem wartości typu wspólnego systemu.  
  
 W zależności od dostarczonych parametrów, ta metoda jako efekt uboczny może również utworzyć `mdInterfaceImpl` rekord dla każdego interfejsu, który jest dziedziczony lub zaimplementowany przez ten typ. Jednakże ta metoda nie zwraca żadnego z tych `mdInterfaceImpl` tokenów. Jeśli klient chce później dodać lub zmodyfikować `mdInterfaceImpl` token, musi użyć `IMetaDataImport` interfejsu, aby je wyliczyć. Jeśli chcesz używać semantyki COM `[default]` interfejsu, należy podać domyślny interfejs jako pierwszy element w `rtkImplements` ; zestaw atrybutów niestandardowych w klasie wskazuje, że Klasa ma interfejs domyślny (który jest zawsze traktowany jako pierwszy `mdInterfaceImpl` token zadeklarowany dla klasy).  
  
 Każdy element `rtkImplements` tablicy zawiera `mdTypeDef` `mdTypeRef` token lub. Ostatni element w tablicy musi być `mdTokenNil` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataEmit — Interfejs](imetadataemit-interface.md)
- [IMetaDataEmit2 — Interfejs](imetadataemit2-interface.md)
