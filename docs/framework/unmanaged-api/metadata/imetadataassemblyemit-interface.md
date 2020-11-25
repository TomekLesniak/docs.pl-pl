---
title: IMetaDataAssemblyEmit — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
ms.openlocfilehash: 5d8bc54a94e1571ff8335c934407bbf235179ecc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728293"
---
# <a name="imetadataassemblyemit-interface"></a>IMetaDataAssemblyEmit — Interfejs

Dostarcza metody, które obsługują model z własnymi opisami używany przez środowisko uruchomieniowe języka wspólnego do rozwiązywania i korzystania z zasobów.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[DefineAssembly, metoda](imetadataassemblyemit-defineassembly-method.md)|Tworzy strukturę danych zestawu zawierającą metadane dla określonego zestawu i zwraca skojarzony token metadanych.|  
|[DefineAssemblyRef, metoda](imetadataassemblyemit-defineassemblyref-method.md)|Tworzy `AssemblyRef` strukturę zawierającą metadane zestawu, do którego odwołuje się ten zestaw, i zwraca skojarzony token metadanych.|  
|[DefineExportedType, metoda](imetadataassemblyemit-defineexportedtype-method.md)|Tworzy `ExportedType` strukturę zawierającą metadane dla określonego typu wyeksportowanego i zwraca skojarzony token metadanych.|  
|[DefineFile, metoda](imetadataassemblyemit-definefile-method.md)|Tworzy `File` strukturę metadanych zawierającą metadane zestawu, do którego odwołuje się ten zestaw, i zwraca skojarzony token metadanych.|  
|[DefineManifestResource, metoda](imetadataassemblyemit-definemanifestresource-method.md)|Tworzy `ManifestResource` strukturę zawierającą metadane dla określonego zasobu manifestu i zwraca skojarzony token metadanych.|  
|[SetAssemblyProps — Metoda](imetadataassemblyemit-setassemblyprops-method.md)|Modyfikuje określoną `Assembly` strukturę metadanych.|  
|[SetAssemblyRefProps, metoda](imetadataassemblyemit-setassemblyrefprops-method.md)|Modyfikuje określoną `AssemblyRef` strukturę metadanych.|  
|[SetExportedTypeProps, metoda](imetadataassemblyemit-setexportedtypeprops-method.md)|Modyfikuje określoną `ExportedType` strukturę metadanych.|  
|[SetFileProps, metoda](imetadataassemblyemit-setfileprops-method.md)|Modyfikuje określoną `File` strukturę metadanych.|  
|[SetManifestResourceProps, metoda](imetadataassemblyemit-setmanifestresourceprops-method.md)|Modyfikuje określoną `ManifestResource` strukturę metadanych.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy metadanych](metadata-interfaces.md)
- [IMetaDataAssemblyImport — Interfejs](imetadataassemblyimport-interface.md)
