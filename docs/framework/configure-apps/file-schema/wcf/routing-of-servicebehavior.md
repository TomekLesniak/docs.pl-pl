---
title: <routing> dla <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: cd53b720bad5752189f1c30d9e4acd3a66830396
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150885"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="d1c71-102">\<routing> dla \<serviceBehavior></span><span class="sxs-lookup"><span data-stu-id="d1c71-102">\<routing> of \<serviceBehavior></span></span>

<span data-ttu-id="d1c71-103">Zapewnia dostęp do usługi routingu w czasie wykonywania w celu umożliwienia dynamicznej modyfikacji konfiguracji routingu.</span><span class="sxs-lookup"><span data-stu-id="d1c71-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**  
  
## <a name="syntax"></a><span data-ttu-id="d1c71-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d1c71-104">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String"
               routeOnHeadersOnly="Boolean"
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1c71-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="d1c71-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d1c71-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="d1c71-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1c71-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="d1c71-107">Attributes</span></span>  
  
|<span data-ttu-id="d1c71-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="d1c71-108">Attribute</span></span>|<span data-ttu-id="d1c71-109">Opis</span><span class="sxs-lookup"><span data-stu-id="d1c71-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1c71-110">filterTable</span><span class="sxs-lookup"><span data-stu-id="d1c71-110">filterTable</span></span>|<span data-ttu-id="d1c71-111">Ciąg określający nazwę tabeli routingu zawierającej filtry, które mają być oceniane przez usługę routingu.</span><span class="sxs-lookup"><span data-stu-id="d1c71-111">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="d1c71-112">Ta wartość musi być zgodna z `name` atrybutem [\<filterTable>](filtertable.md) elementu w [\<filterTables>](filtertables.md) sekcji.</span><span class="sxs-lookup"><span data-stu-id="d1c71-112">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="d1c71-113">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="d1c71-113">routeOnHeaderOnly</span></span>|<span data-ttu-id="d1c71-114">Wartość logiczna określająca, czy filtr będzie przebadał zarówno treść komunikatu, jak i nagłówek, czy tylko nagłówek.</span><span class="sxs-lookup"><span data-stu-id="d1c71-114">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="d1c71-115">Wartość domyślna to `true`.</span><span class="sxs-lookup"><span data-stu-id="d1c71-115">The default is `true`.</span></span>|  
|<span data-ttu-id="d1c71-116">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="d1c71-116">soapProcessingEnabled</span></span>|<span data-ttu-id="d1c71-117">Wartość logiczna określająca, czy należy wykonać przetwarzanie protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="d1c71-117">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1c71-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="d1c71-118">Child Elements</span></span>  

 <span data-ttu-id="d1c71-119">Brak.</span><span class="sxs-lookup"><span data-stu-id="d1c71-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1c71-120">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="d1c71-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d1c71-121">Element</span><span class="sxs-lookup"><span data-stu-id="d1c71-121">Element</span></span>|<span data-ttu-id="d1c71-122">Opis</span><span class="sxs-lookup"><span data-stu-id="d1c71-122">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d1c71-123">Określa zachowanie elementu.</span><span class="sxs-lookup"><span data-stu-id="d1c71-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1c71-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d1c71-124">Remarks</span></span>  

 <span data-ttu-id="d1c71-125">Po dodaniu do konfiguracji zachowania usługi, ten element konfiguracji włącza Routing dla usługi.</span><span class="sxs-lookup"><span data-stu-id="d1c71-125">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="d1c71-126">Możesz określić rzeczywistą tabelę routingu, która ma być używana przez usługę w tym elemencie.</span><span class="sxs-lookup"><span data-stu-id="d1c71-126">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="d1c71-127">Za pomocą tej sekcji konfiguracji można zmienić ustawienia routingu na bieżąco po zmianie wzorca wdrożenia.</span><span class="sxs-lookup"><span data-stu-id="d1c71-127">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="d1c71-128">W czasie wykonywania można zarejestrować własne rozszerzenie routingu z nowymi ustawieniami routingu, a usługa routingu rozpocznie korzystanie z zaktualizowanych informacji o konfiguracji dla nowych komunikatów i sesji, pozostawiając jednocześnie komunikaty/sesje w locie przy użyciu dowolnych reguł podczas ich uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="d1c71-128">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="d1c71-129">Umożliwia to bezpieczne dla sesji ponowne odtwarzanie usługi routingu podczas środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="d1c71-129">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
