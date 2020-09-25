---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: e8f0e0fa2ea1606bf980fd6fa1fcd47f12c3b540
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204752"
---
# \<mexEndpoint>

<span data-ttu-id="784b8-101">Ten element konfiguracji definiuje standardowy punkt końcowy ze stałym kontraktem kontraktem IMetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="784b8-101">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="784b8-102">Ponieważ wszystkie punkty końcowe wymiany metadanych określają kontraktem IMetadataExchange jako kontrakt, można użyć tego standardowego punktu zamiast definiować go dla siebie.</span><span class="sxs-lookup"><span data-stu-id="784b8-102">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="784b8-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="784b8-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="784b8-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="784b8-104">Attributes and Elements</span></span>  

 <span data-ttu-id="784b8-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="784b8-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="784b8-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="784b8-106">Attributes</span></span>  
  
|<span data-ttu-id="784b8-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="784b8-107">Attribute</span></span>|<span data-ttu-id="784b8-108">Opis</span><span class="sxs-lookup"><span data-stu-id="784b8-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="784b8-109">name</span><span class="sxs-lookup"><span data-stu-id="784b8-109">name</span></span>|<span data-ttu-id="784b8-110">Ciąg określający nazwę konfiguracji standardowego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="784b8-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="784b8-111">Nazwa jest używana w `endpointConfiguration` atrybucie punktu końcowego usługi, aby połączyć standardowy punkt końcowy z jego konfiguracją.</span><span class="sxs-lookup"><span data-stu-id="784b8-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="784b8-112">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="784b8-112">Child Elements</span></span>  

 <span data-ttu-id="784b8-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="784b8-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="784b8-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="784b8-114">Parent Elements</span></span>  
  
|<span data-ttu-id="784b8-115">Element</span><span class="sxs-lookup"><span data-stu-id="784b8-115">Element</span></span>|<span data-ttu-id="784b8-116">Opis</span><span class="sxs-lookup"><span data-stu-id="784b8-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="784b8-117">Kolekcja standardowych punktów końcowych, które są wstępnie zdefiniowanymi punktami końcowymi z co najmniej jedną z jej właściwości (adres, powiązanie, kontrakt).</span><span class="sxs-lookup"><span data-stu-id="784b8-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
