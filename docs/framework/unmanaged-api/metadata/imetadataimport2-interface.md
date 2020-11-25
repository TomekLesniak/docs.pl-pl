---
title: IMetaDataImport2 — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: a845ecfde6583d625d2a8f165443344ff9e40d05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702553"
---
# <a name="imetadataimport2-interface"></a>IMetaDataImport2 — Interfejs

Rozszerza interfejs [IMetaDataImport](imetadataimport-interface.md) w celu zapewnienia możliwości pracy z typami ogólnymi.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[EnumGenericParamConstraints, metoda](imetadataimport2-enumgenericparamconstraints-method.md)|Pobiera moduł wyliczający dla tablicy ograniczeń parametrów ogólnych skojarzonych z parametrem ogólnym reprezentowanym przez określony token.|  
|[EnumGenericParams, metoda](imetadataimport2-enumgenericparams-method.md)|Pobiera moduł wyliczający dla tablicy tokenów parametrów ogólnych skojarzonych z określonym tokenem TypeDef lub MethodDef.|  
|[EnumMethodSpecs, metoda](imetadataimport2-enummethodspecs-method.md)|Pobiera moduł wyliczający dla tablicy tokenów elementu MethodSpec skojarzonych z określonym tokenem MethodDef lub MemberRef.|  
|[GetGenericParamConstraintProps, metoda](imetadataimport2-getgenericparamconstraintprops-method.md)|Pobiera metadane skojarzone z ograniczeniem parametru generycznego reprezentowane przez określony token ograniczenia.|  
|[GetGenericParamProps, metoda](imetadataimport2-getgenericparamprops-method.md)|Pobiera metadane skojarzone z parametrem ogólnym reprezentowanym przez określony token.|  
|[GetMethodSpecProps, metoda](imetadataimport2-getmethodspecprops-method.md)|Pobiera sygnaturę metadanych metody przywoływanej przez określony token elementu MethodSpec.|  
|[GetPEKind, metoda](imetadataimport2-getpekind-method.md)|Pobiera wartość identyfikującą charakter kodu w przenośnym pliku wykonywalnym (PE), zazwyczaj plik DLL lub EXE, zdefiniowany w bieżącym zakresie metadanych|  
|[GetVersionString, metoda](imetadataimport2-getversionstring-method.md)|Pobiera numer wersji środowiska uruchomieniowego, który został użyty do skompilowania zestawu.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Reflection.PortableExecutableKinds>
- [Interfejsy metadanych](metadata-interfaces.md)
- [IMetaDataImport — Interfejs](imetadataimport-interface.md)
