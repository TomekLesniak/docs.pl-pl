---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5e695bb56b59da40ce9e83f9f4f77d0d22d0b40f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202425"
---
# \<tokenReplayCache>

Rejestruje pamięć podręczną powtarzania tokenów za pomocą usługi lub kolekcji obsługi tokenów zabezpieczających.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|typ|Typ, który pochodzi od <xref:System.IdentityModel.Tokens.TokenReplayCache> klasy. Aby uzyskać więcej informacji na temat sposobu określania niestandardowego `type` , zobacz [odwołania do typów niestandardowych].
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<caches>](caches.md)|Rejestruje pamięci podręczne używane przez usługę lub kolekcję programu obsługi tokenów zabezpieczających.|  
  
## <a name="remarks"></a>Uwagi  

 Pamięć podręczna powtarzania tokenów służy do wykrywania powtórzonych tokenów. Wykrywanie powtarzania tokenów jest włączane przez [\<tokenReplayDetection>](tokenreplaydetection.md) element, który określa również maksymalny czas wygaśnięcia tokenów.  
  
## <a name="example"></a>Przykład  

 Poniższy kod XML przedstawia konfigurację niestandardowej pamięci podręcznej na potrzeby wykrywania ponownie odtwarzanych tokenów.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
