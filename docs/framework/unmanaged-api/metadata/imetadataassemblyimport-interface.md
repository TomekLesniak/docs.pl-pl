---
title: IMetaDataAssemblyImport — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: c556fe247754b363ece0c5dc60750068276ddcc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714760"
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport — Interfejs

Zapewnia metody umożliwiające dostęp i sprawdzanie zawartości manifestu zestawu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[CloseEnum — Metoda](imetadataassemblyimport-closeenum-method.md)|Zwalnia dojście do określonego modułu wyliczającego.|  
|[EnumAssemblyRefs, metoda](imetadataassemblyimport-enumassemblyrefs-method.md)|Pobiera wskaźnik interfejsu do modułu wyliczającego, który zawiera `mdAssemblyRef` tokeny zestawów, do których odwołuje się zestaw w bieżącym zakresie metadanych.|  
|[EnumExportedTypes, metoda](imetadataassemblyimport-enumexportedtypes-method.md)|Pobiera wskaźnik interfejsu do modułu wyliczającego, który zawiera `mdExportedType` tokeny typów com, do których odwołuje się zestaw w bieżącym zakresie metadanych.|  
|[EnumFiles, metoda](imetadataassemblyimport-enumfiles-method.md)|Pobiera wskaźnik interfejsu do modułu wyliczającego, który zawiera `mdFile` tokeny plików, do których odwołuje się zestaw w bieżącym zakresie metadanych.|  
|[EnumManifestResources, metoda](imetadataassemblyimport-enummanifestresources-method.md)|Pobiera wskaźnik interfejsu do modułu wyliczającego, który zawiera `mdManifestResource` tokeny zasobów, do których odwołuje się zestaw w bieżącym zakresie metadanych.|  
|[FindAssembliesByName, metoda](imetadataassemblyimport-findassembliesbyname-method.md)|Pobiera tablicę `mdAssemblyRef` tokenów dla zestawów o określonej nazwie.|  
|[FindExportedTypeByName, metoda](imetadataassemblyimport-findexportedtypebyname-method.md)|Pobiera `mdExportedType` token dla typu com o określonej nazwie.|  
|[FindManifestResourceByName, metoda](imetadataassemblyimport-findmanifestresourcebyname-method.md)|Pobiera `mdManifestResource` token dla zasobu o określonej nazwie.|  
|[GetAssemblyFromScope, metoda](imetadataassemblyimport-getassemblyfromscope-method.md)|Pobiera token dla zestawu w bieżącym zakresie metadanych.|  
|[GetAssemblyProps, metoda](imetadataassemblyimport-getassemblyprops-method.md)|Pobiera ustawienia właściwości określonego zestawu.|  
|[GetAssemblyRefProps, metoda](imetadataassemblyimport-getassemblyrefprops-method.md)|Pobiera ustawienia właściwości określonego `mdAssemblyRef` tokenu.|  
|[GetExportedTypeProps, metoda](imetadataassemblyimport-getexportedtypeprops-method.md)|Pobiera ustawienia właściwości określonego typu COM.|  
|[GetFileProps, metoda](imetadataassemblyimport-getfileprops-method.md)|Pobiera ustawienia właściwości określonego pliku.|  
|[GetManifestResourceProps, metoda](imetadataassemblyimport-getmanifestresourceprops-method.md)|Pobiera ustawienia właściwości określonego zasobu manifestu.|  
  
## <a name="requirements"></a>Wymagania  

 **Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy metadanych](metadata-interfaces.md)
- [IMetaDataAssemblyEmit — Interfejs](imetadataassemblyemit-interface.md)
