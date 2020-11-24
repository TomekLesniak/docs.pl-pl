---
title: IMetaDataImport — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport
helpviewer_keywords:
- IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0adbbd35-5e8d-4fec-8268-dc70a07c5975
topic_type:
- apiref
ms.openlocfilehash: 0049db66d7a753488388c85e87e1f907db56c7cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679094"
---
# <a name="imetadataimport-interface"></a>IMetaDataImport — Interfejs

Zapewnia metody importowania i manipulowania istniejącymi metadanymi z przenośnego pliku wykonywalnego (PE) lub innego źródła, takiego jak biblioteka typów lub autonomiczny plik binarny metadanych w czasie wykonywania.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[CloseEnum — Metoda](imetadataimport-closeenum-method.md)|Zamyka moduł wyliczający z określonym dojściem.|  
|[CountEnum, metoda](imetadataimport-countenum-method.md)|Pobiera liczbę elementów w module wyliczającym z określonym dojściem.|  
|[EnumCustomAttributes — Metoda](imetadataimport-enumcustomattributes-method.md)|Wylicza listę niestandardowych tokenów definicji atrybutów skojarzonych z określonym typem lub członkiem.|  
|[EnumEvents, metoda](imetadataimport-enumevents-method.md)|Wylicza tokeny definicji zdarzeń dla określonego tokenu TypeDef.|  
|[EnumFields, metoda](imetadataimport-enumfields-method.md)|Wylicza tokeny FieldDef dla typu, do którego odwołuje się określony token TypeDef.|  
|[EnumFieldsWithName, metoda](imetadataimport-enumfieldswithname-method.md)|Wylicza tokeny FieldDef określonego typu o określonej nazwie.|  
|[EnumInterfaceImpls, metoda](imetadataimport-enuminterfaceimpls-method.md)|Wylicza tokeny MethodDef reprezentujące implementacje interfejsu.|  
|[EnumMemberRefs, metoda](imetadataimport-enummemberrefs-method.md)|Wylicza tokeny elementu MemberRef reprezentujące elementy członkowskie określonego typu.|  
|[EnumMembers, metoda](imetadataimport-enummembers-method.md)|Wylicza tokeny MemberDef reprezentujące składowe określonego typu.|  
|[EnumMembersWithName, metoda](imetadataimport-enummemberswithname-method.md)|Wylicza tokeny MemberDef reprezentujące elementy członkowskie określonego typu o określonej nazwie.|  
|[EnumMethodImpls, metoda](imetadataimport-enummethodimpls-method.md)|Wylicza tokeny MethodBody i MethodDeclaration reprezentujące metody określonego typu.|  
|[EnumMethods, metoda](imetadataimport-enummethods-method.md)|Wylicza tokeny MethodDef reprezentujące metody określonego typu.|  
|[EnumMethodSemantics, metoda](imetadataimport-enummethodsemantics-method.md)|Wylicza właściwości i zdarzenia zmiany właściwości, z którymi powiązana jest określona metoda.|  
|[EnumMethodsWithName, metoda](imetadataimport-enummethodswithname-method.md)|Wylicza metody, które mają określoną nazwę i które są definiowane przez typ, do którego odwołuje się określony token TypeDef.|  
|[EnumModuleRefs, metoda](imetadataimport-enummodulerefs-method.md)|Wylicza tokeny ModuleRef reprezentujące importowane moduły.|  
|[EnumParams, metoda](imetadataimport-enumparams-method.md)|Wylicza tokeny ParamDef reprezentujące parametry metody przywoływanej przez określony token MethodDef.|  
|[EnumPermissionSets, metoda](imetadataimport-enumpermissionsets-method.md)|Wylicza uprawnienia dla obiektów w określonym zakresie metadanych.|  
|[EnumProperties, metoda](imetadataimport-enumproperties-method.md)|Wylicza tokeny PropertyDef reprezentujące właściwości typu, do którego odwołuje się określony token TypeDef.|  
|[EnumSignatures, metoda](imetadataimport-enumsignatures-method.md)|Wylicza tokeny podpisu reprezentujące podpisy autonomiczne w bieżącym zakresie.|  
|[EnumTypeDefs, metoda](imetadataimport-enumtypedefs-method.md)|Wylicza tokeny TypeDef reprezentujące wszystkie typy w bieżącym zakresie.|  
|[EnumTypeRefs, metoda](imetadataimport-enumtyperefs-method.md)|Wylicza tokeny TypeRef zdefiniowane w bieżącym zakresie metadanych.|  
|[EnumTypeSpecs, metoda](imetadataimport-enumtypespecs-method.md)|Wylicza tokeny elementu TypeSpec zdefiniowane w bieżącym zakresie metadanych.|  
|[EnumUnresolvedMethods, metoda](imetadataimport-enumunresolvedmethods-method.md)|Wylicza tokeny MemberDef reprezentujące nierozpoznane metody w bieżącym zakresie metadanych.|  
|[EnumUserStrings, metoda](imetadataimport-enumuserstrings-method.md)|Wylicza tokeny ciągów reprezentujące stałe ciągi w bieżącym zakresie metadanych.|  
|[FindField, metoda](imetadataimport-findfield-method.md)|Pobiera token FieldDef dla pola, które jest elementem członkowskim określonego typu i ma określoną nazwę i sygnaturę metadanych.|  
|[FindMember, metoda](imetadataimport-findmember-method.md)|Pobiera wskaźnik do tokenu MemberDef dla elementu członkowskiego zdefiniowanego przez określony typ z określoną nazwą i sygnaturą metadanych.|  
|[FindMemberRef, metoda](imetadataimport-findmemberref-method.md)|Pobiera wskaźnik do tokenu MemberRef dla elementu członkowskiego zdefiniowanego przez określony typ z określoną nazwą i sygnaturą metadanych.|  
|[FindMethod, metoda](imetadataimport-findmethod-method.md)|Pobiera wskaźnik do tokenu MethodDef dla metody zdefiniowanej przez określony typ z określoną nazwą i sygnaturą metadanych.|  
|[FindTypeDefByName, metoda](imetadataimport-findtypedefbyname-method.md)|Pobiera wskaźnik do tokenu metadanych TypeDef dla typu o określonej nazwie.|  
|[FindTypeRef, metoda](imetadataimport-findtyperef-method.md)|Pobiera wskaźnik do tokenu metadanych elementu TypeRef, który odwołuje się do typu w określonym zakresie wyszukiwania o określonej nazwie.|  
|[GetClassLayout, metoda](imetadataimport-getclasslayout-method.md)|Pobiera informacje o układzie dla klasy, do której odwołuje się określony token TypeDef.|  
|[GetCustomAttributeByName, metoda](imetadataimport-getcustomattributebyname-method.md)|Pobiera wartość atrybutu niestandardowego pod nazwą.|  
|[GetCustomAttributeProps, metoda](imetadataimport-getcustomattributeprops-method.md)|Pobiera wartość atrybutu niestandardowego z uwzględnieniem jego tokenu metadanych.|  
|[GetEventProps, metoda](imetadataimport-geteventprops-method.md)|Pobiera informacje o metadanych (w tym typ deklarujący, metody dodawania i usuwania dla delegatów oraz wszelkie flagi i inne powiązane dane) dla zdarzenia reprezentowanego przez określony token zdarzenia.|  
|[GetFieldMarshal, metoda](imetadataimport-getfieldmarshal-method.md)|Pobiera wskaźnik do natywnego, niezarządzanego typu pola reprezentowanego przez określony token metadanych pola.|  
|[GetFieldProps, metoda](imetadataimport-getfieldprops-method.md)|Pobiera metadane skojarzone z polem, do którego odwołuje się określony token FieldDef.|  
|[GetInterfaceImplProps, metoda](imetadataimport-getinterfaceimplprops-method.md)|Pobiera wskaźnik do tokenów metadanych dla typu, który implementuje określoną metodę i dla interfejsu, który deklaruje tę metodę.|  
|[GetMemberProps, metoda](imetadataimport-getmemberprops-method.md)|Pobiera informacje o metadanych (w tym nazwę, podpis binarny i względny adres wirtualny) elementu członkowskiego typu, do którego odwołuje się określony token metadanych.|  
|[GetMemberRefProps, metoda](imetadataimport-getmemberrefprops-method.md)|Pobiera metadane skojarzone z elementem członkowskim, do którego odwołuje się określony token.|  
|[GetMethodProps — Metoda](imetadataimport-getmethodprops-method.md)|Pobiera metadane skojarzone z metodą przywoływaną przez określony token MethodDef.|  
|[GetMethodSemantics, metoda](imetadataimport-getmethodsemantics-method.md)|Pobiera wskaźnik do relacji między metodą przywoływaną przez określony token MethodDef i sparowaną właściwością i zdarzeniem, do którego odwołuje się określony token EventProp.|  
|[GetModuleFromScope, metoda](imetadataimport-getmodulefromscope-method.md)|Pobiera wskaźnik do tokenu metadanych dla modułu, do którego odwołuje się bieżący zakres metadanych.|  
|[GetModuleRefProps, metoda](imetadataimport-getmodulerefprops-method.md)|Pobiera nazwę modułu, do którego odwołuje się określony token metadanych.|  
|[GetNameFromToken, metoda](imetadataimport-getnamefromtoken-method.md)|Pobiera nazwę UTF-8 obiektu, do którego odwołuje się określony token metadanych.|  
|[GetNativeCallConvFromSig, metoda](imetadataimport-getnativecallconvfromsig-method.md)|Pobiera natywną konwencję wywoływania dla metody reprezentowanej przez określony wskaźnik podpisu.|  
|[GetNestedClassProps, metoda](imetadataimport-getnestedclassprops-method.md)|Pobiera token TypeDef dla otaczającego typu nadrzędnego określonego typu zagnieżdżonego.|  
|[GetParamForMethodIndex, metoda](imetadataimport-getparamformethodindex-method.md)|Pobiera wskaźnik do tokenu, który reprezentuje parametr w określonej pozycji porządkowej w sekwencji parametrów metody dla metody reprezentowanej przez określony token MethodDef.|  
|[GetParamProps, metoda](imetadataimport-getparamprops-method.md)|Pobiera wartości metadanych dla parametru, do którego odwołuje się określony token ParamDef.|  
|[GetPermissionSetProps, metoda](imetadataimport-getpermissionsetprops-method.md)|Pobiera metadane skojarzone z System. Security. PermissionSet reprezentowane przez określony token uprawnień.|  
|[GetPinvokeMap](imetadataimport-getpinvokemap-method.md)|Pobiera token typu ModuleRef reprezentujący zestaw docelowy wywołania PInvoke.|  
|[GetPropertyProps, metoda](imetadataimport-getpropertyprops-method.md)|Pobiera metadane skojarzone z właściwością reprezentowaną przez określony token.|  
|[GetRVA, metoda](imetadataimport-getrva-method.md)|Pobiera przesunięcie względnego adresu wirtualnego obiektu kodu reprezentowanego przez określony token.|  
|[GetScopeProps, metoda](imetadataimport-getscopeprops-method.md)|Pobiera nazwę i opcjonalnie identyfikator wersji zestawu lub modułu w bieżącym zakresie metadanych.|  
|[GetSigFromToken, metoda](imetadataimport-getsigfromtoken-method.md)|Pobiera binarny podpis metadanych skojarzony z określonym tokenem.|  
|[GetTypeDefProps, metoda](imetadataimport-gettypedefprops-method.md)|Zwraca informacje o metadanych dla typu reprezentowanego przez określony token TypeDef.|  
|[GetTypeRefProps, metoda](imetadataimport-gettyperefprops-method.md)|Pobiera metadane skojarzone z typem przywoływanym przez określony token elementu TypeRef.|  
|[GetTypeSpecFromToken, metoda](imetadataimport-gettypespecfromtoken-method.md)|Pobiera binarny podpis metadanych specyfikacji typu reprezentowanej przez określony token.|  
|[GetUserString, metoda](imetadataimport-getuserstring-method.md)|Pobiera ciąg literału reprezentowanego przez określony token metadanych.|  
|[IsGlobal, metoda](imetadataimport-isglobal-method.md)|Pobiera wartość wskazującą, czy pole, metoda lub typ reprezentowane przez określony token metadanych ma zakres globalny.|  
|[IsValidToken, metoda](imetadataimport-isvalidtoken-method.md)|Pobiera wartość wskazującą, czy określony token przechowuje prawidłowe odwołanie do obiektu kodu.|  
|[ResetEnum, metoda](imetadataimport-resetenum-method.md)|Resetuje określony moduł wyliczający do określonego położenia.|  
|[ResolveTypeRef, metoda](imetadataimport-resolvetyperef-method.md)|Pobiera informacje o typie dla typu, do którego odwołuje się określony token elementu TypeRef.|  
  
## <a name="remarks"></a>Uwagi  

 Projekt `IMetaDataImport` interfejsu jest przeznaczony głównie do użytku przez narzędzia i usługi, które będą importować informacje o typie (na przykład narzędzia programistyczne) lub zarządzać wdrożonymi składnikami (na przykład w przypadku usług rozpoznawania/aktywacji). Metody w `IMetaDataImport` należą do następujących kategorii zadań:  
  
- Wyliczanie kolekcji elementów w zakresie metadanych.  
  
- Znajdowanie elementu, który ma określony zestaw właściwości.  
  
- Pobieranie właściwości określonego elementu.  
  
- Metody get są specjalnie zaprojektowane do zwracania właściwości jednowartościowych elementu metadanych. Gdy właściwość jest odwołaniem do innego elementu, zwracany jest token dla tego elementu. Dowolny typ wejściowy wskaźnika może mieć wartość NULL, aby wskazać, że określona wartość nie jest żądana. Aby uzyskać właściwości, które są zasadniczo obiektami kolekcji (na przykład kolekcje interfejsów, które implementuje Klasa), użyj metod wyliczania.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy metadanych](metadata-interfaces.md)
- [IMetaDataImport2 — Interfejs](imetadataimport2-interface.md)
