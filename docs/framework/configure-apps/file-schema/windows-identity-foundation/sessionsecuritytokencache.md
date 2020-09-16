---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 4169fe307e9ef7c391500a2292fcc247f435caa9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555890"
---
# \<sessionSecurityTokenCache>
<span data-ttu-id="e7d7f-101">Rejestruje pamięć podręczną tokenów sesji za pomocą usługi lub kolekcji obsługi tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="e7d7f-101">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**  
  
## <a name="syntax"></a><span data-ttu-id="e7d7f-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="e7d7f-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7d7f-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e7d7f-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e7d7f-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e7d7f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7d7f-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e7d7f-105">Attributes</span></span>  
  
|<span data-ttu-id="e7d7f-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="e7d7f-106">Attribute</span></span>|<span data-ttu-id="e7d7f-107">Opis</span><span class="sxs-lookup"><span data-stu-id="e7d7f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7d7f-108">typ</span><span class="sxs-lookup"><span data-stu-id="e7d7f-108">type</span></span>|<span data-ttu-id="e7d7f-109">Typ, który pochodzi od <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> klasy.</span><span class="sxs-lookup"><span data-stu-id="e7d7f-109">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7d7f-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e7d7f-110">Child Elements</span></span>  
 <span data-ttu-id="e7d7f-111">Brak</span><span class="sxs-lookup"><span data-stu-id="e7d7f-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7d7f-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e7d7f-112">Parent Elements</span></span>  
  
|<span data-ttu-id="e7d7f-113">Element</span><span class="sxs-lookup"><span data-stu-id="e7d7f-113">Element</span></span>|<span data-ttu-id="e7d7f-114">Opis</span><span class="sxs-lookup"><span data-stu-id="e7d7f-114">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="e7d7f-115">Rejestruje pamięci podręczne używane przez usługę lub kolekcję programu obsługi tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="e7d7f-115">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e7d7f-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="e7d7f-116">Example</span></span>  
 <span data-ttu-id="e7d7f-117">W poniższym kodzie XML przedstawiono konfigurację niestandardowej pamięci podręcznej dla tokenów zabezpieczających sesji ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ).</span><span class="sxs-lookup"><span data-stu-id="e7d7f-117">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="e7d7f-118">Konfiguracja jest pobierana z `ClaimsAwareWebFarm` przykładu.</span><span class="sxs-lookup"><span data-stu-id="e7d7f-118">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="e7d7f-119">Aby uzyskać więcej informacji na temat tego przykładu, zobacz [indeks przykładowego kodu WIF](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span><span class="sxs-lookup"><span data-stu-id="e7d7f-119">For more information about this sample, see [WIF Code Sample Index](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7d7f-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e7d7f-120">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
