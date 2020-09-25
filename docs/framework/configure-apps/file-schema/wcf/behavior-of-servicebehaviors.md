---
title: <behavior> dla <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 739f95f527fd73062c8cec43efc6777efeb077f3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195158"
---
# <a name="behavior-of-servicebehaviors"></a><span data-ttu-id="97226-102">\<behavior> dla \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="97226-102">\<behavior> of \<serviceBehaviors></span></span>

<span data-ttu-id="97226-103">`behavior` Element zawiera zbiór ustawień dotyczących zachowania usługi.</span><span class="sxs-lookup"><span data-stu-id="97226-103">The `behavior` element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="97226-104">Każde działanie jest indeksowane według jego `name`.</span><span class="sxs-lookup"><span data-stu-id="97226-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="97226-105">Usługi mogą łączyć się z każdym zachowaniem za pomocą tej nazwy przy użyciu `behaviorConfiguration` atrybutu [\<endpoint>](endpoint-element.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="97226-105">Services can link to each behavior through this name using the `behaviorConfiguration` attribute of the [\<endpoint>](endpoint-element.md) element.</span></span> <span data-ttu-id="97226-106">Dzięki temu punktów końcowych udostępnić typowych konfiguracji zachowanie bez ponownego definiowania ustawień.</span><span class="sxs-lookup"><span data-stu-id="97226-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span> <span data-ttu-id="97226-107">Począwszy od .NET Framework 4, powiązania i zachowania nie muszą mieć nazwy.</span><span class="sxs-lookup"><span data-stu-id="97226-107">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="97226-108">Aby uzyskać więcej informacji na temat konfiguracji domyślnej i powiązań pustego i zachowań, zobacz [Uproszczona konfiguracja](../../../wcf/simplified-configuration.md) i [Uproszczona konfiguracja dla usług WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="97226-108">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97226-109">Elementy zachowań specyficzne dla działań przepływu pracy systemu Windows, takie jak [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) element, są udokumentowane [ \<behavior> \<serviceBehaviors> ](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) na stronie.</span><span class="sxs-lookup"><span data-stu-id="97226-109">Behavior elements specific to Windows Workflow activities, such as the [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) element, are documented in the [\<behavior> of \<serviceBehaviors>](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) page.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="97226-110">Składnia</span><span class="sxs-lookup"><span data-stu-id="97226-110">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97226-111">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="97226-111">Attributes and Elements</span></span>  

 <span data-ttu-id="97226-112">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="97226-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97226-113">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="97226-113">Attributes</span></span>  
  
|<span data-ttu-id="97226-114">Atrybut</span><span class="sxs-lookup"><span data-stu-id="97226-114">Attribute</span></span>|<span data-ttu-id="97226-115">Opis</span><span class="sxs-lookup"><span data-stu-id="97226-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97226-116">name</span><span class="sxs-lookup"><span data-stu-id="97226-116">name</span></span>|<span data-ttu-id="97226-117">Unikatowy ciąg, który zawiera nazwę konfiguracji zachowanie.</span><span class="sxs-lookup"><span data-stu-id="97226-117">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="97226-118">Ta wartość jest ciągiem zdefiniowanej przez użytkownika, który musi być unikatowy, ponieważ działa jako ciąg identyfikacyjny dla elementu.</span><span class="sxs-lookup"><span data-stu-id="97226-118">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="97226-119">Począwszy od .NET Framework 4, powiązania i zachowania nie muszą mieć nazwy.</span><span class="sxs-lookup"><span data-stu-id="97226-119">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="97226-120">Aby uzyskać więcej informacji na temat konfiguracji domyślnej i powiązań pustego i zachowań, zobacz [Uproszczona konfiguracja](../../../wcf/simplified-configuration.md) i [Uproszczona konfiguracja dla usług WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="97226-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97226-121">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="97226-121">Child Elements</span></span>  
  
|<span data-ttu-id="97226-122">Element</span><span class="sxs-lookup"><span data-stu-id="97226-122">Element</span></span>|<span data-ttu-id="97226-123">Opis</span><span class="sxs-lookup"><span data-stu-id="97226-123">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-element.md)|<span data-ttu-id="97226-124">Zawiera dane konfiguracyjne dla elementu DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="97226-124">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<persistenceProvider>](persistenceprovider.md)|<span data-ttu-id="97226-125">Określa typ implementacji dostawcy trwałości, a także limit czasu na potrzeby operacji trwałości.</span><span class="sxs-lookup"><span data-stu-id="97226-125">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>|  
|[\<routing>](routing-of-servicebehavior.md)|<span data-ttu-id="97226-126">Zapewnia dostęp do usługi routingu w czasie wykonywania w celu umożliwienia dynamicznej modyfikacji konfiguracji routingu.</span><span class="sxs-lookup"><span data-stu-id="97226-126">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|<span data-ttu-id="97226-127">Zawiera element konfiguracji przepływu pracy, który ustala na poziomie usługi ważność transmisji, wiadomości lub nadawcy.</span><span class="sxs-lookup"><span data-stu-id="97226-127">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|<span data-ttu-id="97226-128">Określa ustawienia, które zezwalają na dostęp do operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="97226-128">Specifies settings that authorize access to service operations.</span></span>|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="97226-129">Określa poświadczenie, które ma być używane w uwierzytelnianiu usługi i ustawień związanych z walidacją poświadczeń klienta.</span><span class="sxs-lookup"><span data-stu-id="97226-129">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>|  
|[\<serviceDebug>](servicedebug.md)|<span data-ttu-id="97226-130">Określa funkcje debugowania i pomocy dla usługi Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="97226-130">Specifies debugging and help information features for a Windows Communication Foundation (WCF) service.</span></span>|  
|[\<serviceDiscovery>](servicediscovery.md)|<span data-ttu-id="97226-131">Określa możliwość odnajdywania punktów końcowych usługi.</span><span class="sxs-lookup"><span data-stu-id="97226-131">Specifies the discoverability of service endpoints.</span></span>|  
|[\<serviceMetadata>](servicemetadata.md)|<span data-ttu-id="97226-132">Określa publikację metadanych usługi i skojarzonych z nią informacji.</span><span class="sxs-lookup"><span data-stu-id="97226-132">Specifies the publication of service metadata and associated information.</span></span>|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|<span data-ttu-id="97226-133">Określa ustawienia, które włączają inspekcję zdarzeń zabezpieczeń podczas operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="97226-133">Specifies settings that enable auditing of security events during service operations.</span></span>|  
|[\<serviceThrottling>](servicethrottling.md)|<span data-ttu-id="97226-134">Określa mechanizm ograniczania przepustowości usługi WCF.</span><span class="sxs-lookup"><span data-stu-id="97226-134">Specifies the throttling mechanism of a WCF service.</span></span>|  
|[\<serviceTimeouts>](servicetimeouts.md)|<span data-ttu-id="97226-135">Określa limit czasu dla usługi.</span><span class="sxs-lookup"><span data-stu-id="97226-135">Specifies the timeout for a service.</span></span>|  
|[\<workflowRuntime>](workflowruntime.md)|<span data-ttu-id="97226-136">Określa ustawienia dla wystąpienia elementu WorkflowRuntime do hostowania usług WCF opartych na przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="97226-136">Specifies settings for an instance of WorkflowRuntime for hosting workflow-based WCF services.</span></span>|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="97226-137">Umożliwia pobieranie informacji o adresie metadanych z nagłówków komunikatów żądania.</span><span class="sxs-lookup"><span data-stu-id="97226-137">Enables the retrieval of metadata address information from the request message headers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97226-138">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="97226-138">Parent Elements</span></span>  
  
|<span data-ttu-id="97226-139">Element</span><span class="sxs-lookup"><span data-stu-id="97226-139">Element</span></span>|<span data-ttu-id="97226-140">Opis</span><span class="sxs-lookup"><span data-stu-id="97226-140">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="97226-141">Kolekcja elementów zachowanie usługi.</span><span class="sxs-lookup"><span data-stu-id="97226-141">A collection of service behavior elements.</span></span>|
