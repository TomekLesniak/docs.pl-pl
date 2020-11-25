---
title: IMetaDataAssemblyEmit::SetExportedTypeProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
ms.openlocfilehash: 076d027945dc27942e4b0989e14e86d829f76679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713492"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a>IMetaDataAssemblyEmit::SetExportedTypeProps — Metoda

Modyfikuje określoną `ExportedType` strukturę metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ct`  
 podczas Token metadanych określający `ExportedType` strukturę metadanych, która ma zostać zmodyfikowana.  
  
 `tkImplementation`  
 podczas Token, typu `File` , `AssemblyRef` lub `ExportedType` , który określa sposób implementacji tego typu.  
  
 `tkTypeDef`  
 podczas `TypeDef` Token, do którego odwołuje się plik kodu.  
  
 `dwExportedTypeFlags`  
 podczas Bitowa kombinacja wartości, które określają atrybuty typu.  
  
## <a name="remarks"></a>Uwagi  

 Aby utworzyć `ExportedType` strukturę metadanych, użyj metody [IMetaDataAssemblyEmit::D efineexportedtype](imetadataassemblyemit-defineexportedtype-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataAssemblyEmit — Interfejs](imetadataassemblyemit-interface.md)
