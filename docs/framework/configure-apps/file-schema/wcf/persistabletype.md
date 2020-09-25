---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 6425b21fe50865beb7bb2876ea478b415fbe3944
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181521"
---
# \<persistableType>

<span data-ttu-id="e8af6-101">Określa wszystkie typy, które są trwałe.</span><span class="sxs-lookup"><span data-stu-id="e8af6-101">Specifies all the persistable types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**  
  
## <a name="syntax"></a><span data-ttu-id="e8af6-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="e8af6-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="e8af6-103">Typ</span><span class="sxs-lookup"><span data-stu-id="e8af6-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8af6-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e8af6-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e8af6-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e8af6-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8af6-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e8af6-106">Attributes</span></span>  
  
|<span data-ttu-id="e8af6-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="e8af6-107">Attribute</span></span>|<span data-ttu-id="e8af6-108">Opis</span><span class="sxs-lookup"><span data-stu-id="e8af6-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8af6-109">identyfikator</span><span class="sxs-lookup"><span data-stu-id="e8af6-109">id</span></span>|<span data-ttu-id="e8af6-110">Wymagany atrybut, który zawiera ciąg, który określa unikatowy identyfikator dla typu trwałego.</span><span class="sxs-lookup"><span data-stu-id="e8af6-110">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="e8af6-111">name</span><span class="sxs-lookup"><span data-stu-id="e8af6-111">name</span></span>|<span data-ttu-id="e8af6-112">Opcjonalny atrybut, który zawiera ciąg określający nazwę typu, który jest trwały.</span><span class="sxs-lookup"><span data-stu-id="e8af6-112">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8af6-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e8af6-113">Child Elements</span></span>  

 <span data-ttu-id="e8af6-114">Brak</span><span class="sxs-lookup"><span data-stu-id="e8af6-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8af6-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e8af6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e8af6-116">Element</span><span class="sxs-lookup"><span data-stu-id="e8af6-116">Element</span></span>|<span data-ttu-id="e8af6-117">Opis</span><span class="sxs-lookup"><span data-stu-id="e8af6-117">Description</span></span>|  
|-------------|-----------------|  
|[\<persistableTypes>](persistabletypes.md)|<span data-ttu-id="e8af6-118">Kolekcja `persistableType` elementów.</span><span class="sxs-lookup"><span data-stu-id="e8af6-118">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8af6-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e8af6-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="e8af6-120">Integrowanie z aplikacjami COM+</span><span class="sxs-lookup"><span data-stu-id="e8af6-120">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="e8af6-121">Instrukcje: konfigurowanie ustawień usługi COM+</span><span class="sxs-lookup"><span data-stu-id="e8af6-121">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
