---
title: Protokoły zabezpieczeń wersja 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
ms.openlocfilehash: d98a05bbcb8413c33672a17580c6d16b57c63b83
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254028"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="d08e5-102">Protokoły zabezpieczeń wersja 1.0</span><span class="sxs-lookup"><span data-stu-id="d08e5-102">Security Protocols version 1.0</span></span>

<span data-ttu-id="d08e5-103">Protokoły zabezpieczenia usług w sieci Web zapewniają mechanizmy zabezpieczeń usług sieci Web, które obejmują wszystkie istniejące wymagania dotyczące zabezpieczeń dotyczące komunikatów w przedsiębiorstwie.</span><span class="sxs-lookup"><span data-stu-id="d08e5-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="d08e5-104">W tej sekcji opisano szczegóły dotyczące programu Windows Communication Foundation (WCF) w wersji 1,0 (zaimplementowane w programie <xref:System.ServiceModel.Channels.SecurityBindingElement> ) dla następujących protokołów zabezpieczeń usług sieci Web.</span><span class="sxs-lookup"><span data-stu-id="d08e5-104">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="d08e5-105">Specyfikacja/dokument</span><span class="sxs-lookup"><span data-stu-id="d08e5-105">Specification/Document</span></span>|<span data-ttu-id="d08e5-106">Łącze</span><span class="sxs-lookup"><span data-stu-id="d08e5-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="d08e5-107">WSS: zabezpieczenia komunikatów SOAP 1,0</span><span class="sxs-lookup"><span data-stu-id="d08e5-107">WSS: SOAP Message Security 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|<span data-ttu-id="d08e5-108">WSS: Nazwa użytkownika — profil tokenu 1,0</span><span class="sxs-lookup"><span data-stu-id="d08e5-108">WSS: Username Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="d08e5-109">WSS: Profil tokenu x509 1,0</span><span class="sxs-lookup"><span data-stu-id="d08e5-109">WSS: X509 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|<span data-ttu-id="d08e5-110">WSS: Profil tokenu SAML 1,1 1,0</span><span class="sxs-lookup"><span data-stu-id="d08e5-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|<span data-ttu-id="d08e5-111">WSS: zabezpieczenia komunikatów SOAP 1,1</span><span class="sxs-lookup"><span data-stu-id="d08e5-111">WSS: SOAP Message Security 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|<span data-ttu-id="d08e5-112">Nazwa użytkownika programu WSS username profile 1,1</span><span class="sxs-lookup"><span data-stu-id="d08e5-112">WSS Username Token Profile 1.1</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="d08e5-113">WSS: Profil tokenu X. 509 1,1</span><span class="sxs-lookup"><span data-stu-id="d08e5-113">WSS: X.509 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|<span data-ttu-id="d08e5-114">WSS: Profil tokenu Kerberos 1,1</span><span class="sxs-lookup"><span data-stu-id="d08e5-114">WSS: Kerberos Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|<span data-ttu-id="d08e5-115">WSS: Profil tokenu SAML 1,1 1,1</span><span class="sxs-lookup"><span data-stu-id="d08e5-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|<span data-ttu-id="d08e5-116">WS-Secure konwersacja</span><span class="sxs-lookup"><span data-stu-id="d08e5-116">WS-Secure Conversation</span></span>|<http://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|<span data-ttu-id="d08e5-117">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="d08e5-117">WS-Trust</span></span>|<http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|<span data-ttu-id="d08e5-118">Uwaga dotycząca aplikacji:</span><span class="sxs-lookup"><span data-stu-id="d08e5-118">Application Note:</span></span><br /><br /> <span data-ttu-id="d08e5-119">Używanie WS-Trust do uzgadniania TLS</span><span class="sxs-lookup"><span data-stu-id="d08e5-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="d08e5-120">Do opublikowania</span><span class="sxs-lookup"><span data-stu-id="d08e5-120">To be published</span></span>|  
|<span data-ttu-id="d08e5-121">Uwaga dotycząca aplikacji:</span><span class="sxs-lookup"><span data-stu-id="d08e5-121">Application Note:</span></span><br /><br /> <span data-ttu-id="d08e5-122">Używanie WS-Trust do SPNEGO</span><span class="sxs-lookup"><span data-stu-id="d08e5-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="d08e5-123">Do opublikowania</span><span class="sxs-lookup"><span data-stu-id="d08e5-123">To be published</span></span>|  
|<span data-ttu-id="d08e5-124">Uwaga dotycząca aplikacji:</span><span class="sxs-lookup"><span data-stu-id="d08e5-124">Application Note:</span></span><br /><br /> <span data-ttu-id="d08e5-125">Odwołania i tożsamość punktów końcowych usługi sieci Web</span><span class="sxs-lookup"><span data-stu-id="d08e5-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="d08e5-126">Do opublikowania</span><span class="sxs-lookup"><span data-stu-id="d08e5-126">To be published</span></span>|  
|<span data-ttu-id="d08e5-127">WS-SecurityPolicy 1,1</span><span class="sxs-lookup"><span data-stu-id="d08e5-127">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="d08e5-128">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="d08e5-128">(2005/07)</span></span>|<http://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> <span data-ttu-id="d08e5-129">zmieniony przez [Errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) przesłany do usługi języka Oasis WS-SX Technical Komitetem</span><span class="sxs-lookup"><span data-stu-id="d08e5-129">as amended by [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) submitted to OASIS WS-SX Technical Committee</span></span> |  
  
 <span data-ttu-id="d08e5-130">Program WCF, wersja 1, zapewnia 17 trybów uwierzytelniania, które mogą być używane jako podstawa konfiguracji zabezpieczeń usług sieci Web.</span><span class="sxs-lookup"><span data-stu-id="d08e5-130">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="d08e5-131">Każdy tryb jest zoptymalizowany pod kątem wspólnego zestawu wymagań dotyczących wdrażania, takich jak:</span><span class="sxs-lookup"><span data-stu-id="d08e5-131">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="d08e5-132">Poświadczenia używane do uwierzytelniania klientów i usług.</span><span class="sxs-lookup"><span data-stu-id="d08e5-132">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="d08e5-133">Mechanizmy ochrony komunikatów lub transportu.</span><span class="sxs-lookup"><span data-stu-id="d08e5-133">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="d08e5-134">Wzorce wymiany komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d08e5-134">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="d08e5-135">Tryb uwierzytelniania</span><span class="sxs-lookup"><span data-stu-id="d08e5-135">Authentication Mode</span></span>|<span data-ttu-id="d08e5-136">Uwierzytelnianie klienta</span><span class="sxs-lookup"><span data-stu-id="d08e5-136">Client Authentication</span></span>|<span data-ttu-id="d08e5-137">Uwierzytelnianie serwera</span><span class="sxs-lookup"><span data-stu-id="d08e5-137">Server Authentication</span></span>|<span data-ttu-id="d08e5-138">Tryb</span><span class="sxs-lookup"><span data-stu-id="d08e5-138">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="d08e5-139">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="d08e5-139">UserNameOverTransport</span></span>|<span data-ttu-id="d08e5-140">Nazwa użytkownika/hasło</span><span class="sxs-lookup"><span data-stu-id="d08e5-140">User name/password</span></span>|<span data-ttu-id="d08e5-141">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-141">X509</span></span>|<span data-ttu-id="d08e5-142">Transport</span><span class="sxs-lookup"><span data-stu-id="d08e5-142">Transport</span></span>|  
