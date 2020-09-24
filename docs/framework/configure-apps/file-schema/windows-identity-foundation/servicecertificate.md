---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: ce8be6eea5469b099a368a0b62e791faa7e3cbfc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156995"
---
# \<serviceCertificate>

<span data-ttu-id="194e0-101">Konfiguruje certyfikat X. 509, który jest używany do szyfrowania i odszyfrowywania tokenów.</span><span class="sxs-lookup"><span data-stu-id="194e0-101">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="194e0-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="194e0-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="194e0-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="194e0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="194e0-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="194e0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="194e0-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="194e0-105">Attributes</span></span>  

 <span data-ttu-id="194e0-106">Brak</span><span class="sxs-lookup"><span data-stu-id="194e0-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="194e0-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="194e0-107">Child Elements</span></span>  
  
|<span data-ttu-id="194e0-108">Element</span><span class="sxs-lookup"><span data-stu-id="194e0-108">Element</span></span>|<span data-ttu-id="194e0-109">Opis</span><span class="sxs-lookup"><span data-stu-id="194e0-109">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="194e0-110">Określa ustawienia, które są używane do znajdowania i weryfikowania certyfikatu X. 509 w magazynie certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="194e0-110">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="194e0-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="194e0-111">Parent Elements</span></span>  
  
|<span data-ttu-id="194e0-112">Element</span><span class="sxs-lookup"><span data-stu-id="194e0-112">Element</span></span>|<span data-ttu-id="194e0-113">Opis</span><span class="sxs-lookup"><span data-stu-id="194e0-113">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="194e0-114">Zawiera ustawienia, które konfigurują <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) i <xref:System.IdentityModel.Services.SessionAuthenticationModule> (sam).</span><span class="sxs-lookup"><span data-stu-id="194e0-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="194e0-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="194e0-115">Example</span></span>  

 <span data-ttu-id="194e0-116">Poniższy kod XML pokazuje użycie \<serviceCertificate> elementu.</span><span class="sxs-lookup"><span data-stu-id="194e0-116">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="194e0-117">KOD XML jest pobierany z `CustomToken` przykładu.</span><span class="sxs-lookup"><span data-stu-id="194e0-117">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
