---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d7e89acedc8fc1004b0198172e58813944df85f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262310"
---
# <a name="servicecredentials"></a><span data-ttu-id="193e3-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="193e3-102">ServiceCredentials</span></span>

<span data-ttu-id="193e3-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="193e3-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="193e3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="193e3-104">Syntax</span></span>  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="193e3-105">Metody</span><span class="sxs-lookup"><span data-stu-id="193e3-105">Methods</span></span>  

 <span data-ttu-id="193e3-106">Klasa ServiceCredentials nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="193e3-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="193e3-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="193e3-107">Properties</span></span>  

 <span data-ttu-id="193e3-108">Klasa ServiceCredentials ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="193e3-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="193e3-109">Kolekcja</span><span class="sxs-lookup"><span data-stu-id="193e3-109">ClientCertificate</span></span>  

 <span data-ttu-id="193e3-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="193e3-110">Data type: string</span></span>  
  
 <span data-ttu-id="193e3-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="193e3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="193e3-112">Ustawienia uwierzytelniania certyfikatu klienta i aprowizacji dla tej usługi.</span><span class="sxs-lookup"><span data-stu-id="193e3-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="193e3-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="193e3-113">IssuedTokenAuthentication</span></span>  

 <span data-ttu-id="193e3-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="193e3-114">Data type: string</span></span>  
  
 <span data-ttu-id="193e3-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="193e3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="193e3-116">Bieżące ustawienia uwierzytelniania wystawionego tokenu dla tej usługi.</span><span class="sxs-lookup"><span data-stu-id="193e3-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="193e3-117">Element równorzędny</span><span class="sxs-lookup"><span data-stu-id="193e3-117">Peer</span></span>  

 <span data-ttu-id="193e3-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="193e3-118">Data type: string</span></span>  
  
 <span data-ttu-id="193e3-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="193e3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="193e3-120">Bieżące ustawienia uwierzytelniania i inicjowania obsługi poświadczeń, które będą używane przez punkty końcowe transportu elementu równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="193e3-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="193e3-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="193e3-121">SecureConversationAuthentication</span></span>  

 <span data-ttu-id="193e3-122">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="193e3-122">Data type: string</span></span>  
  
 <span data-ttu-id="193e3-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="193e3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="193e3-124">Określa bieżące ustawienia bezpiecznej konwersacji.</span><span class="sxs-lookup"><span data-stu-id="193e3-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="193e3-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="193e3-125">ServiceCertificate</span></span>  

 <span data-ttu-id="193e3-126">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="193e3-126">Data type: string</span></span>  
  
 <span data-ttu-id="193e3-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="193e3-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="193e3-128">Certyfikat skojarzony z tą usługą.</span><span class="sxs-lookup"><span data-stu-id="193e3-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="193e3-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="193e3-129">UserNameAuthentication</span></span>  

 <span data-ttu-id="193e3-130">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="193e3-130">Data type: string</span></span>  
  
 <span data-ttu-id="193e3-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="193e3-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="193e3-132">Ustawienia nazwy użytkownika/hasła dla tej usługi.</span><span class="sxs-lookup"><span data-stu-id="193e3-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="193e3-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="193e3-133">WindowsAuthentication</span></span>  

 <span data-ttu-id="193e3-134">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="193e3-134">Data type: string</span></span>  
  
 <span data-ttu-id="193e3-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="193e3-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="193e3-136">Ustawienia uwierzytelniania systemu Windows dla tej usługi.</span><span class="sxs-lookup"><span data-stu-id="193e3-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="193e3-137">Wymagania</span><span class="sxs-lookup"><span data-stu-id="193e3-137">Requirements</span></span>  
  
|<span data-ttu-id="193e3-138">PLIK</span><span class="sxs-lookup"><span data-stu-id="193e3-138">MOF</span></span>|<span data-ttu-id="193e3-139">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="193e3-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="193e3-140">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="193e3-140">Namespace</span></span>|<span data-ttu-id="193e3-141">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="193e3-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="193e3-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="193e3-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
