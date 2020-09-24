---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: 0f043442fb8edd9bf95a839a26cc42e8122d9100
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167070"
---
# \<clear>

<span data-ttu-id="4a5c2-101">Czyści wszystkie programy obsługi tokenów zabezpieczających z bieżącej kolekcji obsługi tokenów.</span><span class="sxs-lookup"><span data-stu-id="4a5c2-101">Clears all security token handlers from the current token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="4a5c2-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="4a5c2-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <clear>  
      </clear>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a5c2-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="4a5c2-103">Attributes and Elements</span></span>  

 <span data-ttu-id="4a5c2-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="4a5c2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a5c2-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="4a5c2-105">Attributes</span></span>  

 <span data-ttu-id="4a5c2-106">Brak</span><span class="sxs-lookup"><span data-stu-id="4a5c2-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4a5c2-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="4a5c2-107">Child Elements</span></span>  

 <span data-ttu-id="4a5c2-108">Brak</span><span class="sxs-lookup"><span data-stu-id="4a5c2-108">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a5c2-109">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="4a5c2-109">Parent Elements</span></span>  
  
|<span data-ttu-id="4a5c2-110">Element</span><span class="sxs-lookup"><span data-stu-id="4a5c2-110">Element</span></span>|<span data-ttu-id="4a5c2-111">Opis</span><span class="sxs-lookup"><span data-stu-id="4a5c2-111">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="4a5c2-112">Określa kolekcję programów obsługi tokenów zabezpieczających, które są zarejestrowane w punkcie końcowym.</span><span class="sxs-lookup"><span data-stu-id="4a5c2-112">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|
