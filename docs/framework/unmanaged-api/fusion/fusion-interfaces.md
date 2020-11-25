---
title: Interfejsy łączenia
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
ms.openlocfilehash: 59e34a39bada1dcf5e66a0c5b92a7fcbfb41d884
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711692"
---
# <a name="fusion-interfaces"></a>Interfejsy łączenia

W tej sekcji opisano niezarządzane interfejsy, które są używane przez interfejs API Fusion do uzyskiwania dostępu do właściwości zasobów aplikacji i lokalizowania odpowiednich wersji tych zasobów dla aplikacji.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [IAppIdAuthority — Interfejs](iappidauthority-interface.md)  
 Dostarcza metody, które generują i porównują klucze dla tożsamości i odwołań aplikacji.  
  
 [IAssemblyCache — Interfejs](iassemblycache-interface.md)  
 Przedstawia reprezentację globalnej pamięci podręcznej zestawów.  
  
 [IAssemblyCacheItem — Interfejs](iassemblycacheitem-interface.md)  
 Reprezentuje pojedynczy zestaw w globalnej pamięci podręcznej zestawów.  
  
 [IAssemblyEnum — Interfejs](iassemblyenum-interface.md)  
 Reprezentuje moduł wyliczający dla tablicy `IAssemblyName` obiektów.  
  
 [IAssemblyName — Interfejs](iassemblyname-interface.md)  
 Zapewnia metody opisujące unikatową tożsamość zestawu i pracę z nim.  
  
 [IDefinitionAppId — Interfejs](idefinitionappid-interface.md)  
 Reprezentuje unikatowy identyfikator kodu, który definiuje aplikację w bieżącym zakresie.  
  
 [IDefinitionIdentity — Interfejs](idefinitionidentity-interface.md)  
 Reprezentuje unikatowy podpis kodu, który definiuje aplikację w bieżącym zakresie.  
  
 [IEnumDefinitionIdentity — Interfejs](ienumdefinitionidentity-interface.md)  
 Służy jako moduł wyliczający dla kolekcji `IDefinitionIdentity` obiektów.  
  
 [IEnumIDENTITY_ATTRIBUTE — Interfejs](ienumidentity-attribute-interface.md)  
 Służy jako moduł wyliczający dla atrybutów obiektu kodu w bieżącym zakresie.  
  
 [IEnumReferenceIdentity — Interfejs](ienumreferenceidentity-interface.md)  
 Służy jako moduł wyliczający dla kolekcji `IReferenceIdentity` obiektów.  
  
 [IIdentityAuthority — Interfejs](iidentityauthority-interface.md)  
 Zarządza kluczami tożsamości dla obiektów kodu.  
  
 [IInstallReferenceEnum — Interfejs](iinstallreferenceenum-interface.md)  
 Reprezentuje moduł wyliczający dla zestawów, do których istnieją odwołania zainstalowane w globalnej pamięci podręcznej zestawów.  
  
 [IInstallReferenceItem — Interfejs](iinstallreferenceitem-interface.md)  
 Reprezentuje element zainstalowany w globalnej pamięci podręcznej zestawów.  
  
 [IReferenceAppId — Interfejs](ireferenceappid-interface.md)  
 Reprezentuje odwołanie do unikatowego identyfikatora aplikacji w bieżącym zakresie.  
  
 [IReferenceIdentity — Interfejs](ireferenceidentity-interface.md)  
 Reprezentuje odwołanie do unikatowego podpisu obiektu kodu.  
  
## <a name="reference"></a>Dokumentacja  

 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Łączenie statycznych funkcji globalnych](fusion-global-static-functions.md)  
  
 [Wyliczenia łączenia](fusion-enumerations.md)  
  
 [Łączenie — Struktury](fusion-structures.md)
