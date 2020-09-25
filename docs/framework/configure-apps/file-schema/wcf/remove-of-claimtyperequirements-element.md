---
title: <remove><claimTypeRequirements>elementu
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 773f37156969f64f02711e6a60764aeb7e50a840
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181326"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="558a0-102">\<remove>\<claimTypeRequirements>elementu</span><span class="sxs-lookup"><span data-stu-id="558a0-102">\<remove> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="558a0-103">Określa typy oświadczeń do usunięcia w federacyjnym poświadczeniu.</span><span class="sxs-lookup"><span data-stu-id="558a0-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="558a0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="558a0-104">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="558a0-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="558a0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="558a0-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="558a0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="558a0-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="558a0-107">Attributes</span></span>  
  
|<span data-ttu-id="558a0-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="558a0-108">Attribute</span></span>|<span data-ttu-id="558a0-109">Opis</span><span class="sxs-lookup"><span data-stu-id="558a0-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="558a0-110">Claim</span><span class="sxs-lookup"><span data-stu-id="558a0-110">claimType</span></span>|<span data-ttu-id="558a0-111">Identyfikator URI, który definiuje typ żądania do usunięcia.</span><span class="sxs-lookup"><span data-stu-id="558a0-111">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="558a0-112">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="558a0-112">Child Elements</span></span>  

 <span data-ttu-id="558a0-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="558a0-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="558a0-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="558a0-114">Parent Elements</span></span>  
  
|<span data-ttu-id="558a0-115">Element</span><span class="sxs-lookup"><span data-stu-id="558a0-115">Element</span></span>|<span data-ttu-id="558a0-116">Opis</span><span class="sxs-lookup"><span data-stu-id="558a0-116">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="558a0-117">Określa kolekcję wymaganych typów roszczeń.</span><span class="sxs-lookup"><span data-stu-id="558a0-117">Specifies a collection of required claim types.</span></span> <span data-ttu-id="558a0-118">Każdy element jest typu <xref:System.ServiceModel.Configuration.ClaimTypeElement> .</span><span class="sxs-lookup"><span data-stu-id="558a0-118">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="558a0-119">W scenariuszu federacyjnym usługi określają wymagania dotyczące poświadczeń przychodzących.</span><span class="sxs-lookup"><span data-stu-id="558a0-119">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="558a0-120">Na przykład poświadczenia przychodzące muszą mieć określony zestaw typów roszczeń.</span><span class="sxs-lookup"><span data-stu-id="558a0-120">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="558a0-121">Każdy element w tej kolekcji określa typy wymaganych i opcjonalnych oświadczeń, które powinny być wyświetlane w federacyjnym poświadczeniu.</span><span class="sxs-lookup"><span data-stu-id="558a0-121">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="558a0-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="558a0-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
