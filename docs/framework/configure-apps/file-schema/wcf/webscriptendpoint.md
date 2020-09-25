---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 5e3ca9c4a43432d7f5da6d8816b6a2b984851050
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177844"
---
# \<webScriptEndpoint>

<span data-ttu-id="38e4e-101">Ten element konfiguracji definiuje standardowy punkt końcowy ze stałym [\<webHttpBinding>](webhttpbinding.md) powiązaniem, które automatycznie dodaje [\<enableWebScript>](enablewebscript.md) zachowanie.</span><span class="sxs-lookup"><span data-stu-id="38e4e-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="38e4e-102">Użyj tego punktu końcowego podczas pisania usługi, która jest wywoływana z aplikacji ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="38e4e-102">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="38e4e-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="38e4e-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38e4e-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="38e4e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="38e4e-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="38e4e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38e4e-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="38e4e-106">Attributes</span></span>  
  
|<span data-ttu-id="38e4e-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="38e4e-107">Attribute</span></span>|<span data-ttu-id="38e4e-108">Opis</span><span class="sxs-lookup"><span data-stu-id="38e4e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38e4e-109">WebEndpointType</span><span class="sxs-lookup"><span data-stu-id="38e4e-109">webEndpointType</span></span>|<span data-ttu-id="38e4e-110">Ciąg określający typ punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="38e4e-110">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38e4e-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="38e4e-111">Child Elements</span></span>  

 <span data-ttu-id="38e4e-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="38e4e-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38e4e-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="38e4e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="38e4e-114">Element</span><span class="sxs-lookup"><span data-stu-id="38e4e-114">Element</span></span>|<span data-ttu-id="38e4e-115">Opis</span><span class="sxs-lookup"><span data-stu-id="38e4e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="38e4e-116">Kolekcja standardowych punktów końcowych, które są wstępnie zdefiniowanymi punktami końcowymi z co najmniej jedną z jej właściwości (adres, powiązanie, kontrakt).</span><span class="sxs-lookup"><span data-stu-id="38e4e-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38e4e-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="38e4e-117">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