|<span data-ttu-id="d08e5-143">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="d08e5-143">CertificateOverTransport</span></span>|<span data-ttu-id="d08e5-144">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-144">X509</span></span>|<span data-ttu-id="d08e5-145">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-145">X509</span></span>|<span data-ttu-id="d08e5-146">Transport</span><span class="sxs-lookup"><span data-stu-id="d08e5-146">Transport</span></span>|  
|<span data-ttu-id="d08e5-147">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="d08e5-147">KerberosOverTransport</span></span>|<span data-ttu-id="d08e5-148">Windows</span><span class="sxs-lookup"><span data-stu-id="d08e5-148">Windows</span></span>|<span data-ttu-id="d08e5-149">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-149">X509</span></span>|<span data-ttu-id="d08e5-150">Transport</span><span class="sxs-lookup"><span data-stu-id="d08e5-150">Transport</span></span>|  
|<span data-ttu-id="d08e5-151">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="d08e5-151">IssuedTokenOverTransport</span></span>|<span data-ttu-id="d08e5-152">Federacyjni</span><span class="sxs-lookup"><span data-stu-id="d08e5-152">Federated</span></span>|<span data-ttu-id="d08e5-153">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-153">X509</span></span>|<span data-ttu-id="d08e5-154">Transport</span><span class="sxs-lookup"><span data-stu-id="d08e5-154">Transport</span></span>|  
|<span data-ttu-id="d08e5-155">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="d08e5-155">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="d08e5-156">Windows SSPI negocjowane</span><span class="sxs-lookup"><span data-stu-id="d08e5-156">Windows Sspi Negotiated</span></span>|<span data-ttu-id="d08e5-157">Windows SSPI negocjowane</span><span class="sxs-lookup"><span data-stu-id="d08e5-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="d08e5-158">Transport</span><span class="sxs-lookup"><span data-stu-id="d08e5-158">Transport</span></span>|  
|<span data-ttu-id="d08e5-159">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="d08e5-159">AnonymousForCertificate</span></span>|<span data-ttu-id="d08e5-160">Brak</span><span class="sxs-lookup"><span data-stu-id="d08e5-160">None</span></span>|<span data-ttu-id="d08e5-161">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-161">X509</span></span>|<span data-ttu-id="d08e5-162">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-162">Message</span></span>|  
|<span data-ttu-id="d08e5-163">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="d08e5-163">UserNameForCertificate</span></span>|<span data-ttu-id="d08e5-164">Nazwa użytkownika/hasło</span><span class="sxs-lookup"><span data-stu-id="d08e5-164">User name/password</span></span>|<span data-ttu-id="d08e5-165">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-165">X509</span></span>|<span data-ttu-id="d08e5-166">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-166">Message</span></span>|  
|<span data-ttu-id="d08e5-167">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="d08e5-167">MutualCertificate</span></span>|<span data-ttu-id="d08e5-168">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-168">X509</span></span>|<span data-ttu-id="d08e5-169">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-169">X509</span></span>|<span data-ttu-id="d08e5-170">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-170">Message</span></span>|  
|<span data-ttu-id="d08e5-171">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="d08e5-171">MutualCertificateDuplex</span></span>|<span data-ttu-id="d08e5-172">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-172">X509</span></span>|<span data-ttu-id="d08e5-173">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-173">X509</span></span>|<span data-ttu-id="d08e5-174">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-174">Message</span></span>|  
|<span data-ttu-id="d08e5-175">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="d08e5-175">IssuedTokenForCertificate</span></span>|<span data-ttu-id="d08e5-176">Federacyjni</span><span class="sxs-lookup"><span data-stu-id="d08e5-176">Federated</span></span>|<span data-ttu-id="d08e5-177">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-177">X509</span></span>|<span data-ttu-id="d08e5-178">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-178">Message</span></span>|  
|<span data-ttu-id="d08e5-179">Kerberos</span><span class="sxs-lookup"><span data-stu-id="d08e5-179">Kerberos</span></span>|<span data-ttu-id="d08e5-180">Windows</span><span class="sxs-lookup"><span data-stu-id="d08e5-180">Windows</span></span>|<span data-ttu-id="d08e5-181">Windows</span><span class="sxs-lookup"><span data-stu-id="d08e5-181">Windows</span></span>|<span data-ttu-id="d08e5-182">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-182">Message</span></span>|  
|<span data-ttu-id="d08e5-183">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="d08e5-183">IssuedToken</span></span>|<span data-ttu-id="d08e5-184">Federacyjni</span><span class="sxs-lookup"><span data-stu-id="d08e5-184">Federated</span></span>|<span data-ttu-id="d08e5-185">Federacyjni</span><span class="sxs-lookup"><span data-stu-id="d08e5-185">Federated</span></span>|<span data-ttu-id="d08e5-186">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-186">Message</span></span>|  
|<span data-ttu-id="d08e5-187">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-187">SspiNegotiated</span></span>|<span data-ttu-id="d08e5-188">Windows SSPI negocjowane</span><span class="sxs-lookup"><span data-stu-id="d08e5-188">Windows Sspi Negotiated</span></span>|<span data-ttu-id="d08e5-189">Windows SSPI negocjowane</span><span class="sxs-lookup"><span data-stu-id="d08e5-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="d08e5-190">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-190">Message</span></span>|  
|<span data-ttu-id="d08e5-191">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-191">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="d08e5-192">Brak</span><span class="sxs-lookup"><span data-stu-id="d08e5-192">None</span></span>|<span data-ttu-id="d08e5-193">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="d08e5-193">X509, TLS-Nego</span></span>|<span data-ttu-id="d08e5-194">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-194">Message</span></span>|  
|<span data-ttu-id="d08e5-195">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-195">UserNameForSslNegotiated</span></span>|<span data-ttu-id="d08e5-196">Nazwa użytkownika/hasło</span><span class="sxs-lookup"><span data-stu-id="d08e5-196">User name/password</span></span>|<span data-ttu-id="d08e5-197">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="d08e5-197">X509, TLS-Nego</span></span>|<span data-ttu-id="d08e5-198">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-198">Message</span></span>|  
|<span data-ttu-id="d08e5-199">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-199">MutualSslNegotiated</span></span>|<span data-ttu-id="d08e5-200">X509</span><span class="sxs-lookup"><span data-stu-id="d08e5-200">X509</span></span>|<span data-ttu-id="d08e5-201">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="d08e5-201">X509, TLS-Nego</span></span>|<span data-ttu-id="d08e5-202">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-202">Message</span></span>|  
|<span data-ttu-id="d08e5-203">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-203">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="d08e5-204">Federacyjni</span><span class="sxs-lookup"><span data-stu-id="d08e5-204">Federated</span></span>|<span data-ttu-id="d08e5-205">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="d08e5-205">X509, TLS-Nego</span></span>|<span data-ttu-id="d08e5-206">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="d08e5-206">Message</span></span>|  
  
 <span data-ttu-id="d08e5-207">Punkty końcowe używające takich trybów uwierzytelniania mogą wyrażać wymagania dotyczące zabezpieczeń przy użyciu WS-SecurityPolicy (WS-SP).</span><span class="sxs-lookup"><span data-stu-id="d08e5-207">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="d08e5-208">W tym dokumencie opisano strukturę nagłówka zabezpieczeń i komunikatów infrastruktury dla każdego trybu uwierzytelniania oraz przedstawiono przykłady zasad i komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d08e5-208">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="d08e5-209">Funkcja WCF wykorzystuje WS-SecureConversation, aby zapewnić obsługę bezpiecznych sesji w celu ochrony wymiany wielokomunikatowej między aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="d08e5-209">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="d08e5-210">Aby uzyskać szczegółowe informacje dotyczące implementacji, zobacz sekcję "bezpieczne sesje".</span><span class="sxs-lookup"><span data-stu-id="d08e5-210">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="d08e5-211">Oprócz trybów uwierzytelniania program WCF udostępnia ustawienia do kontrolowania typowych mechanizmów ochrony, które mają zastosowanie do większości trybów uwierzytelniania opartych na zabezpieczeniach komunikatów, na przykład: kolejność podpisu i operacje szyfrowania, zestawy algorytmów, wyprowadzanie kluczy i potwierdzenie podpisu.</span><span class="sxs-lookup"><span data-stu-id="d08e5-211">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="d08e5-212">W tym dokumencie są używane następujące prefiksy i przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="d08e5-212">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="d08e5-213">Prefiks</span><span class="sxs-lookup"><span data-stu-id="d08e5-213">Prefix</span></span>|<span data-ttu-id="d08e5-214">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="d08e5-214">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="d08e5-215">s</span><span class="sxs-lookup"><span data-stu-id="d08e5-215">s</span></span>|<http://www.w3.org/2003/05/soap-envelope/>|
