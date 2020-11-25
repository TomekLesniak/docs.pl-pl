---
title: IMetaDataAssemblyEmit::DefineAssembly — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 6d783e27c60db7381025f3b2382728e3996323ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725732"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>IMetaDataAssemblyEmit::DefineAssembly — Metoda

Tworzy `Assembly` strukturę zawierającą metadane dla określonego zestawu i zwraca skojarzony token metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pbPublicKey`  
 podczas Klucz publiczny, który identyfikuje wydawcę zestawu lub wartość NULL, jeśli zestaw nie ma silnej nazwy.  
  
 `cbPublicKey`  
 podczas Rozmiar w bajtach `pbPublicKey` .  
  
 `uHashAlgId`  
 podczas Identyfikator algorytmu wyznaczania wartości skrótu, który ma być używany do szyfrowania plików w zestawie, lub wartość NULL, aby określić algorytm SHA-1.  
  
 `szName`  
 podczas Nazwa tekstu do odczytania przez człowieka. Ta wartość nie może przekraczać 1024 znaków.  
  
 `pMetaData`  
 podczas Wskaźnik do wystąpienia ASSEMBLYMETADATA, który zawiera wersję, platformę i informacje o ustawieniach regionalnych dla zestawu.  
  
 `dwAssemblyFlags`  
 podczas Kombinacja wartości [CorAssemblyFlags —](corassemblyflags-enumeration.md) , które opisują funkcje zestawu.  
  
 `pmda`  
 określoną Wskaźnik do tokenu metadanych.  
  
## <a name="remarks"></a>Uwagi  

 `Assembly`W manifeście można zdefiniować tylko jedną strukturę metadanych.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataAssemblyEmit — Interfejs](imetadataassemblyemit-interface.md)
