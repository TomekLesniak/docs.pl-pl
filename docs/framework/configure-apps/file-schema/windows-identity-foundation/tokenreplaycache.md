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

<span data-ttu-id="5e5d9-101">Rejestruje pamięć podręczną powtarzania tokenów za pomocą usługi lub kolekcji obsługi tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="5e5d9-101">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="5e5d9-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="5e5d9-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e5d9-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="5e5d9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="5e5d9-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="5e5d9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e5d9-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="5e5d9-105">Attributes</span></span>  
  
|<span data-ttu-id="5e5d9-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="5e5d9-106">Attribute</span></span>|<span data-ttu-id="5e5d9-107">Opis</span><span class="sxs-lookup"><span data-stu-id="5e5d9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e5d9-108">typ</span><span class="sxs-lookup"><span data-stu-id="5e5d9-108">type</span></span>|<span data-ttu-id="5e5d9-109">Typ, który pochodzi od <xref:System.IdentityModel.Tokens.TokenReplayCache> klasy.</span><span class="sxs-lookup"><span data-stu-id="5e5d9-109">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="5e5d9-110">Aby uzyskać więcej informacji na temat sposobu określania niestandardowego `type` , zobacz [odwołania do typów niestandardowych].</span><span class="sxs-lookup"><span data-stu-id="5e5d9-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="5e5d9-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="5e5d9-111">Child Elements</span></span>  

 <span data-ttu-id="5e5d9-112">Brak</span><span class="sxs-lookup"><span data-stu-id="5e5d9-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e5d9-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="5e5d9-113">Parent Elements</span></span>  
  
|<span data-ttu-id="5e5d9-114">Element</span><span class="sxs-lookup"><span data-stu-id="5e5d9-114">Element</span></span>|<span data-ttu-id="5e5d9-115">Opis</span><span class="sxs-lookup"><span data-stu-id="5e5d9-115">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="5e5d9-116">Rejestruje pamięci podręczne używane przez usługę lub kolekcję programu obsługi tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="5e5d9-116">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e5d9-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5e5d9-117">Remarks</span></span>  

 <span data-ttu-id="5e5d9-118">Pamięć podręczna powtarzania tokenów służy do wykrywania powtórzonych tokenów.</span><span class="sxs-lookup"><span data-stu-id="5e5d9-118">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="5e5d9-119">Wykrywanie powtarzania tokenów jest włączane przez [\<tokenReplayDetection>](tokenreplaydetection.md) element, który określa również maksymalny czas wygaśnięcia tokenów.</span><span class="sxs-lookup"><span data-stu-id="5e5d9-119">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e5d9-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="5e5d9-120">Example</span></span>  

 <span data-ttu-id="5e5d9-121">Poniższy kod XML przedstawia konfigurację niestandardowej pamięci podręcznej na potrzeby wykrywania ponownie odtwarzanych tokenów.</span><span class="sxs-lookup"><span data-stu-id="5e5d9-121">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e5d9-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5e5d9-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
