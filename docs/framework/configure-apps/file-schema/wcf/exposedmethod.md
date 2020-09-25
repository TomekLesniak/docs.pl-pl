---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 2947f0de6a88f39463e58a3b39bda52588fe4baa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203907"
---
# \<exposedMethod>

<span data-ttu-id="611d3-101">Reprezentuje metodę COM+, która jest uwidaczniana, gdy interfejs składnika modelu COM+ jest udostępniany jako usługa sieci Web.</span><span class="sxs-lookup"><span data-stu-id="611d3-101">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**  
  
## <a name="syntax"></a><span data-ttu-id="611d3-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="611d3-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="611d3-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="611d3-103">Attributes and Elements</span></span>  

 <span data-ttu-id="611d3-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="611d3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="611d3-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="611d3-105">Attributes</span></span>  
  
|<span data-ttu-id="611d3-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="611d3-106">Attribute</span></span>|<span data-ttu-id="611d3-107">Opis</span><span class="sxs-lookup"><span data-stu-id="611d3-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="611d3-108">name</span><span class="sxs-lookup"><span data-stu-id="611d3-108">name</span></span>|<span data-ttu-id="611d3-109">Ciąg, który zawiera metodę COM+, która jest uwidaczniana, gdy interfejs składnika modelu COM+ jest ujawniony jako usługa sieci Web.</span><span class="sxs-lookup"><span data-stu-id="611d3-109">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="611d3-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="611d3-110">Child Elements</span></span>  

 <span data-ttu-id="611d3-111">Brak.</span><span class="sxs-lookup"><span data-stu-id="611d3-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="611d3-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="611d3-112">Parent Elements</span></span>  
  
|<span data-ttu-id="611d3-113">Element</span><span class="sxs-lookup"><span data-stu-id="611d3-113">Element</span></span>|<span data-ttu-id="611d3-114">Opis</span><span class="sxs-lookup"><span data-stu-id="611d3-114">Description</span></span>|  
|-------------|-----------------|  
|[\<exposedMethods>](exposedmethods.md)|<span data-ttu-id="611d3-115">Kolekcja [\<exposedMethod>](exposedmethod.md) elementów.</span><span class="sxs-lookup"><span data-stu-id="611d3-115">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="611d3-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="611d3-116">Remarks</span></span>  

 <span data-ttu-id="611d3-117">Narzędzie konfiguracji integracji modelu COM+ (ComSvcConfig.exe) może służyć do dodawania określonych metod z interfejsu COM, które mają być wyświetlane w wygenerowanym kontrakcie usługi.</span><span class="sxs-lookup"><span data-stu-id="611d3-117">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="611d3-118">Na przykład można użyć poniższego polecenia, aby dodać trzy nazwane metody z `IFinances` interfejsu com na `ItemOrders` . Składnik finansowy do wygenerowanego kontraktu usługi.</span><span class="sxs-lookup"><span data-stu-id="611d3-118">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="611d3-119">Po uruchomieniu również ComSvcConfig.exe program generuje następujący kontrakt usługi z listą wymienionych wcześniej metod jako [\<exposedMethod>](exposedmethod.md) elementy.</span><span class="sxs-lookup"><span data-stu-id="611d3-119">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="611d3-120">W czasie inicjalizacji usługi środowisko uruchomieniowe próbuje wygenerować kontrakt usługi przez odzwierciedlenie i dodanie tylko metod uwzględnionych na liście [\<exposedMethod>](exposedmethod.md) elementów.</span><span class="sxs-lookup"><span data-stu-id="611d3-120">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="611d3-121">Ślad jest generowany dla każdej metody interfejsu, która nie jest uwzględniona w kontrakcie usługi.</span><span class="sxs-lookup"><span data-stu-id="611d3-121">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="611d3-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="611d3-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="611d3-123">Integrowanie z aplikacjami COM+</span><span class="sxs-lookup"><span data-stu-id="611d3-123">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="611d3-124">Instrukcje: konfigurowanie ustawień usługi COM+</span><span class="sxs-lookup"><span data-stu-id="611d3-124">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
