---
title: <clear><claimTypeRequirements>elementu
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: aa94a012da11bcec6fb5fe270ad9f3574f88e6d7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172908"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="c09e9-102">\<clear>\<claimTypeRequirements>elementu</span><span class="sxs-lookup"><span data-stu-id="c09e9-102">\<clear> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="c09e9-103">Określa, że wszystkie typy roszczeń mają być usunięte w poświadczeniu federacyjnym.</span><span class="sxs-lookup"><span data-stu-id="c09e9-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="c09e9-104">Dzięki temu zbieranie danych jest puste.</span><span class="sxs-lookup"><span data-stu-id="c09e9-104">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="c09e9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c09e9-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c09e9-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c09e9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c09e9-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c09e9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c09e9-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c09e9-108">Attributes</span></span>  

 <span data-ttu-id="c09e9-109">Brak.</span><span class="sxs-lookup"><span data-stu-id="c09e9-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c09e9-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c09e9-110">Child Elements</span></span>  

 <span data-ttu-id="c09e9-111">Brak.</span><span class="sxs-lookup"><span data-stu-id="c09e9-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c09e9-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c09e9-112">Parent Elements</span></span>  
  
|<span data-ttu-id="c09e9-113">Element</span><span class="sxs-lookup"><span data-stu-id="c09e9-113">Element</span></span>|<span data-ttu-id="c09e9-114">Opis</span><span class="sxs-lookup"><span data-stu-id="c09e9-114">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="c09e9-115">Określa kolekcję wymaganych typów roszczeń.</span><span class="sxs-lookup"><span data-stu-id="c09e9-115">Specifies a collection of required claim types.</span></span> <span data-ttu-id="c09e9-116">Każdy element jest typu <xref:System.ServiceModel.Configuration.ClaimTypeElement> .</span><span class="sxs-lookup"><span data-stu-id="c09e9-116">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="c09e9-117">W scenariuszu federacyjnym usługi określają wymagania dotyczące poświadczeń przychodzących.</span><span class="sxs-lookup"><span data-stu-id="c09e9-117">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="c09e9-118">Na przykład poświadczenia przychodzące muszą mieć określony zestaw typów roszczeń.</span><span class="sxs-lookup"><span data-stu-id="c09e9-118">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="c09e9-119">Każdy element w tej kolekcji określa typy wymaganych i opcjonalnych oświadczeń, które powinny być wyświetlane w federacyjnym poświadczeniu.</span><span class="sxs-lookup"><span data-stu-id="c09e9-119">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c09e9-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c09e9-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