|<span data-ttu-id="d08e5-216">sp</span><span class="sxs-lookup"><span data-stu-id="d08e5-216">sp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|<span data-ttu-id="d08e5-217">a</span><span class="sxs-lookup"><span data-stu-id="d08e5-217">a</span></span>|<http://www.w3.org/2005/08/addressing>|  
|<span data-ttu-id="d08e5-218">wsse</span><span class="sxs-lookup"><span data-stu-id="d08e5-218">wsse</span></span>|<span data-ttu-id="d08e5-219">TBD — JĘZYKA OASIS Z IDENTYFIKATOREM URI PROGRAMU WSS 1,0</span><span class="sxs-lookup"><span data-stu-id="d08e5-219">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="d08e5-220">wsse11</span><span class="sxs-lookup"><span data-stu-id="d08e5-220">wsse11</span></span>|<span data-ttu-id="d08e5-221">TBD — JĘZYKA OASIS Z IDENTYFIKATOREM URI PROGRAMU WSS 1,1</span><span class="sxs-lookup"><span data-stu-id="d08e5-221">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="d08e5-222">wsu</span><span class="sxs-lookup"><span data-stu-id="d08e5-222">wsu</span></span>|<span data-ttu-id="d08e5-223">TBD — identyfikator URI narzędzia języka Oasis WSS 1,0</span><span class="sxs-lookup"><span data-stu-id="d08e5-223">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="d08e5-224">ds</span><span class="sxs-lookup"><span data-stu-id="d08e5-224">ds</span></span>|<span data-ttu-id="d08e5-225">TBD — identyfikator URI XMLDSig W3C</span><span class="sxs-lookup"><span data-stu-id="d08e5-225">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="d08e5-226">wst</span><span class="sxs-lookup"><span data-stu-id="d08e5-226">wst</span></span>|<span data-ttu-id="d08e5-227">TBD — IDENTYFIKATOR URI WS-Trust 2005/02</span><span class="sxs-lookup"><span data-stu-id="d08e5-227">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="d08e5-228">wssc</span><span class="sxs-lookup"><span data-stu-id="d08e5-228">wssc</span></span>|<span data-ttu-id="d08e5-229">TBD — IDENTYFIKATOR URI WS-SecureConversation 2005/02</span><span class="sxs-lookup"><span data-stu-id="d08e5-229">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="d08e5-230">wsaw</span><span class="sxs-lookup"><span data-stu-id="d08e5-230">wsaw</span></span>|<span data-ttu-id="d08e5-231">Do opracowania później — przestrzeń nazw zasad WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="d08e5-231">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="d08e5-232">wsp</span><span class="sxs-lookup"><span data-stu-id="d08e5-232">wsp</span></span>|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|<span data-ttu-id="d08e5-233">mssp</span><span class="sxs-lookup"><span data-stu-id="d08e5-233">mssp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a><span data-ttu-id="d08e5-234">1. profile tokenów</span><span class="sxs-lookup"><span data-stu-id="d08e5-234">1. Token Profiles</span></span>  

 <span data-ttu-id="d08e5-235">Specyfikacja zabezpieczenia usług w sieci Web reprezentuje poświadczenie jako tokeny zabezpieczające.</span><span class="sxs-lookup"><span data-stu-id="d08e5-235">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="d08e5-236">Usługa WCF obsługuje następujące typy tokenów:</span><span class="sxs-lookup"><span data-stu-id="d08e5-236">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="d08e5-237">1,1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="d08e5-237">1.1 UsernameToken</span></span>  

 <span data-ttu-id="d08e5-238">Program WCF jest zgodny z profilami UsernameToken10 i UsernameToken11 z następującymi ograniczeniami:</span><span class="sxs-lookup"><span data-stu-id="d08e5-238">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="d08e5-239">Atrybut R1101 Passwordtype elementu UsernameToken\Password musi być pominięty lub mieć wartość #PasswordText (domyślnie).</span><span class="sxs-lookup"><span data-stu-id="d08e5-239">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="d08e5-240">Jeden może zaimplementować #PasswordDigest przy użyciu rozszerzalności.</span><span class="sxs-lookup"><span data-stu-id="d08e5-240">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="d08e5-241">Zauważono, że #PasswordDigest był często omyłkowo uznawany za bezpieczny mechanizm ochrony hasłem.</span><span class="sxs-lookup"><span data-stu-id="d08e5-241">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="d08e5-242">Ale #PasswordDigest nie może stanowić zamiennika szyfrowania UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="d08e5-242">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="d08e5-243">Głównym celem #PasswordDigest jest ochrona przed atakami metodą powtórzeń.</span><span class="sxs-lookup"><span data-stu-id="d08e5-243">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="d08e5-244">W przypadku trybów uwierzytelniania WCF złośliwe ataki są rozwiązywane za pomocą sygnatur komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d08e5-244">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="d08e5-245">B1102 WCF nigdy nie emituje identyfikatora wiersza i utworzonych elementów podrzędnych UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="d08e5-245">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="d08e5-246">Te elementy podrzędne mają na celu ułatwienie wykrywania powtarzania.</span><span class="sxs-lookup"><span data-stu-id="d08e5-246">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="d08e5-247">Usługa WCF używa zamiast tego sygnatury komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d08e5-247">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="d08e5-248">JĘZYKA Oasis WSS Message Security UsernameToken profil 1,1 (UsernameToken11) wprowadził klucz wyprowadzania z funkcji password.</span><span class="sxs-lookup"><span data-stu-id="d08e5-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="d08e5-249">Hasła B1103 UsernameToken nie można używać do wyprowadzania klucza i w związku z tym dla operacji kryptograficznych.</span><span class="sxs-lookup"><span data-stu-id="d08e5-249">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="d08e5-250">Uzasadnienie: hasła są zwykle uznawane za słabe, aby można było używać ich na potrzeby operacji kryptograficznych.</span><span class="sxs-lookup"><span data-stu-id="d08e5-250">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="d08e5-251">Token x509 1,2</span><span class="sxs-lookup"><span data-stu-id="d08e5-251">1.2 X509 Token</span></span>  

 <span data-ttu-id="d08e5-252">Usługa WCF obsługuje certyfikaty X509v3 jako typ poświadczenia i następuje po X509TokenProfile 1.0 i X509TokenProfile 1.1 z następującymi ograniczeniami:</span><span class="sxs-lookup"><span data-stu-id="d08e5-252">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="d08e5-253">R1201 atrybut ValueType w elemencie BinarySecurityToken musi mieć wartość #X509v3, gdy zawiera certyfikat X509v3.</span><span class="sxs-lookup"><span data-stu-id="d08e5-253">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="d08e5-254">Profil tokenu x509 usług WSS 1,0 i 1,1 definiuje również #X509PKIPathv1 i #PKCS7 jako typy wartości.</span><span class="sxs-lookup"><span data-stu-id="d08e5-254">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="d08e5-255">Program WCF nie obsługuje tych typów.</span><span class="sxs-lookup"><span data-stu-id="d08e5-255">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="d08e5-256">R1202 Jeśli w certyfikacie x509 znajduje się rozszerzenie SubjectKeyIdentifier (SKI), wsse: Identyfikator klucza powinien być używany do odwołań zewnętrznych do tokenu, z atrybutem ValueType jako #X509SubjectKeyIdentifier i jego zawartością jest zakodowana w formacie base64 wartość rozszerzenia SKI certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="d08e5-256">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="d08e5-257">Odwołania NARCIARSKIe są szeroko implementowane i sprawdzane jako typ odwołania zewnętrznego o wysokiej interoperacyjności.</span><span class="sxs-lookup"><span data-stu-id="d08e5-257">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="d08e5-258">R1203 odwołanie zewnętrzne do tokenu zabezpieczającego x509 nie powinno korzystać z usług DS: X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="d08e5-258">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="d08e5-259">R1204 Jeśli X509TokenProfile 1.1 jest używany, odwołanie zewnętrzne do tokenu zabezpieczającego x509 powinno używać odcisku palca wprowadzonego przez WS-Security 1,1.</span><span class="sxs-lookup"><span data-stu-id="d08e5-259">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="d08e5-260">Usługa WCF obsługuje X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="d08e5-260">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="d08e5-261">Występują jednak problemy ze współdziałaniem z X509IssuerSerial: WCF używa ciągu do porównywania dwóch wartości X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="d08e5-261">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="d08e5-262">W związku z tym jeśli jedna zmiana kolejności składników nazwy podmiotu jest wysyłana do usługi WCF odwołanie do certyfikatu, może nie zostać znaleziona.</span><span class="sxs-lookup"><span data-stu-id="d08e5-262">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="d08e5-263">1,3 token Kerberos</span><span class="sxs-lookup"><span data-stu-id="d08e5-263">1.3 Kerberos Token</span></span>  

 <span data-ttu-id="d08e5-264">Usługa WCF obsługuje KerberosTokenProfile 1.1 na potrzeby uwierzytelniania systemu Windows z następującymi ograniczeniami:</span><span class="sxs-lookup"><span data-stu-id="d08e5-264">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="d08e5-265">R1301 token Kerberos musi mieć wartość opakowanego protokołu Kerberos v4 AP_REQ zgodnie z definicją w GSS_API i specyfikacją protokołu Kerberos i musi mieć atrybut ValueType o wartości #GSS_Kerberosv5_AP_REQ.</span><span class="sxs-lookup"><span data-stu-id="d08e5-265">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="d08e5-266">Funkcja WCF używa opakowanego protokołu Kerberos w języku GSS-REQ, a nie od zera-REQ.</span><span class="sxs-lookup"><span data-stu-id="d08e5-266">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="d08e5-267">Jest to najlepsze rozwiązanie w zakresie zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="d08e5-267">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="d08e5-268">1,4 token SAML v 1.1</span><span class="sxs-lookup"><span data-stu-id="d08e5-268">1.4 SAML v1.1 Token</span></span>  

 <span data-ttu-id="d08e5-269">Usługa WCF obsługuje profile tokenów SAML programu WSS 1,0 i 1,1 dla tokenów SAML w wersji 1.1.</span><span class="sxs-lookup"><span data-stu-id="d08e5-269">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="d08e5-270">Istnieje możliwość zaimplementowania innych wersji formatów tokenów języka SAML.</span><span class="sxs-lookup"><span data-stu-id="d08e5-270">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="d08e5-271">1,5 token kontekstu zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="d08e5-271">1.5 Security Context Token</span></span>  

 <span data-ttu-id="d08e5-272">WCF obsługuje token kontekstu zabezpieczeń (SCT) wprowadzony w usłudze WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="d08e5-272">WCF supports the Security Context Token (SCT) introduced in WS-SecureConversation.</span></span> <span data-ttu-id="d08e5-273">SCT służy do reprezentowania kontekstu zabezpieczeń ustanowionego w SecureConversation, a także do protokołów negocjacji binarnych TLS i SSPI, opisanych poniżej.</span><span class="sxs-lookup"><span data-stu-id="d08e5-273">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="d08e5-274">2. typowe parametry zabezpieczeń komunikatów</span><span class="sxs-lookup"><span data-stu-id="d08e5-274">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="d08e5-275">Sygnatura czasowa 2,1</span><span class="sxs-lookup"><span data-stu-id="d08e5-275">2.1 TimeStamp</span></span>  

 <span data-ttu-id="d08e5-276">Obecność sygnatury czasowej jest kontrolowana przy użyciu <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> właściwości <xref:System.ServiceModel.Channels.SecurityBindingElement> klasy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-276">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="d08e5-277">Funkcja WCF zawsze serializować wsse: TimeStamp z polami wsse: Created i wsse: Expires.</span><span class="sxs-lookup"><span data-stu-id="d08e5-277">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="d08e5-278">Wsse: sygnatura czasowa jest zawsze podpisywana przy użyciu podpisywania.</span><span class="sxs-lookup"><span data-stu-id="d08e5-278">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="d08e5-279">2,2 kolejność ochrony</span><span class="sxs-lookup"><span data-stu-id="d08e5-279">2.2 Protection Order</span></span>  

 <span data-ttu-id="d08e5-280">Usługa WCF obsługuje kolejność ochrony wiadomości przed szyfrowaniem i szyfrowanie przed znakiem (zasady zabezpieczeń 1,1).</span><span class="sxs-lookup"><span data-stu-id="d08e5-280">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="d08e5-281">Zalecane jest "podpisywanie przed szyfrowaniem", w tym: komunikaty chronione przy użyciu szyfrowania przed podpisaniem podpisu, chyba że jest używany mechanizm WS-Security 1,1 SignatureConfirmation, a sygnatura z zaszyfrowaną zawartością sprawia, że inspekcja jest trudniejsza.</span><span class="sxs-lookup"><span data-stu-id="d08e5-281">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="d08e5-282">Ochrona za sygnaturą 2,3</span><span class="sxs-lookup"><span data-stu-id="d08e5-282">2.3 Signature Protection</span></span>  

 <span data-ttu-id="d08e5-283">Gdy jest używane szyfrowanie przed znakiem, zaleca się ochronę podpisu, aby zapobiec atakom typu "nadjęcie" na potrzeby odgadnięcia zaszyfrowanej zawartości lub klucza podpisywania (zwłaszcza gdy Token niestandardowy jest używany z słabym materiałem klucza).</span><span class="sxs-lookup"><span data-stu-id="d08e5-283">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="d08e5-284">Pakiet algorytmów 2,4</span><span class="sxs-lookup"><span data-stu-id="d08e5-284">2.4 Algorithm Suite</span></span>  

 <span data-ttu-id="d08e5-285">Usługa WCF obsługuje wszystkie pakiety algorytmów wymienione w zasadach zabezpieczeń 1,1.</span><span class="sxs-lookup"><span data-stu-id="d08e5-285">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="d08e5-286">Tworzenie klucza 2,5</span><span class="sxs-lookup"><span data-stu-id="d08e5-286">2.5 Key Derivation</span></span>  

 <span data-ttu-id="d08e5-287">WCF używa "wyprowadzania klucza dla kluczy symetrycznych" zgodnie z opisem w temacie WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="d08e5-287">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="d08e5-288">Potwierdzenie podpisu 2,6</span><span class="sxs-lookup"><span data-stu-id="d08e5-288">2.6 Signature Confirmation</span></span>  

 <span data-ttu-id="d08e5-289">Potwierdzenie podpisu może być uznawane za ochronę przed atakami typu średniego firmy w celu ochrony zestawu podpisów.</span><span class="sxs-lookup"><span data-stu-id="d08e5-289">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="d08e5-290">2,7 — układ nagłówka zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="d08e5-290">2.7 Security Header Layout</span></span>  

 <span data-ttu-id="d08e5-291">Każdy tryb uwierzytelniania opisuje określony układ nagłówka zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="d08e5-291">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="d08e5-292">Elementy w nagłówku zabezpieczeń są częściowo uporządkowane.</span><span class="sxs-lookup"><span data-stu-id="d08e5-292">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="d08e5-293">Aby zdefiniować kolejność elementów podrzędnych nagłówka zabezpieczeń, WS-Security zasad definiuje następujące tryby układu nagłówka zabezpieczeń:</span><span class="sxs-lookup"><span data-stu-id="d08e5-293">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d08e5-294">Dokładny</span><span class="sxs-lookup"><span data-stu-id="d08e5-294">Strict</span></span>|<span data-ttu-id="d08e5-295">Elementy są dodawane do nagłówka Security, zgodnie z regułami układu numerowanego opisanymi w sekcji zasady zabezpieczeń 7.7.1 zgodnie z ogólną zasadą "DECLARE przed użyciem".</span><span class="sxs-lookup"><span data-stu-id="d08e5-295">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="d08e5-296">Swobodny</span><span class="sxs-lookup"><span data-stu-id="d08e5-296">Lax</span></span>|<span data-ttu-id="d08e5-297">Elementy są dodawane do nagłówka zabezpieczenia w dowolnej kolejności, która jest zgodna z programem WSS: zabezpieczenia komunikatów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="d08e5-297">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="d08e5-298">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="d08e5-298">LaxTimestampFirst</span></span>|<span data-ttu-id="d08e5-299">Analogicznie jak swobodny, z tą różnicą, że pierwszy element w nagłówku zabezpieczeń musi być wsse: timestamp</span><span class="sxs-lookup"><span data-stu-id="d08e5-299">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="d08e5-300">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="d08e5-300">LaxTimestampLast</span></span>|<span data-ttu-id="d08e5-301">Analogicznie jak swobodny, z tą różnicą, że ostatni element w nagłówku zabezpieczeń musi być wsse: timestamp</span><span class="sxs-lookup"><span data-stu-id="d08e5-301">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="d08e5-302">Funkcja WCF obsługuje wszystkie cztery tryby układu nagłówka zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="d08e5-302">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="d08e5-303">Przykłady struktury nagłówka zabezpieczeń i komunikatów dla trybów uwierzytelniania poniżej są zgodne z trybem Strict.</span><span class="sxs-lookup"><span data-stu-id="d08e5-303">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="d08e5-304">2. typowe parametry zabezpieczeń komunikatów</span><span class="sxs-lookup"><span data-stu-id="d08e5-304">2. Common Message Security Parameters</span></span>  

 <span data-ttu-id="d08e5-305">Ta sekcja zawiera przykładowe zasady dla każdego trybu uwierzytelniania wraz z przykładami przedstawiającymi strukturę nagłówka zabezpieczeń w komunikatach wymienianych przez klienta i usługę.</span><span class="sxs-lookup"><span data-stu-id="d08e5-305">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="d08e5-306">Ochrona przed transportem 6,1</span><span class="sxs-lookup"><span data-stu-id="d08e5-306">6.1 Transport Protection</span></span>  

 <span data-ttu-id="d08e5-307">Usługa WCF oferuje pięć trybów uwierzytelniania, które używają bezpiecznego transportu do ochrony komunikatów; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport i SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="d08e5-307">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="d08e5-308">Te tryby uwierzytelniania są konstruowane przy użyciu powiązania transportu opisanego w SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-308">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="d08e5-309">W przypadku trybu uwierzytelniania UserNameOverTransport UsernameToken jest podpisanym tokenem pomocniczym.</span><span class="sxs-lookup"><span data-stu-id="d08e5-309">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="d08e5-310">W przypadku innych trybów uwierzytelniania token pojawia się jako podpisany token zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="d08e5-310">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="d08e5-311">Dodatek C. 1.2 i C. 1.3 z SecurityPolicy opisują szczegóły układu nagłówka zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="d08e5-311">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="d08e5-312">Poniższe przykładowe nagłówki zabezpieczeń pokazują ścisły układ dla danego trybu uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="d08e5-312">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="d08e5-313">Wartość właściwości "klucze pochodne" dla tokenów we wszystkich przypadkach wynosi "false".</span><span class="sxs-lookup"><span data-stu-id="d08e5-313">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="d08e5-314">Wartości różnych właściwości powiązania transportowego są następujące:</span><span class="sxs-lookup"><span data-stu-id="d08e5-314">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="d08e5-315">Sygnatura czasowa: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-315">Timestamp: true</span></span>  
  
 <span data-ttu-id="d08e5-316">Układ nagłówka zabezpieczeń: Strict</span><span class="sxs-lookup"><span data-stu-id="d08e5-316">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="d08e5-317">Pakiet algorytmów: Basic256</span><span class="sxs-lookup"><span data-stu-id="d08e5-317">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="d08e5-318">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="d08e5-318">6.1.1 UsernameOverTransport</span></span>  

 <span data-ttu-id="d08e5-319">W tym trybie uwierzytelniania klient uwierzytelnia się za pomocą tokenu nazwy użytkownika, który jest wyświetlany na warstwie protokołu SOAP jako podpisany token pomocniczy, który jest zawsze wysyłany z inicjatora do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-319">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="d08e5-320">Usługa jest uwierzytelniana przy użyciu certyfikatu X. 509 w warstwie transportowej.</span><span class="sxs-lookup"><span data-stu-id="d08e5-320">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="d08e5-321">Użyte powiązanie jest powiązaniem transportu.</span><span class="sxs-lookup"><span data-stu-id="d08e5-321">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="d08e5-322">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-322">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="d08e5-323">Układ nagłówka zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="d08e5-323">Security Header Layout</span></span>  
  
 <span data-ttu-id="d08e5-324">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-324">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken>  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-325">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-325">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="d08e5-326">CertificateOverTransport 6.1.2</span><span class="sxs-lookup"><span data-stu-id="d08e5-326">6.1.2 CertificateOverTransport</span></span>  

 <span data-ttu-id="d08e5-327">W tym trybie uwierzytelniania klient jest uwierzytelniany przy użyciu certyfikatu X. 509, który jest wyświetlany w warstwie protokołu SOAP jako zatwierdzenie tokenu pomocniczego, który jest zawsze wysyłany z inicjatora do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-327">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="d08e5-328">Usługa jest uwierzytelniana przy użyciu certyfikatu X. 509 w warstwie transportowej.</span><span class="sxs-lookup"><span data-stu-id="d08e5-328">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="d08e5-329">Użyte powiązanie jest powiązaniem transportu.</span><span class="sxs-lookup"><span data-stu-id="d08e5-329">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="d08e5-330">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-330">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />
              <sp:WssX509V3Token10 />
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="d08e5-331">Układ nagłówka zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="d08e5-331">Security Header Layout</span></span>  
  
 <span data-ttu-id="d08e5-332">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-332">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-333">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-333">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="d08e5-334">IssuedTokenOverTransport 6.1.3</span><span class="sxs-lookup"><span data-stu-id="d08e5-334">6.1.3 IssuedTokenOverTransport</span></span>  

 <span data-ttu-id="d08e5-335">W tym trybie uwierzytelniania klient nie jest uwierzytelniany w usłudze, w związku z czym, ale przedstawia token wystawiony przez usługę tokenu zabezpieczającego (STS) i udowadnia znajomość klucza współużytkowanego.</span><span class="sxs-lookup"><span data-stu-id="d08e5-335">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="d08e5-336">Wystawiony token jest wyświetlany w warstwie protokołu SOAP jako zatwierdzenie tokenu, który jest zawsze wysyłany z inicjatora do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-336">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="d08e5-337">Usługa jest uwierzytelniana przy użyciu certyfikatu X. 509 w warstwie transportowej.</span><span class="sxs-lookup"><span data-stu-id="d08e5-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="d08e5-338">Powiązanie jest powiązaniem transportu.</span><span class="sxs-lookup"><span data-stu-id="d08e5-338">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="d08e5-339">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-339">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="d08e5-340">Układ nagłówka zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="d08e5-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="d08e5-341">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-341">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-342">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="d08e5-343">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="d08e5-343">6.1.4 KerberosOverTransport</span></span>  

 <span data-ttu-id="d08e5-344">W tym trybie uwierzytelniania klient jest uwierzytelniany w usłudze przy użyciu biletu protokołu Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d08e5-344">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="d08e5-345">Token Kerberos jest wyświetlany w warstwie protokołu SOAP jako token pomocniczy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-345">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="d08e5-346">Usługa jest uwierzytelniana przy użyciu certyfikatu X. 509 w warstwie transportowej.</span><span class="sxs-lookup"><span data-stu-id="d08e5-346">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="d08e5-347">Powiązanie jest powiązaniem transportu.</span><span class="sxs-lookup"><span data-stu-id="d08e5-347">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="d08e5-348">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-348">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="d08e5-349">Układ nagłówka zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="d08e5-349">Security Header Layout</span></span>  
  
 <span data-ttu-id="d08e5-350">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-350">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-351">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-351">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="d08e5-352">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="d08e5-352">6.1.5 SspiNegotiatedOverTransport</span></span>  

 <span data-ttu-id="d08e5-353">W tym trybie protokół negocjacji jest używany do przeprowadzania uwierzytelniania klienta i serwera.</span><span class="sxs-lookup"><span data-stu-id="d08e5-353">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="d08e5-354">Protokół Kerberos jest używany, jeśli jest to możliwe, w przeciwnym razie NTLM.</span><span class="sxs-lookup"><span data-stu-id="d08e5-354">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="d08e5-355">Wynikający z tego, że SCT zostanie wyświetlony w warstwie protokołu SOAP jako zaświadczanie tokenu pomocniczego, który jest zawsze wysyłany z inicjatora do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-355">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="d08e5-356">Usługa jest również uwierzytelniana w warstwie transportowej przez certyfikat X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-356">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="d08e5-357">Użyte powiązanie jest powiązaniem transportu.</span><span class="sxs-lookup"><span data-stu-id="d08e5-357">The binding used is a transport binding.</span></span> <span data-ttu-id="d08e5-358">"SPNEGO" (negocjowanie) opisuje, jak WCF używa protokołu negocjowania binarnego interfejsu SSPI z usługą WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="d08e5-358">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="d08e5-359">Przykłady nagłówka zabezpieczeń w tej sekcji są po ustanowieniu SCT przez uzgadnianie SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="d08e5-359">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="d08e5-360">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-360">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="d08e5-361">Przykłady nagłówka zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="d08e5-361">Security Header Examples</span></span>  

 <span data-ttu-id="d08e5-362">Po ustanowieniu tokenu kontekstu zabezpieczeń za pośrednictwem uzgadniania SPNEGO przy użyciu WS-Trust negocjowania binarnego komunikaty aplikacji mają nagłówki zabezpieczeń z następującą strukturą.</span><span class="sxs-lookup"><span data-stu-id="d08e5-362">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="d08e5-363">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-363">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-364">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-364">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="d08e5-365">6,2 przy użyciu certyfikatów X. 509 do uwierzytelniania usługi</span><span class="sxs-lookup"><span data-stu-id="d08e5-365">6.2 Using X.509 Certificates for Service Authentication</span></span>  

 <span data-ttu-id="d08e5-366">W tej sekcji opisano następujące tryby uwierzytelniania: MutualCertificate WSS 1.0, wzajemne CertificateDuplex, MutualCertificate WSS 1.1, AnonymousForCertificate, UserNameForCertificate i IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="d08e5-366">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="d08e5-367">6.2.1 MutualCertificate WSS 1.0</span><span class="sxs-lookup"><span data-stu-id="d08e5-367">6.2.1 MutualCertificate WSS1.0</span></span>  

 <span data-ttu-id="d08e5-368">W tym trybie uwierzytelniania klient jest uwierzytelniany przy użyciu certyfikatu X. 509, który jest wyświetlany w warstwie protokołu SOAP jako token inicjatora.</span><span class="sxs-lookup"><span data-stu-id="d08e5-368">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="d08e5-369">Usługa jest również uwierzytelniana przy użyciu certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-369">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="d08e5-370">Używane powiązanie jest powiązaniem asymetrycznym z następującymi wartościami właściwości:</span><span class="sxs-lookup"><span data-stu-id="d08e5-370">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="d08e5-371">Token inicjatora: certyfikat X. 509 klienta z trybem dołączania ustawionym na. ../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="d08e5-371">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="d08e5-372">Token adresata: certyfikat X. 509 serwera z ustawionym trybem dołączania. ../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="d08e5-372">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="d08e5-373">Ochrona tokenu: FAŁSZ</span><span class="sxs-lookup"><span data-stu-id="d08e5-373">Token Protection: False</span></span>  
  
 <span data-ttu-id="d08e5-374">Cały podpis nagłówka i treści: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-374">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d08e5-375">Kolejność ochrony: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d08e5-375">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d08e5-376">Szyfruj sygnaturę: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-376">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d08e5-377">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-377">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-378">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-378">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-379">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-379">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-380">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-380">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-381">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-381">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="d08e5-382">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-382">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-383">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-383">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="d08e5-384">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="d08e5-384">6.2.2 MutualCertificateDuplex</span></span>  

 <span data-ttu-id="d08e5-385">W tym trybie uwierzytelniania klient jest uwierzytelniany przy użyciu certyfikatu X. 509, który jest wyświetlany w warstwie protokołu SOAP jako token inicjatora.</span><span class="sxs-lookup"><span data-stu-id="d08e5-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="d08e5-386">Usługa jest również uwierzytelniana przy użyciu certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="d08e5-387">Używane powiązanie jest powiązaniem asymetrycznym z następującymi wartościami właściwości:</span><span class="sxs-lookup"><span data-stu-id="d08e5-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="d08e5-388">Token inicjatora: certyfikat x509 klienta, tryb dołączania ma wartość. ../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="d08e5-388">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="d08e5-389">Token adresata: certyfikat x509 serwera, tryb dołączania ma wartość. ../IncludeToken/AlwaysToInitiator</span><span class="sxs-lookup"><span data-stu-id="d08e5-389">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="d08e5-390">Ochrona tokenu: FAŁSZ</span><span class="sxs-lookup"><span data-stu-id="d08e5-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="d08e5-391">Cały podpis nagłówka i treści: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d08e5-392">Kolejność ochrony: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d08e5-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d08e5-393">Szyfruj sygnaturę: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d08e5-394">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-394">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-395">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-396">Żądanie i odpowiedź</span><span class="sxs-lookup"><span data-stu-id="d08e5-396">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-397">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-397">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-398">Żądanie i odpowiedź</span><span class="sxs-lookup"><span data-stu-id="d08e5-398">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="d08e5-399">6.2.3 przy użyciu funkcji Symetrycznebinding z uwierzytelnianiem za pomocą usługi X. 509</span><span class="sxs-lookup"><span data-stu-id="d08e5-399">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  

 <span data-ttu-id="d08e5-400">"WSS10" zapewnia ograniczoną obsługę scenariuszy z tokenami x509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-400">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="d08e5-401">Na przykład nie było możliwości zapewnienia podpisywania i ochrony przed szyfrowaniem komunikatów przy użyciu tylko tokenu x509 usługi.</span><span class="sxs-lookup"><span data-stu-id="d08e5-401">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="d08e5-402">"WSS11" wprowadził Użycie EncryptedKey jako tokenu symetrycznego.</span><span class="sxs-lookup"><span data-stu-id="d08e5-402">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="d08e5-403">Teraz klucz tymczasowy szyfrowany dla certyfikatu X. 509 usługi może być używany zarówno w przypadku ochrony komunikatów żądania, jak i odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="d08e5-403">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="d08e5-404">W przypadku trybów uwierzytelniania opisanych w sekcji 6,4 poniżej Użyj tego wzorca.</span><span class="sxs-lookup"><span data-stu-id="d08e5-404">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="d08e5-405">WS-SecurityPolicy opisuje ten wzorzec przy użyciu programu Symetrycznybinding z tokenem x509 usługi jako tokenem ochrony.</span><span class="sxs-lookup"><span data-stu-id="d08e5-405">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="d08e5-406">Tryby uwierzytelniania AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 i IssuedTokenForCertificate używają podobnego wystąpienia SP: Symetrycznebinding z następującymi wartościami właściwości:</span><span class="sxs-lookup"><span data-stu-id="d08e5-406">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="d08e5-407">Token ochrony: certyfikat x509 serwera, tryb dołączania ma wartość. ../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="d08e5-407">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="d08e5-408">Ochrona tokenu: FAŁSZ</span><span class="sxs-lookup"><span data-stu-id="d08e5-408">Token Protection: False</span></span>  
  
 <span data-ttu-id="d08e5-409">Cały podpis nagłówka i treści: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-409">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d08e5-410">Kolejność ochrony: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d08e5-410">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d08e5-411">Szyfruj sygnaturę: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-411">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d08e5-412">Powyższe tryby uwierzytelniania różnią się tylko przez tokeny pomocnicze, których używają.</span><span class="sxs-lookup"><span data-stu-id="d08e5-412">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="d08e5-413">AnonymousForCertificate nie ma żadnych tokenów pomocniczych, MutualCertificate WSS 1,1 ma certyfikat x509 klienta jako poświadczający tokeny pomocnicze, UserNameForCertificate ma token nazwy użytkownika jako podpisany token pomocniczy, a IssuedTokenForCertificate ma token wystawiony jako token pomocniczy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-413">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="d08e5-414">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-414">Policy</span></span>  
  
 <span data-ttu-id="d08e5-415">Powiązanie symetryczne</span><span class="sxs-lookup"><span data-stu-id="d08e5-415">Symmetric Binding</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireThumbprintReference />
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
          <sp:RequireSignatureConfirmation />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="d08e5-416">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="d08e5-416">6.2.4 AnonymousForCertificate</span></span>  

 <span data-ttu-id="d08e5-417">W tym trybie uwierzytelniania klient jest anonimowy i usługa jest uwierzytelniana przy użyciu certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-417">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="d08e5-418">Użyte powiązanie to wystąpienie powiązania symetrycznego, zgodnie z opisem w 6.4.2.</span><span class="sxs-lookup"><span data-stu-id="d08e5-418">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="d08e5-419">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-419">Policy</span></span>  
  
 <span data-ttu-id="d08e5-420">Aby uzyskać szczegółowe informacje o powiązaniu, zobacz sekcję "zasady" w obszarze 6.2.3 powyżej</span><span class="sxs-lookup"><span data-stu-id="d08e5-420">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-421">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-422">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-422">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-423">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-423">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-424">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-424">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-425">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-425">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-426">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-426">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="d08e5-427">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="d08e5-427">6.2.5 UserNameForCertificate</span></span>  

 <span data-ttu-id="d08e5-428">W tym trybie uwierzytelniania klient jest uwierzytelniany w usłudze przy użyciu tokenu nazwy użytkownika, który pojawia się w warstwie protokołu SOAP jako podpisanego tokenu pomocniczego.</span><span class="sxs-lookup"><span data-stu-id="d08e5-428">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="d08e5-429">Usługa jest uwierzytelniana na kliencie przy użyciu certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-429">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="d08e5-430">Używane powiązanie jest powiązaniem symetrycznym z tokenem ochrony, który jest kluczem generowanym przez klienta, szyfrowanym przy użyciu klucza publicznego usługi.</span><span class="sxs-lookup"><span data-stu-id="d08e5-430">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="d08e5-431">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-431">Policy</span></span>  
  
 <span data-ttu-id="d08e5-432">Aby uzyskać szczegółowe informacje o powiązaniu, zobacz sekcję "zasady" w obszarze 6.2.3 powyżej</span><span class="sxs-lookup"><span data-stu-id="d08e5-432">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="d08e5-433">Podpisany token pomocniczy</span><span class="sxs-lookup"><span data-stu-id="d08e5-433">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-434">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-434">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-435">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-435">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-436">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-436">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-437">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-437">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-438">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-438">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-439">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-439">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="d08e5-440">6.2.6 MutualCertificate (WSS 1,1)</span><span class="sxs-lookup"><span data-stu-id="d08e5-440">6.2.6 MutualCertificate (WSS 1.1)</span></span>  

 <span data-ttu-id="d08e5-441">W tym trybie uwierzytelniania klient jest uwierzytelniany przy użyciu certyfikatu X. 509, który jest wyświetlany w warstwie protokołu SOAP jako token pomocniczy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="d08e5-442">Usługa jest również uwierzytelniana przy użyciu certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="d08e5-443">Używane powiązanie jest powiązaniem symetrycznym z tokenem ochrony, który jest kluczem generowanym przez klienta, szyfrowanym przy użyciu klucza publicznego usługi.</span><span class="sxs-lookup"><span data-stu-id="d08e5-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="d08e5-444">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-444">Policy</span></span>  
  
 <span data-ttu-id="d08e5-445">Szczegóły powiązań można znaleźć w temacie zasady w sekcji 6.2.3</span><span class="sxs-lookup"><span data-stu-id="d08e5-445">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="d08e5-446">Zatwierdzanie tokenu pomocniczego</span><span class="sxs-lookup"><span data-stu-id="d08e5-446">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-447">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-447">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-448">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-448">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-449">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-449">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-450">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-450">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-451">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-451">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-452">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-452">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="d08e5-453">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="d08e5-453">6.2.7 IssuedTokenForCertificate</span></span>  

 <span data-ttu-id="d08e5-454">W tym trybie uwierzytelniania klient nie jest uwierzytelniany w usłudze w taki sposób, ale przedstawia token wystawiony przez usługę STS i udowadnia znajomość klucza współużytkowanego.</span><span class="sxs-lookup"><span data-stu-id="d08e5-454">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="d08e5-455">Wystawiony token pojawia się na warstwie protokołu SOAP jako token pomocniczy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-455">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="d08e5-456">Usługa jest uwierzytelniana na kliencie przy użyciu certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-456">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="d08e5-457">Używane powiązanie jest powiązaniem symetrycznym z tokenem ochrony, który jest kluczem generowanym przez klienta, szyfrowanym przy użyciu klucza publicznego usługi.</span><span class="sxs-lookup"><span data-stu-id="d08e5-457">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="d08e5-458">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-458">Policy</span></span>  
  
 <span data-ttu-id="d08e5-459">Szczegóły powiązania można znaleźć w temacie zasady w sekcji 6.2.3 powyżej</span><span class="sxs-lookup"><span data-stu-id="d08e5-459">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="d08e5-460">Zatwierdzanie tokenu pomocniczego</span><span class="sxs-lookup"><span data-stu-id="d08e5-460">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />
       <sp:RequireInternalReference />
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-461">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-461">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-462">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-462">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-463">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-463">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-464">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-464">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-465">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-465">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-466">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-466">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a><span data-ttu-id="d08e5-467">6,3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="d08e5-467">6.3 Kerberos</span></span>  

 <span data-ttu-id="d08e5-468">W tym trybie uwierzytelniania klient jest uwierzytelniany w usłudze przy użyciu biletu protokołu Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d08e5-468">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="d08e5-469">Ten sam bilet zapewnia również uwierzytelnianie serwera.</span><span class="sxs-lookup"><span data-stu-id="d08e5-469">That same ticket also provides server authentication.</span></span> <span data-ttu-id="d08e5-470">Używane powiązanie jest powiązaniem symetrycznym z następującymi właściwościami:</span><span class="sxs-lookup"><span data-stu-id="d08e5-470">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="d08e5-471">Token ochrony: bilet protokołu Kerberos, tryb dołączania jest ustawiony na wartość. ../IncludeToken/Once</span><span class="sxs-lookup"><span data-stu-id="d08e5-471">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="d08e5-472">Ochrona tokenu: FAŁSZ</span><span class="sxs-lookup"><span data-stu-id="d08e5-472">Token Protection: False</span></span>  
  
 <span data-ttu-id="d08e5-473">Cały podpis nagłówka i treści: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-473">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d08e5-474">Kolejność ochrony: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d08e5-474">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d08e5-475">Szyfruj sygnaturę: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-475">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d08e5-476">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-476">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:WssGssKerberosV5ApReqToken11 />
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-477">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-477">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-478">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-478">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-479">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-479">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-480">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-480">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-481">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-481">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-482">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-482">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="d08e5-483">6,4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="d08e5-483">6.4 IssuedToken</span></span>  

 <span data-ttu-id="d08e5-484">W tym trybie uwierzytelniania klient nie jest uwierzytelniany w usłudze, w związku z czym klient przedstawia token wystawiony przez usługę STS i udowadnia znajomość klucza współużytkowanego.</span><span class="sxs-lookup"><span data-stu-id="d08e5-484">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="d08e5-485">Usługa nie jest uwierzytelniana klientowi, w związku z czym w zamian jest szyfrowany klucz współużytkowany jako część wystawionego tokenu, aby tylko usługa mogła odszyfrować klucz.</span><span class="sxs-lookup"><span data-stu-id="d08e5-485">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="d08e5-486">Używane powiązanie jest powiązaniem symetrycznym z następującymi właściwościami:</span><span class="sxs-lookup"><span data-stu-id="d08e5-486">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="d08e5-487">Token ochrony: wystawiony token, tryb dołączania ma wartość. ../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="d08e5-487">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="d08e5-488">Ochrona tokenu: FAŁSZ</span><span class="sxs-lookup"><span data-stu-id="d08e5-488">Token Protection: False</span></span>  
  
 <span data-ttu-id="d08e5-489">Cały podpis nagłówka i treści: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-489">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d08e5-490">Kolejność ochrony: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d08e5-490">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d08e5-491">Szyfruj sygnaturę: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-491">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d08e5-492">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-492">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireInternalReference />
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-493">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-493">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-494">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-494">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-495">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-495">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-496">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-496">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-497">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-497">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-498">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-498">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="d08e5-499">6,5 użycie SslNegotiated do uwierzytelniania usługi</span><span class="sxs-lookup"><span data-stu-id="d08e5-499">6.5 Using SslNegotiated for Service Authentication</span></span>  

 <span data-ttu-id="d08e5-500">W tej sekcji opisano grupę trybów uwierzytelniania, która używa powiązania symetrycznego z tokenem ochrony z tokenem kontekstu zabezpieczeń na WS-SecureConversation (WS-SC), którego wartość klucza jest negocjowana przez wykonanie protokołu TLS przez przekroczenie WS-Trust (WS-T) RST/RSTR komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d08e5-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="d08e5-501">Szczegóły implementacji uzgadniania TLS przy użyciu WS-Trust są opisane w TLSNEGO.</span><span class="sxs-lookup"><span data-stu-id="d08e5-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="d08e5-502">W tym przykładzie w komunikatach przyjęto założenie, że SCT ze skojarzonym kontekstem zabezpieczeń zostanie już ustanowiony za pomocą uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="d08e5-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="d08e5-503">Używane powiązanie jest powiązaniem symetrycznym z następującymi właściwościami:</span><span class="sxs-lookup"><span data-stu-id="d08e5-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="d08e5-504">Token ochrony: SslContextToken, tryb dołączania jest ustawiony na. ../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="d08e5-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="d08e5-505">Ochrona tokenu: FAŁSZ</span><span class="sxs-lookup"><span data-stu-id="d08e5-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="d08e5-506">Cały podpis nagłówka i treści: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d08e5-507">Kolejność ochrony: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d08e5-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d08e5-508">Szyfruj sygnaturę: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-508">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="d08e5-509">zasady 6.5.1ymi dla uwierzytelniania usługi SslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-509">6.5.1 Policy for SslNegotiated service authentication</span></span>  

 <span data-ttu-id="d08e5-510">Zasady dla wszystkich trybów uwierzytelniania w tej sekcji są podobne i różnią się tylko przez określone podpisane tokeny obsługujące lub zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="d08e5-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient'>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="d08e5-511">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-511">6.5.2 AnonymousForSslNegotiated</span></span>  

 <span data-ttu-id="d08e5-512">W tym trybie uwierzytelniania klient jest anonimowy i usługa jest uwierzytelniana przy użyciu certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="d08e5-513">Użyte powiązanie to wystąpienie powiązania symetrycznego, zgodnie z opisem w 6.5.1 powyżej.</span><span class="sxs-lookup"><span data-stu-id="d08e5-513">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="d08e5-514">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-514">Policy</span></span>  
  
 <span data-ttu-id="d08e5-515">Aby uzyskać szczegółowe informacje dotyczące powiązań, zobacz zasady w 6.5.1 powyżej.</span><span class="sxs-lookup"><span data-stu-id="d08e5-515">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-516">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-516">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-517">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-517">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-518">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-518">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-519">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-519">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-520">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-520">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-521">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-521">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="d08e5-522">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-522">6.5.3 UserNameForSslNegotiated</span></span>  

 <span data-ttu-id="d08e5-523">W tym trybie uwierzytelniania klient jest uwierzytelniany przy użyciu tokenu nazwy użytkownika, który jest wyświetlany na warstwie protokołu SOAP jako podpisanego tokenu pomocniczego.</span><span class="sxs-lookup"><span data-stu-id="d08e5-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="d08e5-524">Usługa jest uwierzytelniana przy użyciu certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="d08e5-525">Użyte powiązanie to wystąpienie powiązania symetrycznego, zgodnie z opisem w 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="d08e5-525">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="d08e5-526">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-526">Policy</span></span>  
  
 <span data-ttu-id="d08e5-527">Szczegóły powiązania można znaleźć w sekcji 6.5.1 powyżej</span><span class="sxs-lookup"><span data-stu-id="d08e5-527">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="d08e5-528">Podpisany token pomocniczy</span><span class="sxs-lookup"><span data-stu-id="d08e5-528">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-529">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-529">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-530">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-530">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-531">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-531">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-532">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-532">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-533">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-533">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-534">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-534">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="d08e5-535">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-535">6.5.4 IssuedTokenForSslNegotiated</span></span>  

 <span data-ttu-id="d08e5-536">W tym trybie uwierzytelniania klient nie jest uwierzytelniany w usłudze w taki sposób, ale przedstawia token wystawiony przez usługę STS i udowadnia znajomość klucza współużytkowanego.</span><span class="sxs-lookup"><span data-stu-id="d08e5-536">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="d08e5-537">Wystawiony token pojawia się na warstwie protokołu SOAP jako token pomocniczy.</span><span class="sxs-lookup"><span data-stu-id="d08e5-537">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="d08e5-538">Usługa jest uwierzytelniana przy użyciu certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-538">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="d08e5-539">Użyte powiązanie to wystąpienie powiązania symetrycznego, zgodnie z opisem w 6.5.1 powyżej.</span><span class="sxs-lookup"><span data-stu-id="d08e5-539">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="d08e5-540">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-540">Policy</span></span>  
  
 <span data-ttu-id="d08e5-541">Szczegóły powiązania można znaleźć w sekcji 6.5.1 powyżej</span><span class="sxs-lookup"><span data-stu-id="d08e5-541">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="d08e5-542">Zatwierdzanie tokenu pomocniczego</span><span class="sxs-lookup"><span data-stu-id="d08e5-542">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />
        <sp:RequireInternalReference />
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-543">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-543">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-544">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-544">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-545">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-545">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-546">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-546">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-547">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-547">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-548">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-548">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="d08e5-549">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-549">6.5.5 MutualSslNegotiated</span></span>  

 <span data-ttu-id="d08e5-550">W tym trybie uwierzytelniania klient i usługa uwierzytelniają się za pomocą certyfikatów X. 509.</span><span class="sxs-lookup"><span data-stu-id="d08e5-550">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="d08e5-551">Użyte powiązanie to wystąpienie powiązania symetrycznego, zgodnie z opisem w 6.5.1 powyżej.</span><span class="sxs-lookup"><span data-stu-id="d08e5-551">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="d08e5-552">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-552">Policy</span></span>  
  
 <span data-ttu-id="d08e5-553">Szczegóły powiązania można znaleźć w sekcji 6.5.1 powyżej</span><span class="sxs-lookup"><span data-stu-id="d08e5-553">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="d08e5-554">Zatwierdzanie tokenu pomocniczego</span><span class="sxs-lookup"><span data-stu-id="d08e5-554">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-555">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-555">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-556">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-556">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-557">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-557">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-558">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-558">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-559">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-559">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-560">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-560">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="d08e5-561">6,6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="d08e5-561">6.6 SspiNegotiated</span></span>  

 <span data-ttu-id="d08e5-562">Przy użyciu tego trybu uwierzytelniania protokół negocjacji jest używany do uwierzytelniania klientów i serwerów.</span><span class="sxs-lookup"><span data-stu-id="d08e5-562">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="d08e5-563">Protokół Kerberos jest używany, jeśli jest to możliwe, w przeciwnym razie NTLM.</span><span class="sxs-lookup"><span data-stu-id="d08e5-563">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="d08e5-564">Używane powiązanie jest powiązaniem symetrycznym z następującymi właściwościami:</span><span class="sxs-lookup"><span data-stu-id="d08e5-564">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="d08e5-565">Token ochrony: SpnegoContextToken, tryb dołączania jest ustawiony na. ../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="d08e5-565">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="d08e5-566">Ochrona tokenu: FAŁSZ</span><span class="sxs-lookup"><span data-stu-id="d08e5-566">Token Protection: False</span></span>  
  
 <span data-ttu-id="d08e5-567">Cały podpis nagłówka i treści: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-567">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d08e5-568">Kolejność ochrony: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d08e5-568">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d08e5-569">Szyfruj sygnaturę: prawda</span><span class="sxs-lookup"><span data-stu-id="d08e5-569">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d08e5-570">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-570">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-571">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-571">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-572">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-572">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-573">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-573">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-574">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-574">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-575">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-575">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-576">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-576">Response</span></span>  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a><span data-ttu-id="d08e5-577">6,7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="d08e5-577">6.7 SecureConversation</span></span>  

 <span data-ttu-id="d08e5-578">Używane powiązanie jest powiązaniem symetrycznym z tokenem ochrony, który jest SCT na WS-SecureConversation (WS-SC).</span><span class="sxs-lookup"><span data-stu-id="d08e5-578">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="d08e5-579">SCT jest negocjowany przy użyciu WS-Trust (WS-Trust) lub WS-SecureConversation (WS-SC) zgodnie z zagnieżdżonym powiązaniem, które jest samym powiązaniem symetrycznym korzystającym z protokołu negocjacji.</span><span class="sxs-lookup"><span data-stu-id="d08e5-579">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="d08e5-580">Protokół negocjacji użyje protokołu Kerberos do przeprowadzenia uwierzytelniania klienta i serwera, o ile jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="d08e5-580">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="d08e5-581">Jeśli nie można użyć protokołu Kerberos, nastąpi powrót do NTLM.</span><span class="sxs-lookup"><span data-stu-id="d08e5-581">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="d08e5-582">Zasady</span><span class="sxs-lookup"><span data-stu-id="d08e5-582">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />
                          <sp:EncryptSignature />
                          <sp:OnlySignEntireHeadersAndBody />
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />
                          <sp:MustSupportRefIssuerSerial />
                          <sp:MustSupportRefThumbprint />
                          <sp:MustSupportRefEncryptedKey />
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />
                          <sp:RequireClientEntropy />
                          <sp:RequireServerEntropy />
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d08e5-583">Przykłady nagłówka zabezpieczeń: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d08e5-583">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="d08e5-584">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-584">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-585">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-585">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d08e5-586">Przykłady nagłówka zabezpieczeń: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d08e5-586">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="d08e5-587">Żądanie</span><span class="sxs-lookup"><span data-stu-id="d08e5-587">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d08e5-588">Reakcja</span><span class="sxs-lookup"><span data-stu-id="d08e5-588">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
