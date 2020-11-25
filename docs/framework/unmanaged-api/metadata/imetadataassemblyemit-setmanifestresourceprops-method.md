---
title: IMetaDataAssemblyEmit::SetManifestResourceProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
ms.openlocfilehash: c46a3bc34ba7efa760e50416e9a6c39779727813
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708929"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a>IMetaDataAssemblyEmit::SetManifestResourceProps — Metoda

Modyfikuje określoną `ManifestResource` strukturę metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `mr`  
 podczas Token określający `ManifestResource` strukturę metadanych, która ma zostać zmodyfikowana.  
  
 `tkImplementation`  
 podczas Token, typu `File` lub `AssemblyRef` , który jest mapowany do dostawcy zasobów.  
  
 `dwOffset`  
 podczas Przesunięcie do początku zasobu w pliku.  
  
 `dwResourceFlags`  
 podczas Bitowa kombinacja wartości flag, które określają atrybuty zasobu.  
  
## <a name="remarks"></a>Uwagi  

 Aby utworzyć `ManifestResource` strukturę metadanych, użyj metody [IMetaDataAssemblyEmit::D efinemanifestresource](imetadataassemblyemit-definemanifestresource-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataAssemblyEmit — Interfejs](imetadataassemblyemit-interface.md)
