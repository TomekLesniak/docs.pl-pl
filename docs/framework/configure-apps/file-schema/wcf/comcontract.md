---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 35596f32bf0e0de9081bc0d4c33fb370c7ab708b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173786"
---
# \<comContract>

<span data-ttu-id="f0a85-101">Określa kontrakt usługi integracji COM+.</span><span class="sxs-lookup"><span data-stu-id="f0a85-101">Specifies a COM+ integration service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a><span data-ttu-id="f0a85-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="f0a85-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0a85-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="f0a85-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f0a85-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="f0a85-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0a85-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="f0a85-105">Attributes</span></span>  
  
|<span data-ttu-id="f0a85-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="f0a85-106">Attribute</span></span>|<span data-ttu-id="f0a85-107">Opis</span><span class="sxs-lookup"><span data-stu-id="f0a85-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0a85-108">przedsiębiorc</span><span class="sxs-lookup"><span data-stu-id="f0a85-108">contract</span></span>|<span data-ttu-id="f0a85-109">Ciąg, który zawiera typ kontraktu.</span><span class="sxs-lookup"><span data-stu-id="f0a85-109">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="f0a85-110">name</span><span class="sxs-lookup"><span data-stu-id="f0a85-110">name</span></span>|<span data-ttu-id="f0a85-111">Ciąg, który zawiera nazwę kontraktu.</span><span class="sxs-lookup"><span data-stu-id="f0a85-111">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="f0a85-112">namespace</span><span class="sxs-lookup"><span data-stu-id="f0a85-112">namespace</span></span>|<span data-ttu-id="f0a85-113">Ciąg, który zawiera przestrzeń nazw kontraktu.</span><span class="sxs-lookup"><span data-stu-id="f0a85-113">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="f0a85-114">requiresSession</span><span class="sxs-lookup"><span data-stu-id="f0a85-114">requiresSession</span></span>|<span data-ttu-id="f0a85-115">Wartość logiczna określająca, czy kontrakt może być używany tylko na powiązaniach sesji.</span><span class="sxs-lookup"><span data-stu-id="f0a85-115">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="f0a85-116">Po zainicjowaniu usługi środowisko Integration Runtime zapewnia spójność tego ustawienia z typem powiązania, które ma być używane.</span><span class="sxs-lookup"><span data-stu-id="f0a85-116">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="f0a85-117">Wyjątek jest generowany, jeśli co najmniej jedno powiązanie kontraktu jest w konflikcie.</span><span class="sxs-lookup"><span data-stu-id="f0a85-117">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="f0a85-118">Jeśli ta właściwość ma wartość `false` , a kanał jednokierunkowy jest używany i istnieją wszystkie parametry [out], generowany jest również wyjątek.</span><span class="sxs-lookup"><span data-stu-id="f0a85-118">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0a85-119">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="f0a85-119">Child Elements</span></span>  
  
|<span data-ttu-id="f0a85-120">Element</span><span class="sxs-lookup"><span data-stu-id="f0a85-120">Element</span></span>|<span data-ttu-id="f0a85-121">Opis</span><span class="sxs-lookup"><span data-stu-id="f0a85-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0a85-122">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="f0a85-122">persistableTypes</span></span>|<span data-ttu-id="f0a85-123">Wszystkie typy, które są trwałe.</span><span class="sxs-lookup"><span data-stu-id="f0a85-123">All the persistable types.</span></span>|  
|<span data-ttu-id="f0a85-124">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="f0a85-124">userDefinedTypes</span></span>|<span data-ttu-id="f0a85-125">Kolekcja typów zdefiniowanych przez użytkownika (UDT), które mają zostać uwzględnione w kontrakcie usługi.</span><span class="sxs-lookup"><span data-stu-id="f0a85-125">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="f0a85-126">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="f0a85-126">exposedMethods</span></span>|<span data-ttu-id="f0a85-127">Kolekcja metod modelu COM+, które są dostępne, gdy interfejs składnika modelu COM+ jest udostępniany jako usługa sieci Web.</span><span class="sxs-lookup"><span data-stu-id="f0a85-127">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0a85-128">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="f0a85-128">Parent Elements</span></span>  
  
|<span data-ttu-id="f0a85-129">Element</span><span class="sxs-lookup"><span data-stu-id="f0a85-129">Element</span></span>|<span data-ttu-id="f0a85-130">Opis</span><span class="sxs-lookup"><span data-stu-id="f0a85-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0a85-131">comContracts</span><span class="sxs-lookup"><span data-stu-id="f0a85-131">comContracts</span></span>|<span data-ttu-id="f0a85-132">Zawiera kolekcję `comContract` elementów.</span><span class="sxs-lookup"><span data-stu-id="f0a85-132">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0a85-133">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f0a85-133">Remarks</span></span>  

 <span data-ttu-id="f0a85-134">Kontrakty usługi integracji modelu COM+ są obecnie ograniczone do `http://tempuri.org` przestrzeni nazw, a nazwa kontraktu pochodzi od pomocniczego interfejsu com.</span><span class="sxs-lookup"><span data-stu-id="f0a85-134">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="f0a85-135">Można jednak określić alternatywy przy użyciu `comContracts` sekcji, a także `comContract` elementu w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="f0a85-135">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="f0a85-136">Można na przykład użyć poniższej konfiguracji, aby określić przestrzeń nazw, nazwę kontraktu i typy zdefiniowane przez użytkownika, a także inne ustawienia dla kontraktu usługi.</span><span class="sxs-lookup"><span data-stu-id="f0a85-136">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="f0a85-137">Po zainicjowaniu usługi określone nazwy obszarów nazw i kontraktów są stosowane do opisów wygenerowanych usług.</span><span class="sxs-lookup"><span data-stu-id="f0a85-137">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a85-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f0a85-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="f0a85-139">Integrowanie z aplikacjami COM+</span><span class="sxs-lookup"><span data-stu-id="f0a85-139">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="f0a85-140">Instrukcje: konfigurowanie ustawień usługi COM+</span><span class="sxs-lookup"><span data-stu-id="f0a85-140">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
