---
title: IMetaDataEmit — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit
helpviewer_keywords:
- IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type:
- apiref
ms.openlocfilehash: f5495c170abf3e991a6e28016687f8ae77f0b423
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722027"
---
# <a name="imetadataemit-interface"></a>IMetaDataEmit — Interfejs

Zapewnia metody tworzenia, modyfikowania i zapisywania metadanych dotyczących zestawu w aktualnie zdefiniowanym zakresie. Metadane mogą być przechowywane w pamięci lub zapisywane na dysku.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[ApplyEditAndContinue, metoda](imetadataemit-applyeditandcontinue-method.md)|Aktualizuje bieżący zakres zestawu zmianami wprowadzonymi w określonym `pImport` .|  
|[DefineCustomAttribute, metoda](imetadataemit-definecustomattribute-method.md)|Tworzy definicję atrybutu niestandardowego z określonym podpisem metadanych do dołączenia do określonego obiektu i pobiera token do tej definicji atrybutu niestandardowego.|  
|[DefineEvent, metoda](imetadataemit-defineevent-method.md)|Tworzy definicję zdarzenia z określonym podpisem metadanych i pobiera token do tej definicji zdarzenia.|  
|[DefineField — Metoda](imetadataemit-definefield-method.md)|Tworzy definicję dla pola z określonym podpisem metadanych i pobiera token do tej definicji pola.|  
|[DefineImportMember, metoda](imetadataemit-defineimportmember-method.md)|Tworzy definicję dla elementu członkowskiego typu, który jest zdefiniowany w module poza bieżącym zakresem, i pobiera token dla tej definicji odwołania.|  
|[DefineImportType, metoda](imetadataemit-defineimporttype-method.md)|Tworzy definicję odwołania do typu, który jest zdefiniowany w module poza bieżącym zakresem, i pobiera token do tej definicji odwołania.|  
|[DefineMemberRef, metoda](imetadataemit-definememberref-method.md)|Tworzy definicję odwołania do elementu członkowskiego modułu poza bieżącym zakresem i pobiera token do tej definicji odwołania.|  
|[DefineMethod, metoda](imetadataemit-definemethod-method.md)|Tworzy definicję metody z określonym podpisem i zwraca token do tej definicji metody.|  
|[DefineMethodImpl, metoda](imetadataemit-definemethodimpl-method.md)|Tworzy definicję dla implementacji metody dziedziczonej z interfejsu i zwraca token do tej definicji implementacji metody.|  
|[DefineModuleRef, metoda](imetadataemit-definemoduleref-method.md)|Tworzy sygnaturę metadanych dla modułu o określonej nazwie.|  
|[DefineNestedType, metoda](imetadataemit-definenestedtype-method.md)|Tworzy sygnaturę metadanych definicji typu i zwraca `mdTypeDef` token dla tego typu, a także określa, że zdefiniowany typ jest członkiem typu, do którego odwołuje się `tdEncloser` .|  
|[DefineParam, metoda](imetadataemit-defineparam-method.md)|Tworzy definicję parametru z określonym podpisem dla metody przywoływanej przez określony token i pobiera token dla tej definicji parametru.|  
|[DefinePermissionSet, metoda](imetadataemit-definepermissionset-method.md)|Tworzy definicję zestawu uprawnień z określonym podpisem metadanych i pobiera token do tej definicji zestawu uprawnień.|  
|[DefinePinvokeMap, metoda](imetadataemit-definepinvokemap-method.md)|Ustawia funkcje podpisu PInvoke metody, do której odwołuje się określony token.|  
|[DefineProperty, metoda](imetadataemit-defineproperty-method.md)|Tworzy definicję właściwości określonego typu, z określonymi `get` `set` metodami dostępu, i pobiera token do tej definicji właściwości.|  
|[DefineSecurityAttributeSet, metoda](imetadataemit-definesecurityattributeset-method.md)|Tworzy zestaw uprawnień zabezpieczeń do dołączenia do obiektu, do którego odwołuje się określony token.|  
|[DefineTypeDef, metoda](imetadataemit-definetypedef-method.md)|Tworzy definicję typu dla typu środowiska uruchomieniowego języka wspólnego i pobiera token metadanych do tej definicji typu.|  
|[DefineTypeRefByName, metoda](imetadataemit-definetyperefbyname-method.md)|Pobiera token metadanych dla typu, który jest zdefiniowany w innym module poza bieżącym zakresem.|  
|[DefineUserString, metoda](imetadataemit-defineuserstring-method.md)|Pobiera token metadanych dla określonego ciągu literału.|  
|[DeleteClassLayout, metoda](imetadataemit-deleteclasslayout-method.md)|Niszczy sygnaturę metadanych układu klasy dla typu, do którego odwołuje się określony token.|  
|[DeleteFieldMarshal, metoda](imetadataemit-deletefieldmarshal-method.md)|Niszczy sygnaturę metadanych kierowania PInvoke dla obiektu, do którego odwołuje się określony token.|  
|[DeletePinvokeMap, metoda](imetadataemit-deletepinvokemap-method.md)|Niszczy metadane mapowania PInvoke dla obiektu, do którego odwołuje się określony token.|  
|[DeleteToken, metoda](imetadataemit-deletetoken-method.md)|Usuwa określony token z bieżącego zakresu metadanych.|  
|[GetSaveSize, metoda](imetadataemit-getsavesize-method.md)|Pobiera Szacowany rozmiar binarny zestawu w bieżącym zakresie.|  
|[GetTokenFromSig, metoda](imetadataemit-gettokenfromsig-method.md)|Pobiera token dla określonej sygnatury metadanych.|  
|[GetTokenFromTypeSpec, metoda](imetadataemit-gettokenfromtypespec-method.md)|Pobiera token metadanych dla typu z określonym podpisem metadanych.|  
|[Merge, metoda](imetadataemit-merge-method.md)|Dodaje określony zaimportowany zakres do listy zakresów, które mają zostać scalone.|  
|[MergeEnd, metoda](imetadataemit-mergeend-method.md)|Scala do bieżącego zakresu wszystkich zakresów metadanych określonych przez jedno lub więcej wcześniejszych wywołań do `IMetaDataEmit::Merge` .|  
|[Save, metoda](imetadataemit-save-method.md)|Zapisuje wszystkie metadane w bieżącym zakresie do pliku pod określonym adresem.|  
|[SaveToMemory, metoda](imetadataemit-savetomemory-method.md)|Zapisuje wszystkie metadane w bieżącym zakresie do określonego obszaru pamięci.|  
|[SaveToStream, metoda](imetadataemit-savetostream-method.md)|Zapisuje wszystkie metadane w bieżącym zakresie do określonego `IStream` .|  
|[SetClassLayout, metoda](imetadataemit-setclasslayout-method.md)|Ustawia lub aktualizuje sygnaturę układu klasy typu zdefiniowanego przez poprzednie wywołanie do `IMetaDataEmit::DefineTypeDef` .|  
|[SetCustomAttributeValue, metoda](imetadataemit-setcustomattributevalue-method.md)|Ustawia lub aktualizuje wartość atrybutu niestandardowego zdefiniowanego przez poprzednie wywołanie do `IMetaDataEmit::DefineCustomAttribute` .|  
|[SetEventProps, metoda](imetadataemit-seteventprops-method.md)|Ustawia lub aktualizuje określoną funkcję zdarzenia zdefiniowaną przez poprzednie wywołanie do `IMetaDataEmit::DefineEvent` .|  
|[SetFieldMarshal, metoda](imetadataemit-setfieldmarshal-method.md)|Ustawia informacje o kierowaniu PInvoke dla parametru, zwraca metodę lub parametr metody, do którego odwołuje się określony token.|  
|[SetFieldProps, metoda](imetadataemit-setfieldprops-method.md)|Ustawia lub aktualizuje wartość domyślną dla pola, do którego odwołuje się określony token pola.|  
|[SetFieldRVA, metoda](imetadataemit-setfieldrva-method.md)|Ustawia wartość zmiennej globalnej dla względnego adresu wirtualnego pola, do którego odwołuje się określony token.|  
|[SetHandler, metoda](imetadataemit-sethandler-method.md)|Ustawia metodę przywoływaną przez określony `IUnknown` wskaźnik jako wywołanie zwrotne powiadomienia o ponownym mapowaniu tokenu.|  
|[SetMethodImplFlags, metoda](imetadataemit-setmethodimplflags-method.md)|Ustawia lub aktualizuje podpis metadanych dziedziczonej metody, do której odwołuje się określony token.|  
|[SetMethodProps, metoda](imetadataemit-setmethodprops-method.md)|Ustawia lub aktualizuje funkcję przechowywaną w określonym względnie wirtualnym adresie metody zdefiniowanej przez poprzednie wywołanie do `IMetaDataEmit::DefineMethod` .|  
|[SetModuleProps, metoda](imetadataemit-setmoduleprops-method.md)|Aktualizuje odwołania do modułu zdefiniowanego przez poprzednie wywołanie do `IMetaDataEmit::DefineModuleRef` .|  
|[SetParamProps, metoda](imetadataemit-setparamprops-method.md)|Ustawia lub zmienia funkcje parametru metody, który został zdefiniowany przez poprzednie wywołanie do `IMetaDataEmit::DefineParam` .|  
|[SetParent, metoda](imetadataemit-setparent-method.md)|Określa, że określony element członkowski zdefiniowany przez poprzednie wywołanie do `IMetaDataEmit::DefineMemberRef` , jest składową określonego typu, zgodnie z wcześniejszym wywołaniem do `IMetaDataEmit::DefineTypeDef` .|  
|[SetPermissionSetProps, metoda](imetadataemit-setpermissionsetprops-method.md)|Ustawia lub aktualizuje funkcje podpisu metadanych zestawu uprawnień zdefiniowanego przez poprzednie wywołanie do `IMetaDataEmit::DefinePermissionSet` .|  
|[SetPinvokeMap, metoda](imetadataemit-setpinvokemap-method.md)|Ustawia lub zmienia funkcje podpisu PInvoke metody, zgodnie z definicją w poprzednim wywołaniu do `IMetaDataEmit::DefinePinvokeMap` .|  
|[SetPropertyProps, metoda](imetadataemit-setpropertyprops-method.md)|Ustawia funkcje przechowywane w metadanych dla właściwości zdefiniowanej przez poprzednie wywołanie do `IMetaDataEmit::DefineProperty` .|  
|[SetRVA, metoda](imetadataemit-setrva-method.md)|Ustawia względny adres wirtualny określonej metody.|  
|[SetTypeDefProps, metoda](imetadataemit-settypedefprops-method.md)|Ustawia funkcje typu zdefiniowanego przez poprzednie wywołanie do `IMetaDataEmit::DefineTypeDef` .|  
|[TranslateSigWithScope, metoda](imetadataemit-translatesigwithscope-method.md)|Importuje zestaw do bieżącego zakresu i pobiera nowy podpis metadanych dla scalonego zakresu.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy metadanych](metadata-interfaces.md)
- [IMetaDataEmit2 — Interfejs](imetadataemit2-interface.md)
