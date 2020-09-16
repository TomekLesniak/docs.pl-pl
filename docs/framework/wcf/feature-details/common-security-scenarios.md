---
title: Typowe scenariusze zabezpieczeń
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: cfd29f8cae8ac362a5fa1709864dce4ae11b5af6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558891"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="edf15-102">Typowe scenariusze zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="edf15-102">Common Security Scenarios</span></span>
<span data-ttu-id="edf15-103">Tematy w tej sekcji wykazują wiele możliwych konfiguracji zabezpieczeń klientów i usług.</span><span class="sxs-lookup"><span data-stu-id="edf15-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="edf15-104">Konfiguracje różnią się w zależności od liczby czynników.</span><span class="sxs-lookup"><span data-stu-id="edf15-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="edf15-105">Na przykład, czy usługa lub klient znajduje się w intranecie, czy też zabezpieczenia są dostarczane przez system Windows lub transport (na przykład HTTPS).</span><span class="sxs-lookup"><span data-stu-id="edf15-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="edf15-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="edf15-106">In This Section</span></span>  
 [<span data-ttu-id="edf15-107">Niezabezpieczony klient internetowy i usługa</span><span class="sxs-lookup"><span data-stu-id="edf15-107">Internet Unsecured Client and Service</span></span>](internet-unsecured-client-and-service.md)  
 <span data-ttu-id="edf15-108">Przykład publicznego, niezabezpieczonego klienta i usługi.</span><span class="sxs-lookup"><span data-stu-id="edf15-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="edf15-109">Niezabezpieczony klient i usługa w intranecie</span><span class="sxs-lookup"><span data-stu-id="edf15-109">Intranet Unsecured Client and Service</span></span>](intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="edf15-110">Podstawowa usługa Windows Communication Foundation (WCF) opracowana w celu zapewnienia informacji o bezpiecznej sieci prywatnej do aplikacji WCF.</span><span class="sxs-lookup"><span data-stu-id="edf15-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="edf15-111">Zabezpieczenia transportu z uwierzytelnianiem podstawowym</span><span class="sxs-lookup"><span data-stu-id="edf15-111">Transport Security with Basic Authentication</span></span>](transport-security-with-basic-authentication.md)  
 <span data-ttu-id="edf15-112">Aplikacja umożliwia klientom logowanie się przy użyciu uwierzytelniania niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="edf15-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="edf15-113">Zabezpieczenia transportu z uwierzytelnianiem systemu Windows</span><span class="sxs-lookup"><span data-stu-id="edf15-113">Transport Security with Windows Authentication</span></span>](transport-security-with-windows-authentication.md)  
 <span data-ttu-id="edf15-114">Pokazuje klienta i usługę zabezpieczone przez zabezpieczenia systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="edf15-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="edf15-115">Zabezpieczanie transportu za pomocą anonimowego klienta</span><span class="sxs-lookup"><span data-stu-id="edf15-115">Transport Security with an Anonymous Client</span></span>](transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="edf15-116">W tym scenariuszu są stosowane zabezpieczenia transportu (takie jak HTTPS), aby zapewnić poufność i integralność.</span><span class="sxs-lookup"><span data-stu-id="edf15-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="edf15-117">Zabezpieczanie transportu przy użyciu uwierzytelniania certyfikatów</span><span class="sxs-lookup"><span data-stu-id="edf15-117">Transport Security with Certificate Authentication</span></span>](transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="edf15-118">Pokazuje klienta i usługę zabezpieczone przez certyfikat.</span><span class="sxs-lookup"><span data-stu-id="edf15-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="edf15-119">Zabezpieczenia komunikatów z anonimowym klientem</span><span class="sxs-lookup"><span data-stu-id="edf15-119">Message Security with an Anonymous Client</span></span>](message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="edf15-120">Pokazuje klienta i usługę zabezpieczone przez zabezpieczenia komunikatów WCF.</span><span class="sxs-lookup"><span data-stu-id="edf15-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="edf15-121">Zabezpieczenia na poziomie komunikatu z użyciem klienta nazwy użytkownika</span><span class="sxs-lookup"><span data-stu-id="edf15-121">Message Security with a User Name Client</span></span>](message-security-with-a-user-name-client.md)  
 <span data-ttu-id="edf15-122">Klient jest aplikacją Windows Forms, która umożliwia klientom logowanie się przy użyciu nazwy użytkownika domeny i hasła.</span><span class="sxs-lookup"><span data-stu-id="edf15-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="edf15-123">Zabezpieczenia komunikatów z klientem dysponującym certyfikatem</span><span class="sxs-lookup"><span data-stu-id="edf15-123">Message Security with a Certificate Client</span></span>](message-security-with-a-certificate-client.md)  
 <span data-ttu-id="edf15-124">Serwery mają certyfikaty, a każdy klient ma certyfikat.</span><span class="sxs-lookup"><span data-stu-id="edf15-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="edf15-125">Kontekst zabezpieczeń jest ustanawiany za pomocą negocjacji Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="edf15-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="edf15-126">Zabezpieczanie komunikatów za pomocą klienta systemu Windows</span><span class="sxs-lookup"><span data-stu-id="edf15-126">Message Security with a Windows Client</span></span>](message-security-with-a-windows-client.md)  
 <span data-ttu-id="edf15-127">Odmiana klienta certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="edf15-127">A variation of the certificate client.</span></span> <span data-ttu-id="edf15-128">Serwery mają certyfikaty, a każdy klient ma certyfikat.</span><span class="sxs-lookup"><span data-stu-id="edf15-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="edf15-129">Kontekst zabezpieczeń jest ustanawiany za pomocą negocjacji TLS.</span><span class="sxs-lookup"><span data-stu-id="edf15-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="edf15-130">Zabezpieczanie komunikatów za pomocą klienta systemu Windows bez negocjowania poświadczeń</span><span class="sxs-lookup"><span data-stu-id="edf15-130">Message Security with a Windows Client without Credential Negotiation</span></span>](message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="edf15-131">Pokazuje klienta i usługę zabezpieczone przez domenę protokołu Kerberos.</span><span class="sxs-lookup"><span data-stu-id="edf15-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="edf15-132">Zabezpieczenia komunikatów ze wzajemnymi certyfikatami</span><span class="sxs-lookup"><span data-stu-id="edf15-132">Message Security with Mutual Certificates</span></span>](message-security-with-mutual-certificates.md)  
 <span data-ttu-id="edf15-133">Serwery mają certyfikaty, a każdy klient ma certyfikat.</span><span class="sxs-lookup"><span data-stu-id="edf15-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="edf15-134">Certyfikat serwera jest dystrybuowany z aplikacją i jest dostępny poza pasmem.</span><span class="sxs-lookup"><span data-stu-id="edf15-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="edf15-135">Zabezpieczenia komunikatów z wystawionymi tokenami</span><span class="sxs-lookup"><span data-stu-id="edf15-135">Message Security with Issued Tokens</span></span>](message-security-with-issued-tokens.md)  
 <span data-ttu-id="edf15-136">Zabezpieczenia federacyjne, które umożliwiają ustanowienie zaufania między domenami niezależnymi.</span><span class="sxs-lookup"><span data-stu-id="edf15-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="edf15-137">Zaufany podsystem</span><span class="sxs-lookup"><span data-stu-id="edf15-137">Trusted Subsystem</span></span>](trusted-subsystem.md)  
 <span data-ttu-id="edf15-138">Klient uzyskuje dostęp do co najmniej jednej usługi sieci Web, która jest dystrybuowana przez sieć.</span><span class="sxs-lookup"><span data-stu-id="edf15-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="edf15-139">Usługi sieci Web uzyskują dostęp do dodatkowych zasobów (np. baz danych lub innych usług sieci Web), które muszą być zabezpieczone.</span><span class="sxs-lookup"><span data-stu-id="edf15-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="edf15-140">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="edf15-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="edf15-141">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="edf15-141">Related Sections</span></span>  
 [<span data-ttu-id="edf15-142">Autoryzacja</span><span class="sxs-lookup"><span data-stu-id="edf15-142">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="edf15-143">Przegląd zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="edf15-143">Security Overview</span></span>](security-overview.md)  
  
 [<span data-ttu-id="edf15-144">Bezpieczeństwo</span><span class="sxs-lookup"><span data-stu-id="edf15-144">Security</span></span>](security.md)  
  
 [<span data-ttu-id="edf15-145">Wiązania i zabezpieczenia</span><span class="sxs-lookup"><span data-stu-id="edf15-145">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="edf15-146">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="edf15-146">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
 [<span data-ttu-id="edf15-147">Authentication</span><span class="sxs-lookup"><span data-stu-id="edf15-147">Authentication</span></span>](authentication-in-wcf.md)  
  
 [<span data-ttu-id="edf15-148">Autoryzacja</span><span class="sxs-lookup"><span data-stu-id="edf15-148">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="edf15-149">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="edf15-149">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="edf15-150">Inspekcja</span><span class="sxs-lookup"><span data-stu-id="edf15-150">Auditing</span></span>](auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="edf15-151">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="edf15-151">See also</span></span>

- [<span data-ttu-id="edf15-152">Wytyczne dotyczące zabezpieczeń i najlepsze rozwiązania</span><span class="sxs-lookup"><span data-stu-id="edf15-152">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)
- <span data-ttu-id="edf15-153">[Model zabezpieczeń dla sieci szkieletowej aplikacji systemu Windows Server](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="edf15-153">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
