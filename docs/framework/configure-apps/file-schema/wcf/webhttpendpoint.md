---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 3282871bf8dbd25726ada7003d3066b9a42e2366
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177985"
---
# \<webHttpEndpoint>

<span data-ttu-id="4f4b1-101">Ten element konfiguracji definiuje standardowy punkt końcowy ze stałym [\<webHttpBinding>](webhttpbinding.md) powiązaniem, które automatycznie dodaje [\<webHttp>](webhttp.md) zachowanie.</span><span class="sxs-lookup"><span data-stu-id="4f4b1-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="4f4b1-102">Użyj tego punktu końcowego podczas pisania usługi REST.</span><span class="sxs-lookup"><span data-stu-id="4f4b1-102">Use this endpoint when writing a REST service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="4f4b1-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="4f4b1-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f4b1-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="4f4b1-104">Attributes and Elements</span></span>  

 <span data-ttu-id="4f4b1-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="4f4b1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f4b1-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="4f4b1-106">Attributes</span></span>  
  
|<span data-ttu-id="4f4b1-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="4f4b1-107">Attribute</span></span>|<span data-ttu-id="4f4b1-108">Opis</span><span class="sxs-lookup"><span data-stu-id="4f4b1-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f4b1-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="4f4b1-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="4f4b1-110">Wartość logiczna wskazująca, czy jest włączone automatyczne Wybieranie formatu.</span><span class="sxs-lookup"><span data-stu-id="4f4b1-110">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="4f4b1-111">Po włączeniu automatycznego wybierania formatu infrastruktura analizuje `Accept` nagłówek komunikatu żądania i określa najbardziej odpowiedni format odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="4f4b1-111">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="4f4b1-112">Jeśli w `Accept` nagłówku nie określono odpowiedniego formatu odpowiedzi, infrastruktura używa `Content-Type` komunikatu żądania lub domyślnego formatu odpowiedzi operacji.</span><span class="sxs-lookup"><span data-stu-id="4f4b1-112">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="4f4b1-113">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="4f4b1-113">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="4f4b1-114">Atrybut, który określa domyślny format odpowiedzi wychodzącej.</span><span class="sxs-lookup"><span data-stu-id="4f4b1-114">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="4f4b1-115">Ten atrybut jest <xref:System.ServiceModel.Web.WebMessageFormat> typu</span><span class="sxs-lookup"><span data-stu-id="4f4b1-115">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="4f4b1-116">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="4f4b1-116">helpEnabled</span></span>|<span data-ttu-id="4f4b1-117">Wartość logiczna wskazująca, czy strona pomocy protokołu HTTP jest włączona dla punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="4f4b1-117">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="4f4b1-118">WebEndpointType</span><span class="sxs-lookup"><span data-stu-id="4f4b1-118">webEndpointType</span></span>|<span data-ttu-id="4f4b1-119">Ciąg określający typ punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="4f4b1-119">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f4b1-120">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="4f4b1-120">Child Elements</span></span>  

 <span data-ttu-id="4f4b1-121">Brak.</span><span class="sxs-lookup"><span data-stu-id="4f4b1-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f4b1-122">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="4f4b1-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4f4b1-123">Element</span><span class="sxs-lookup"><span data-stu-id="4f4b1-123">Element</span></span>|<span data-ttu-id="4f4b1-124">Opis</span><span class="sxs-lookup"><span data-stu-id="4f4b1-124">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="4f4b1-125">Kolekcja standardowych punktów końcowych, które są wstępnie zdefiniowanymi punktami końcowymi z co najmniej jedną z jej właściwości (adres, powiązanie, kontrakt).</span><span class="sxs-lookup"><span data-stu-id="4f4b1-125">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f4b1-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4f4b1-126">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
