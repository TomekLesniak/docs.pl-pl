---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: a5209efddd489f8cb04b3266e6ba0bb033eeae6c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176022"
---
# \<compositeDuplex>

<span data-ttu-id="0efed-101">Definiuje element powiązania, który jest używany, gdy klient musi uwidocznić punkt końcowy dla usługi w celu wysłania komunikatów z powrotem do klienta.</span><span class="sxs-lookup"><span data-stu-id="0efed-101">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a><span data-ttu-id="0efed-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="0efed-102">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0efed-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="0efed-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0efed-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="0efed-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0efed-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="0efed-105">Attributes</span></span>  
  
|<span data-ttu-id="0efed-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="0efed-106">Attribute</span></span>|<span data-ttu-id="0efed-107">Opis</span><span class="sxs-lookup"><span data-stu-id="0efed-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0efed-108">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="0efed-108">clientBaseAddress</span></span>|<span data-ttu-id="0efed-109">Identyfikator URI, który ustawia adres kanału zwrotnego w trybie dupleksu.</span><span class="sxs-lookup"><span data-stu-id="0efed-109">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="0efed-110">Usługa używa tego adresu do nawiązywania kontaktu i nawiązania połączenia z klientem.</span><span class="sxs-lookup"><span data-stu-id="0efed-110">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="0efed-111">Jeśli ten atrybut nie jest ustawiony, zostanie wygenerowany domyślny adres " `full qualified name+default port\TemporaryIndigoAddress\guid` ".</span><span class="sxs-lookup"><span data-stu-id="0efed-111">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="0efed-112">Wartość domyślna to `null`.</span><span class="sxs-lookup"><span data-stu-id="0efed-112">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0efed-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="0efed-113">Child Elements</span></span>  

 <span data-ttu-id="0efed-114">Brak</span><span class="sxs-lookup"><span data-stu-id="0efed-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0efed-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="0efed-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0efed-116">Element</span><span class="sxs-lookup"><span data-stu-id="0efed-116">Element</span></span>|<span data-ttu-id="0efed-117">Opis</span><span class="sxs-lookup"><span data-stu-id="0efed-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0efed-118">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="0efed-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0efed-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0efed-119">Remarks</span></span>  

 <span data-ttu-id="0efed-120">Ten element konfiguracji jest używany z transportami, które nie zezwalają na natywną komunikację bezstronną, na przykład HTTP.</span><span class="sxs-lookup"><span data-stu-id="0efed-120">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="0efed-121">Protokół TCP, w przeciwieństwie, umożliwia natywną komunikację bezstronną i nie wymaga użycia tego elementu powiązania dla usługi do wysyłania komunikatów z powrotem do klienta.</span><span class="sxs-lookup"><span data-stu-id="0efed-121">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="0efed-122">Klient musi uwidocznić adres usługi, aby nawiązać kontakt i nawiązać połączenie.</span><span class="sxs-lookup"><span data-stu-id="0efed-122">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="0efed-123">Ten adres klienta jest dostarczany przez `clientBaseAddress` atrybut.</span><span class="sxs-lookup"><span data-stu-id="0efed-123">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="0efed-124">Należy pamiętać, że Windows Communication Foundation (WCF) automatycznie generuje element ClientBaseAddress, jeśli nie został jawnie ustawiony przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0efed-124">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0efed-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="0efed-125">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="0efed-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0efed-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0efed-127">Powiązania</span><span class="sxs-lookup"><span data-stu-id="0efed-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0efed-128">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="0efed-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0efed-129">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="0efed-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
