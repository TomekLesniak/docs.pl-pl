---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: a4bbd677aba27d93389f8d2f99aadd801c86b65f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172843"
---
# \<userDefinedType>

<span data-ttu-id="e0ed8-101">Reprezentuje typ zdefiniowany przez użytkownika (UDT), który ma zostać uwzględniony w kontrakcie usługi.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-101">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<userDefinedTypes>**](userdefinedtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userDefinedType>**  
  
## <a name="syntax"></a><span data-ttu-id="e0ed8-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="e0ed8-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0ed8-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e0ed8-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e0ed8-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0ed8-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e0ed8-105">Attributes</span></span>  
  
|<span data-ttu-id="e0ed8-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="e0ed8-106">Attribute</span></span>|<span data-ttu-id="e0ed8-107">Opis</span><span class="sxs-lookup"><span data-stu-id="e0ed8-107">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="e0ed8-108">Opcjonalny atrybut, który zawiera ciąg, który zawiera nazwę typu, który można odczytać.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-108">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="e0ed8-109">Nie jest on używany przez środowisko uruchomieniowe, ale pomaga czytelnikowi odróżnić typy.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-109">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="e0ed8-110">Ciąg identyfikatora GUID, który identyfikuje określony typ UDT w zarejestrowanej bibliotece typów.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-110">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="e0ed8-111">Ciąg identyfikatora GUID, który identyfikuje zarejestrowanej biblioteki typów, która definiuje typ.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-111">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="e0ed8-112">Ciąg, który identyfikuje wersję biblioteki typów, która definiuje typ.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-112">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0ed8-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e0ed8-113">Child Elements</span></span>  

 <span data-ttu-id="e0ed8-114">Brak.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0ed8-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e0ed8-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e0ed8-116">Element</span><span class="sxs-lookup"><span data-stu-id="e0ed8-116">Element</span></span>|<span data-ttu-id="e0ed8-117">Opis</span><span class="sxs-lookup"><span data-stu-id="e0ed8-117">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="e0ed8-118">Kolekcja `userDefinedType` elementów.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-118">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0ed8-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e0ed8-119">Remarks</span></span>  

 <span data-ttu-id="e0ed8-120">Środowisko Integration Runtime środowiska COM+ tworzy usługi, sprawdzając bibliotekę typów.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-120">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="e0ed8-121">Gdy składnik COM+ zawiera metody, które przechodzą wariant, system nie może ustalić rzeczywistych typów do przekazania przed środowiskiem uruchomieniowym.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-121">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="e0ed8-122">W związku z tym podczas próby przekazania typu zdefiniowanego przez użytkownika (UDT) w ramach WARIANTu nie powiedzie się, ponieważ nie jest to znany typ serializacji.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-122">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="e0ed8-123">Aby obejść ten problem, można dodać UDTs do pliku konfiguracji, aby można je było uwzględnić jako znane typy w odpowiednim kontrakcie usługi.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-123">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="e0ed8-124">Aby to zrobić, należy jednoznacznie zidentyfikować UDT i kontrakty, czyli oryginalne interfejsy COM, które z niego korzystają.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-124">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="e0ed8-125">Poniższy przykład ilustruje dodanie dwóch konkretnych UDTs do `userDefinedTypes` sekcji> <w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-125">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <userDefinedTypes>
      <userDefinedType name="CustomerType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">
      </userDefinedType>
      <userDefinedType name="AddressType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">
      </userDefinedType>
    </userDefinedTypes>
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="e0ed8-126">Po zainicjowaniu usługi środowisko Integration Runtime wyszukuje określone typy i dodaje je do kolekcji znanych typów dla określonych kontraktów.</span><span class="sxs-lookup"><span data-stu-id="e0ed8-126">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ed8-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e0ed8-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="e0ed8-128">Integrowanie z aplikacjami COM+</span><span class="sxs-lookup"><span data-stu-id="e0ed8-128">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="e0ed8-129">Instrukcje: konfigurowanie ustawień usługi COM+</span><span class="sxs-lookup"><span data-stu-id="e0ed8-129">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
