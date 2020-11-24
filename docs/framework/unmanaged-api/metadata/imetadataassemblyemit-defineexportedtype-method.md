---
title: IMetaDataAssemblyEmit::DefineExportedType — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 6b30218cc7373494870ec54a3196857fcc5c08a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689425"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType — Metoda

Tworzy `ExportedType` strukturę zawierającą metadane dla określonego typu wyeksportowanego i zwraca skojarzony token metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `szName`  
 podczas Nazwa typu do wyeksportowania. W przypadku wersji 1,1 środowiska uruchomieniowego języka wspólnego nazwa wyeksportowanego typu musi być dokładnie zgodna z nazwą podaną w `TypeDef` dla tego typu.  
  
 `tkImplementation`  
 podczas Token określający, gdzie jest zaimplementowany wyeksportowany typ. Prawidłowe wartości i ich powiązane znaczenie są następujące:  
  
- `mdFile` Typ jest zaimplementowany w innym pliku w tym zestawie.  
  
- `mdAssemblyRef` Typ jest zaimplementowany w innym zestawie.  
  
- `mdExportedTYpe` Typ jest zagnieżdżony w innym typie.  
  
- `mdFileNil` Typ znajduje się w tym samym pliku co manifest i nie jest typem zagnieżdżonym.  
  
 `tkTypeDef`  
 podczas Token do metadanych, który określa typ do wyeksportowania. Ta wartość jest wprowadzana w `TypeDef` tabeli w pliku, który implementuje typ i ma zastosowanie tylko wtedy, gdy ten plik znajduje się w tym zestawie.  
  
 `dwExportedTypeFlags`  
 podczas Bitowa kombinacja wartości wyliczenia [CorTypeAttr —](cortypeattr-enumeration.md) , które definiują ustawienia właściwości dla wyeksportowanego typu.  
  
 `pmdct`  
 określoną Wskaźnik do zwracanego tokenu metadanych, który wskazuje wyeksportowany typ.  
  
## <a name="remarks"></a>Uwagi  

 `ExportedType`Dla każdego typu, który jest udostępniany przez ten zestaw, musi być zdefiniowana Struktura metadanych, która jest zaimplementowana w module innym niż ten, który zawiera manifest.  
  
## <a name="requirements"></a>Wymagania  

 **Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataAssemblyEmit — Interfejs](imetadataassemblyemit-interface.md)
