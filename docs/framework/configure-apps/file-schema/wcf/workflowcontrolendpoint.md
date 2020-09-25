---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 572ff7e119828897860944a430e5f51f5d1c3cad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194846"
---
# \<workflowControlEndpoint>

<span data-ttu-id="92f86-101">Ten element konfiguracji definiuje standardowy punkt końcowy do kontroli wykonania wystąpień przepływu pracy (tworzenie, uruchamianie, wstrzymywanie, przerywanie itp.).</span><span class="sxs-lookup"><span data-stu-id="92f86-101">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="92f86-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="92f86-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92f86-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="92f86-103">Attributes and Elements</span></span>  

 <span data-ttu-id="92f86-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="92f86-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92f86-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="92f86-105">Attributes</span></span>  
  
|<span data-ttu-id="92f86-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="92f86-106">Attribute</span></span>|<span data-ttu-id="92f86-107">Opis</span><span class="sxs-lookup"><span data-stu-id="92f86-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92f86-108">name</span><span class="sxs-lookup"><span data-stu-id="92f86-108">name</span></span>|<span data-ttu-id="92f86-109">Ciąg określający nazwę konfiguracji standardowego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="92f86-109">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="92f86-110">Nazwa jest używana w `endpointConfiguration` atrybucie punktu końcowego usługi, aby połączyć standardowy punkt końcowy z jego konfiguracją.</span><span class="sxs-lookup"><span data-stu-id="92f86-110">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92f86-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="92f86-111">Child Elements</span></span>  

 <span data-ttu-id="92f86-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="92f86-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92f86-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="92f86-113">Parent Elements</span></span>  
  
|<span data-ttu-id="92f86-114">Element</span><span class="sxs-lookup"><span data-stu-id="92f86-114">Element</span></span>|<span data-ttu-id="92f86-115">Opis</span><span class="sxs-lookup"><span data-stu-id="92f86-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="92f86-116">Kolekcja standardowych punktów końcowych, które są wstępnie zdefiniowanymi punktami końcowymi z co najmniej jedną z jej właściwości (adres, powiązanie, kontrakt).</span><span class="sxs-lookup"><span data-stu-id="92f86-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92f86-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="92f86-117">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
