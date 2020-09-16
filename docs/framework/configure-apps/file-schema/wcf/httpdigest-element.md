---
title: <httpDigest> Element
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 0ffaba218d31a77407c598f8b7fa0260daa4e39c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556905"
---
# <a name="httpdigest-element"></a><span data-ttu-id="8dec2-102">\<httpDigest> Element</span><span class="sxs-lookup"><span data-stu-id="8dec2-102">\<httpDigest> Element</span></span>
<span data-ttu-id="8dec2-103">Określa poświadczenia typu szyfrowanego używane podczas uwierzytelniania klienta w usłudze.</span><span class="sxs-lookup"><span data-stu-id="8dec2-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**  
  
## <a name="syntax"></a><span data-ttu-id="8dec2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8dec2-104">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8dec2-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="8dec2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8dec2-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="8dec2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8dec2-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="8dec2-107">Attributes</span></span>  
  
|<span data-ttu-id="8dec2-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="8dec2-108">Attribute</span></span>|<span data-ttu-id="8dec2-109">Opis</span><span class="sxs-lookup"><span data-stu-id="8dec2-109">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="8dec2-110">Ustawia preferencje personifikacji, które klient komunikuje się z serwerem.</span><span class="sxs-lookup"><span data-stu-id="8dec2-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="8dec2-111">Tryb personifikacji wybierany przez klienta nie jest wymuszany na serwerze.</span><span class="sxs-lookup"><span data-stu-id="8dec2-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="8dec2-112">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="8dec2-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8dec2-113">-Identyfikacja: serwer może uzyskać tożsamość i uprawnienia klienta, ale nie może personifikować klienta.</span><span class="sxs-lookup"><span data-stu-id="8dec2-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="8dec2-114">-Personifikacja: serwer może personifikować kontekst zabezpieczeń klienta w systemie lokalnym.</span><span class="sxs-lookup"><span data-stu-id="8dec2-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="8dec2-115">-Delegowanie: serwer może personifikować kontekst zabezpieczeń klienta w systemach zdalnych.</span><span class="sxs-lookup"><span data-stu-id="8dec2-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="8dec2-116">-Anonymous: serwer nie może personifikować lub zidentyfikować klienta.</span><span class="sxs-lookup"><span data-stu-id="8dec2-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="8dec2-117">-Brak: nie przypisano poziomu personifikacji.</span><span class="sxs-lookup"><span data-stu-id="8dec2-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="8dec2-118">Wartość domyślna to Identification.</span><span class="sxs-lookup"><span data-stu-id="8dec2-118">The default is Identification.</span></span> <span data-ttu-id="8dec2-119">Ten atrybut jest typu <xref:System.Security.Principal.TokenImpersonationLevel> .</span><span class="sxs-lookup"><span data-stu-id="8dec2-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8dec2-120">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="8dec2-120">Child Elements</span></span>  
 <span data-ttu-id="8dec2-121">Brak</span><span class="sxs-lookup"><span data-stu-id="8dec2-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8dec2-122">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="8dec2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8dec2-123">Element</span><span class="sxs-lookup"><span data-stu-id="8dec2-123">Element</span></span>|<span data-ttu-id="8dec2-124">Opis</span><span class="sxs-lookup"><span data-stu-id="8dec2-124">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="8dec2-125">Określa poświadczenia używane do uwierzytelniania klienta w usłudze.</span><span class="sxs-lookup"><span data-stu-id="8dec2-125">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8dec2-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8dec2-126">Remarks</span></span>  
 <span data-ttu-id="8dec2-127">Skrót jest skrótem określonym przy użyciu algorytmu i zestawu danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="8dec2-127">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="8dec2-128">Wystawcy uwierzytelnienie i uwierzytelnienie zgadzają się na algorytm i wymieniają dane wykorzystywane jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="8dec2-128">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="8dec2-129">Klient może obliczyć skrót i wysłać go do usługi.</span><span class="sxs-lookup"><span data-stu-id="8dec2-129">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="8dec2-130">Usługa oblicza również wartość skrótu i porównuje wartości.</span><span class="sxs-lookup"><span data-stu-id="8dec2-130">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="8dec2-131">Dopasowanie sprawdza poprawność klienta.</span><span class="sxs-lookup"><span data-stu-id="8dec2-131">A match validates the client.</span></span>  
  
 <span data-ttu-id="8dec2-132">Ta funkcja musi być włączona z Active Directory w systemie Windows i Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="8dec2-132">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="8dec2-133">Aby uzyskać więcej informacji, zobacz [uwierzytelnianie szyfrowane w usługach IIS 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="8dec2-133">For more information, see [Digest Authentication in IIS 6.0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dec2-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8dec2-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="8dec2-135">Zachowania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="8dec2-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- <span data-ttu-id="8dec2-136">[Zabezpieczanie klientów [WCF]](../../../wcf/securing-clients.md)</span><span class="sxs-lookup"><span data-stu-id="8dec2-136">[Securing Clients](../../../wcf/securing-clients.md)</span></span>
- [<span data-ttu-id="8dec2-137">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="8dec2-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="8dec2-138">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="8dec2-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
