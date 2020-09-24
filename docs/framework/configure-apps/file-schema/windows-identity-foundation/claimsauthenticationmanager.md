---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 9e099b8de486631702548b8a035a46a7e0f4eb30
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158477"
---
# \<claimsAuthenticationManager>

Rejestruje Menedżera uwierzytelniania oświadczeń dla oświadczeń przychodzących.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|typ|Określa typ niestandardowy, który pochodzi od <xref:System.Security.Claims.ClaimsAuthenticationManager> klasy. Aby uzyskać więcej informacji na temat sposobu określania `type` atrybutu, zobacz [odwołania do typów niestandardowych].|  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Jeśli nie ma `type` atrybutu lub jeśli `type` atrybut odwołuje się do <xref:System.Security.Claims.ClaimsAuthenticationManager> klasy, element nie `<claimsAuthenticationManager>` przyjmuje elementów podrzędnych, jednak klasy pochodne <xref:System.Security.Claims.ClaimsAuthenticationManager> mogą definiować podrzędne elementy konfiguracji.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Określa ustawienia tożsamości na poziomie usług.|  
  
## <a name="remarks"></a>Uwagi  

 Domyślne zachowanie udostępniane przez klasę zwraca <xref:System.Security.Claims.ClaimsAuthenticationManager> oświadczenia przychodzące. Jeśli nie `type` określono atrybutu lub jeśli `type` atrybut określa <xref:System.Security.Claims.ClaimsAuthenticationManager> klasę, `<claimsAuthenticationManager>` element nie przyjmuje elementów podrzędnych. Możesz określić atrybut, `type` Aby zarejestrować typ pochodny <xref:System.Security.Claims.ClaimsAuthenticationManager> klasy, aby zaimplementować zachowanie niestandardowe. Klasy pochodne mogą obsługiwać konfigurację za pomocą elementów podrzędnych `<claimsAuthenticationManager>` elementu przez zastąpienie <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> metody do obsługi tych elementów. Schemat zdefiniowany dla elementów podrzędnych jest projektantem klasy.  
  
 `<claimsAuthenticationManager>`Element ustawia <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> Właściwość.  
  
## <a name="example"></a>Przykład  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
