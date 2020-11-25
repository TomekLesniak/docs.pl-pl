---
title: IAppIdAuthority — Interfejs
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
ms.openlocfilehash: a344f2ab5d9a7aa92018c47ee7a162cd1721aeb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732115"
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority — Interfejs

Dostarcza metody, które generują i porównują klucze dla tożsamości i odwołań aplikacji.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Pobiera wartość wskazującą, czy dwa określone wystąpienia [IDefinitionAppId —](idefinitionappid-interface.md) są równe. Można przekazać wartość flagi IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, aby zignorować odpowiednie informacje o wersji.|  
|`IAppIdAuthority::AreReferencesEqual`|Pobiera wartość wskazującą, czy dwa określone wystąpienia [IReferenceAppId —](ireferenceappid-interface.md) są równe. Można przekazać wartość flagi IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, aby zignorować odpowiednie informacje o wersji.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Pobiera wartość wskazującą, czy dwa określone definicje ciągów są równe. Można przekazać wartość flagi IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, aby zignorować odpowiednie informacje o wersji.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Pobiera wartość wskazującą, czy dwa określone odwołania do ciągu są równe. Można przekazać wartość flagi IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, aby zignorować odpowiednie informacje o wersji.|  
|`IAppIdAuthority::CreateDefinition`|Pobiera wskaźnik interfejsu do nowo wygenerowanego `IDefinitionAppId` wystąpienia, które reprezentuje zestaw w bieżącym zakresie.|  
|`IAppIdAuthority::CreateReference`|Pobiera wskaźnik interfejsu do nowo utworzonego `IReferenceAppId` , który reprezentuje zestaw w bieżącym zakresie.|  
|`IAppIdAuthority::DefinitionToText`|Pobiera wersję ciągu określonego `IDefinitionAppId` przy użyciu określonych wartości flagi.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Pobiera wartość wskazującą, czy określony `IDefinitionAppId` i reprezentuje ten `IReferenceAppId` sam zestaw.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Pobiera wartość wskazującą, czy określony ciąg definicji i ciąg odwołania reprezentują ten sam zestaw.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Pobiera klucz ciągu, który reprezentuje określone `IDefinitionAppId` wystąpienie.|  
|`IAppIdAuthority::GenerateReferenceKey`|Pobiera klucz ciągu, który reprezentuje określone `IReferenceAppId` wystąpienie.|  
|`IAppIdAuthority::HashDefinition`|Pobiera klucz skrótu dla określonego `IDefinitionAppId` wystąpienia.|  
|`IAppIdAuthority::HashReference`|Pobiera klucz skrótu dla określonego `IReferenceAppId` wystąpienia.|  
|`IAppIdAuthority::ReferenceToText`|Pobiera wersję ciągu określonego `IReferenceAppId` przy użyciu określonych wartości flagi.|  
|`IAppIdAuthority::TextToDefinition`|Pobiera wskaźnik interfejsu do `IDefinitionAppId` wystąpienia, które reprezentuje zestaw, do którego odwołuje się określony klucz ciągu.|  
|`IAppIdAuthority::TextToReference`|Pobiera wskaźnik interfejsu do `IReferenceAppId` wystąpienia, które reprezentuje zestaw, do którego odwołuje się określony klucz ciągu.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Izolacja. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy łączenia](fusion-interfaces.md)
