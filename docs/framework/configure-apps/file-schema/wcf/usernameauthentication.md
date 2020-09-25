---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 30fd78d6c56e8b22e0e744a38f18ac076dc70162
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178037"
---
# \<userNameAuthentication>

<span data-ttu-id="d438c-101">Określa poświadczenia usługi na podstawie nazwy użytkownika i hasła.</span><span class="sxs-lookup"><span data-stu-id="d438c-101">Specifies a service's credentials based on user name and password.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="d438c-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="d438c-102">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d438c-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="d438c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="d438c-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="d438c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d438c-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="d438c-105">Attributes</span></span>  
  
|<span data-ttu-id="d438c-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="d438c-106">Attribute</span></span>|<span data-ttu-id="d438c-107">Opis</span><span class="sxs-lookup"><span data-stu-id="d438c-107">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="d438c-108">A <xref:System.TimeSpan> , która określa maksymalny czas buforowania tokenu.</span><span class="sxs-lookup"><span data-stu-id="d438c-108">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="d438c-109">Wartość domyślna to 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="d438c-109">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="d438c-110">Wartość logiczna określająca, czy tokeny logowania są buforowane.</span><span class="sxs-lookup"><span data-stu-id="d438c-110">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="d438c-111">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="d438c-111">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="d438c-112">Ciąg określający typ niestandardowego modułu weryfikacji hasła użytkownika, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="d438c-112">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="d438c-113">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="d438c-113">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="d438c-114">Wartość logiczna określająca, czy grupy systemu Windows znajdują się w kontekście zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="d438c-114">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="d438c-115">Wartość domyślna to `true`.</span><span class="sxs-lookup"><span data-stu-id="d438c-115">The default is `true`.</span></span><br /><br /> <span data-ttu-id="d438c-116">Ustawienie tego atrybutu na `true` ma wpływ na wydajność, ponieważ skutkuje rozwinięciem całej grupy.</span><span class="sxs-lookup"><span data-stu-id="d438c-116">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="d438c-117">Ustaw tę właściwość na, `false` Jeśli nie ma potrzeby ustanawiania listy grup, do których należy użytkownik.</span><span class="sxs-lookup"><span data-stu-id="d438c-117">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="d438c-118">Liczba całkowita określająca maksymalną liczbę tokenów logowania do buforowania.</span><span class="sxs-lookup"><span data-stu-id="d438c-118">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="d438c-119">Ta wartość powinna być większa niż zero.</span><span class="sxs-lookup"><span data-stu-id="d438c-119">This value should be larger than zero.</span></span> <span data-ttu-id="d438c-120">Wartość domyślna to 128.</span><span class="sxs-lookup"><span data-stu-id="d438c-120">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="d438c-121">Gdy `clientCredentialType` atrybut powiązania jest ustawiony na `username` , nazwa użytkownika jest mapowana na konta systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="d438c-121">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="d438c-122">Można przesłonić to zachowanie przy użyciu tego atrybutu, który jest ciągiem zawierającym nazwę <xref:System.Web.Security.MembershipProvider> wartości, która zapewnia odpowiedni mechanizm walidacji hasła.</span><span class="sxs-lookup"><span data-stu-id="d438c-122">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="d438c-123">Określa sposób sprawdzania poprawności hasła nazwy użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d438c-123">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="d438c-124">Prawidłowe wartości:</span><span class="sxs-lookup"><span data-stu-id="d438c-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="d438c-125">— System Windows</span><span class="sxs-lookup"><span data-stu-id="d438c-125">-   Windows</span></span><br /><span data-ttu-id="d438c-126">- MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="d438c-126">-   MembershipProvider</span></span><br /><span data-ttu-id="d438c-127">-Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d438c-127">-   Custom</span></span><br /><br /> <span data-ttu-id="d438c-128">Wartość domyślna to Windows.</span><span class="sxs-lookup"><span data-stu-id="d438c-128">The default is Windows.</span></span> <span data-ttu-id="d438c-129">Ten atrybut jest typu <xref:System.ServiceModel.Security.UserNamePasswordValidationMode> .</span><span class="sxs-lookup"><span data-stu-id="d438c-129">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d438c-130">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="d438c-130">Child Elements</span></span>  

 <span data-ttu-id="d438c-131">Brak.</span><span class="sxs-lookup"><span data-stu-id="d438c-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d438c-132">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="d438c-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d438c-133">Element</span><span class="sxs-lookup"><span data-stu-id="d438c-133">Element</span></span>|<span data-ttu-id="d438c-134">Opis</span><span class="sxs-lookup"><span data-stu-id="d438c-134">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="d438c-135">Określa poświadczenie, które ma być używane w uwierzytelnianiu usługi oraz ustawienia powiązane z walidacją poświadczeń klienta.</span><span class="sxs-lookup"><span data-stu-id="d438c-135">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d438c-136">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d438c-136">Remarks</span></span>  

 <span data-ttu-id="d438c-137">Jeśli żaden z powiązań używanych przez usługę nie jest skonfigurowany do uwierzytelniania opartego na nazwie użytkownika/hasła, atrybuty tego elementu są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="d438c-137">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="d438c-138">Należą `customUserNamePasswordValidatorType` do nich, `includeWindowsGroups` , `membershipProviderName` , i `userNamePasswordValidationMode` .</span><span class="sxs-lookup"><span data-stu-id="d438c-138">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="d438c-139">Jeśli żaden z powiązań używanych przez usługę nie jest skonfigurowany do korzystania z uwierzytelniania systemu Windows dla nazwy użytkownika/hasła, ustawienia związane z buforowaniem tokenów logowania są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="d438c-139">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="d438c-140">Należą do nich `cacheLogonTokenLifetime` , `cacheLogonTokens` i `maxCacheLogonTokens` .</span><span class="sxs-lookup"><span data-stu-id="d438c-140">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d438c-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d438c-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
