---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c63e1b3de464b306f46e2f0935b1208d7262925a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274195"
---
# <a name="clientcredentials"></a><span data-ttu-id="d6b7f-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="d6b7f-102">ClientCredentials</span></span>

<span data-ttu-id="d6b7f-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="d6b7f-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6b7f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d6b7f-104">Syntax</span></span>  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d6b7f-105">Metody</span><span class="sxs-lookup"><span data-stu-id="d6b7f-105">Methods</span></span>  

 <span data-ttu-id="d6b7f-106">Klasa ClientCredentials nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="d6b7f-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d6b7f-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="d6b7f-107">Properties</span></span>  

 <span data-ttu-id="d6b7f-108">Klasa ClientCredentials ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="d6b7f-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="d6b7f-109">Kolekcja</span><span class="sxs-lookup"><span data-stu-id="d6b7f-109">ClientCertificate</span></span>  

 <span data-ttu-id="d6b7f-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d6b7f-110">Data type: string</span></span>  
  
 <span data-ttu-id="d6b7f-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d6b7f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6b7f-112">Certyfikat X. 509, którego klient używa do uwierzytelniania w usłudze.</span><span class="sxs-lookup"><span data-stu-id="d6b7f-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="d6b7f-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="d6b7f-113">HttpDigest</span></span>  

 <span data-ttu-id="d6b7f-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d6b7f-114">Data type: string</span></span>  
  
 <span data-ttu-id="d6b7f-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d6b7f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6b7f-116">Bieżące poświadczenie HTTP digest.</span><span class="sxs-lookup"><span data-stu-id="d6b7f-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="d6b7f-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="d6b7f-117">IssuedToken</span></span>  

 <span data-ttu-id="d6b7f-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d6b7f-118">Data type: string</span></span>  
  
 <span data-ttu-id="d6b7f-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d6b7f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6b7f-120">Adres punktu końcowego i powiązanie używane do kontaktowania się z usługą tokenu zabezpieczeń lokalnych.</span><span class="sxs-lookup"><span data-stu-id="d6b7f-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="d6b7f-121">Element równorzędny</span><span class="sxs-lookup"><span data-stu-id="d6b7f-121">Peer</span></span>  

 <span data-ttu-id="d6b7f-122">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d6b7f-122">Data type: string</span></span>  
  
 <span data-ttu-id="d6b7f-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d6b7f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6b7f-124">Poświadczenia używane przez węzeł równorzędny do samodzielnego uwierzytelnienia w innych węzłach w sieci.</span><span class="sxs-lookup"><span data-stu-id="d6b7f-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="d6b7f-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="d6b7f-125">ServiceCertificate</span></span>  

 <span data-ttu-id="d6b7f-126">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d6b7f-126">Data type: string</span></span>  
  
 <span data-ttu-id="d6b7f-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d6b7f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6b7f-128">Certyfikat X. 509 usługi.</span><span class="sxs-lookup"><span data-stu-id="d6b7f-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="d6b7f-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="d6b7f-129">SupportInteractive</span></span>  

 <span data-ttu-id="d6b7f-130">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="d6b7f-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="d6b7f-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d6b7f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6b7f-132">Wartość logiczna określająca, czy poświadczenie obsługuje interaktywne negocjowanie.</span><span class="sxs-lookup"><span data-stu-id="d6b7f-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="d6b7f-133">Nazwa użytkownika</span><span class="sxs-lookup"><span data-stu-id="d6b7f-133">UserName</span></span>  

 <span data-ttu-id="d6b7f-134">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d6b7f-134">Data type: string</span></span>  
  
 <span data-ttu-id="d6b7f-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d6b7f-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6b7f-136">Nazwa użytkownika i hasło, których klient używa do samodzielnego uwierzytelnienia w usłudze.</span><span class="sxs-lookup"><span data-stu-id="d6b7f-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="d6b7f-137">Windows</span><span class="sxs-lookup"><span data-stu-id="d6b7f-137">Windows</span></span>  

 <span data-ttu-id="d6b7f-138">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d6b7f-138">Data type: string</span></span>  
  
 <span data-ttu-id="d6b7f-139">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d6b7f-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6b7f-140">Poświadczenia systemu Windows, których klient używa do samodzielnego uwierzytelnienia w usłudze.</span><span class="sxs-lookup"><span data-stu-id="d6b7f-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6b7f-141">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d6b7f-141">Requirements</span></span>  
  
|<span data-ttu-id="d6b7f-142">PLIK</span><span class="sxs-lookup"><span data-stu-id="d6b7f-142">MOF</span></span>|<span data-ttu-id="d6b7f-143">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="d6b7f-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d6b7f-144">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="d6b7f-144">Namespace</span></span>|<span data-ttu-id="d6b7f-145">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d6b7f-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6b7f-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d6b7f-146">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>
