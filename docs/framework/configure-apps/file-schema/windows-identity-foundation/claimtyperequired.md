---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: a86265ba3963ebc8bea880befbcf80345529116d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203855"
---
# \<claimTypeRequired>

<span data-ttu-id="c64d3-101">Określa zestaw wymaganych oświadczeń dla przychodzących tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="c64d3-101">Specifies the set of required claims for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**  
  
## <a name="syntax"></a><span data-ttu-id="c64d3-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="c64d3-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c64d3-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c64d3-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c64d3-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c64d3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c64d3-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c64d3-105">Attributes</span></span>  

 <span data-ttu-id="c64d3-106">Brak</span><span class="sxs-lookup"><span data-stu-id="c64d3-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c64d3-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c64d3-107">Child Elements</span></span>  
  
|<span data-ttu-id="c64d3-108">Element</span><span class="sxs-lookup"><span data-stu-id="c64d3-108">Element</span></span>|<span data-ttu-id="c64d3-109">Opis</span><span class="sxs-lookup"><span data-stu-id="c64d3-109">Description</span></span>|  
|-------------|-----------------|  
|[\<claimType>](claimtype.md)|<span data-ttu-id="c64d3-110">Określa jedno opcjonalne lub wymagane żądanie dla przychodzących tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="c64d3-110">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c64d3-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c64d3-111">Parent Elements</span></span>  
  
|<span data-ttu-id="c64d3-112">Element</span><span class="sxs-lookup"><span data-stu-id="c64d3-112">Element</span></span>|<span data-ttu-id="c64d3-113">Opis</span><span class="sxs-lookup"><span data-stu-id="c64d3-113">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="c64d3-114">Określa ustawienia tożsamości na poziomie usług.</span><span class="sxs-lookup"><span data-stu-id="c64d3-114">Specifies service-level identity settings.</span></span>|
