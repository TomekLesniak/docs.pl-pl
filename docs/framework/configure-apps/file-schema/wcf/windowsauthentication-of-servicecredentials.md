---
title: <windowsAuthentication> dla <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: bda375959b535ce5f2996d594f719893164b0bd4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195002"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="09992-102">\<windowsAuthentication> dla \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="09992-102">\<windowsAuthentication> of \<serviceCredentials></span></span>

<span data-ttu-id="09992-103">Określa ustawienia poświadczenia usługi systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="09992-103">Specifies the settings of a Windows service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="09992-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="09992-104">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09992-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="09992-105">Attributes and Elements</span></span>  

 <span data-ttu-id="09992-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="09992-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09992-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="09992-107">Attributes</span></span>  
  
|<span data-ttu-id="09992-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="09992-108">Attribute</span></span>|<span data-ttu-id="09992-109">Opis</span><span class="sxs-lookup"><span data-stu-id="09992-109">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="09992-110">Opcjonalny atrybut logiczny, który określa, czy system zawiera grupy systemu Windows w kontekście zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="09992-110">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="09992-111">Wartość domyślna to `true`.</span><span class="sxs-lookup"><span data-stu-id="09992-111">The default is `true`.</span></span><br /><br /> <span data-ttu-id="09992-112">Ustawienie tego atrybutu na `true` ma wpływ na wydajność, ponieważ skutkuje rozwinięciem całej grupy.</span><span class="sxs-lookup"><span data-stu-id="09992-112">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="09992-113">Ustaw ten atrybut na `false` , jeśli nie ma potrzeby ustanawiania listy grup, do których należy użytkownik.</span><span class="sxs-lookup"><span data-stu-id="09992-113">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="09992-114">Opcjonalny atrybut logiczny, który określa, czy są dozwolone anonimowe, nieuwierzytelnione wywoływania.</span><span class="sxs-lookup"><span data-stu-id="09992-114">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="09992-115">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="09992-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="09992-116">Gdy `clientCredentialType` atrybut powiązania jest ustawiony na `Windows` , system nie zezwala na anonimowe wywołania.</span><span class="sxs-lookup"><span data-stu-id="09992-116">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="09992-117">Oznacza to, że w celu uzyskania dostępu do systemu są dozwolone tylko uwierzytelnione wywołania domeny lub grupy roboczej.</span><span class="sxs-lookup"><span data-stu-id="09992-117">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="09992-118">To zachowanie można zastąpić za pomocą tego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="09992-118">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="09992-119">Użyj tego ustawienia z największą ostrożnością.</span><span class="sxs-lookup"><span data-stu-id="09992-119">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09992-120">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="09992-120">Child Elements</span></span>  

 <span data-ttu-id="09992-121">Brak.</span><span class="sxs-lookup"><span data-stu-id="09992-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09992-122">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="09992-122">Parent Elements</span></span>  
  
|<span data-ttu-id="09992-123">Element</span><span class="sxs-lookup"><span data-stu-id="09992-123">Element</span></span>|<span data-ttu-id="09992-124">Opis</span><span class="sxs-lookup"><span data-stu-id="09992-124">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="09992-125">Określa poświadczenie, które ma być używane w uwierzytelnianiu usługi i ustawień związanych z walidacją poświadczeń klienta.</span><span class="sxs-lookup"><span data-stu-id="09992-125">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09992-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="09992-126">Remarks</span></span>  

 <span data-ttu-id="09992-127">Użyj tego elementu, aby określić, czy zezwolić na dostęp anonimowym użytkownikom systemu Windows przez ustawienie `allowAnonymousLogons` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="09992-127">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="09992-128">Można również określić, czy mają zostać dołączone informacje o grupie, do których użytkownicy należą do AuthorizationContext przez ustawienie `includeWindowsGroups` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="09992-128">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="09992-129">Jeśli jest ustawiona na `true` (ustawienie domyślne), usługa może określić grupy systemu Windows, do których należy klient.</span><span class="sxs-lookup"><span data-stu-id="09992-129">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09992-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="09992-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
