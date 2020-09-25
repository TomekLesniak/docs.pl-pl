---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 347a08a35ff898ab7037c11d3c87fda73c3ab2ab
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178104"
---
# \<headers>

<span data-ttu-id="65143-101">Punkt końcowy może być rozkierowany przy użyciu co najmniej jednego nagłówka SOAP oprócz podstawowego identyfikatora URI.</span><span class="sxs-lookup"><span data-stu-id="65143-101">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="65143-102">Jednym z zestawów scenariuszy, w których jest to przydatne, jest zestaw scenariuszy pośrednich protokołu SOAP, w których punkt końcowy wymaga od klientów tego punktu końcowego dołączenia nagłówków protokołu SOAP przeznaczonych dla pośredników.</span><span class="sxs-lookup"><span data-stu-id="65143-102">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="65143-103">Ten element konfiguracji może służyć do definiowania takich niestandardowych nagłówków adresów.</span><span class="sxs-lookup"><span data-stu-id="65143-103">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="65143-104">Wpisy w kolekcji nagłówka punktu końcowego są elementami XML zdefiniowanymi przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="65143-104">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="65143-105">Każdy element musi być poprawnie sformułowanym plikiem XML.</span><span class="sxs-lookup"><span data-stu-id="65143-105">Each element has to be well-formed XML.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**  
  
## <a name="syntax"></a><span data-ttu-id="65143-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="65143-106">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65143-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="65143-107">Attributes and Elements</span></span>  

 <span data-ttu-id="65143-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="65143-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65143-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="65143-109">Attributes</span></span>  

 <span data-ttu-id="65143-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="65143-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="65143-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="65143-111">Child Elements</span></span>  

 <span data-ttu-id="65143-112">Zdefiniowane przez użytkownika elementy XML.</span><span class="sxs-lookup"><span data-stu-id="65143-112">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65143-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="65143-113">Parent Elements</span></span>  
  
|<span data-ttu-id="65143-114">Element</span><span class="sxs-lookup"><span data-stu-id="65143-114">Element</span></span>|<span data-ttu-id="65143-115">Opis</span><span class="sxs-lookup"><span data-stu-id="65143-115">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="65143-116">Konfiguruje różne typy punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="65143-116">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65143-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="65143-117">Remarks</span></span>  

 <span data-ttu-id="65143-118">Opcjonalne nagłówki zawierają bardziej szczegółowe informacje dotyczące adresowania, które identyfikują lub współpracują z punktem końcowym.</span><span class="sxs-lookup"><span data-stu-id="65143-118">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="65143-119">Na przykład nagłówki mogą wskazywać, jak przetwarzać komunikat przychodzący, gdzie punkt końcowy powinien wysłać komunikat odpowiedzi lub którego wystąpienia usługi należy użyć do przetworzenia komunikatu przychodzącego od określonego użytkownika, gdy jest dostępnych wiele wystąpień.</span><span class="sxs-lookup"><span data-stu-id="65143-119">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65143-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="65143-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="65143-121">Punkty końcowe: adresy, wiązania i kontrakty</span><span class="sxs-lookup"><span data-stu-id="65143-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
