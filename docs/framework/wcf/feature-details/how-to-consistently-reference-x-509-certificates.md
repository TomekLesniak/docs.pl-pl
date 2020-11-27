---
title: 'Instrukcje: spójne odwoływanie się do certyfikatów X.509'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: b5be8990384178c1954834204c23c0b9cf4a5ad9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257278"
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="2ae0e-102">Instrukcje: spójne odwoływanie się do certyfikatów X.509</span><span class="sxs-lookup"><span data-stu-id="2ae0e-102">How to: Consistently Reference X.509 Certificates</span></span>

<span data-ttu-id="2ae0e-103">Certyfikat można zidentyfikować na kilka sposobów: przez skrót certyfikatu, wystawcy i numer seryjny lub identyfikator klucza podmiotu (narciarski).</span><span class="sxs-lookup"><span data-stu-id="2ae0e-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="2ae0e-104">NARCIARSKIe informacje zapewniają unikatową identyfikację klucza publicznego podmiotu certyfikatu i często są używane podczas pracy z podpisywaniem cyfrowym XML.</span><span class="sxs-lookup"><span data-stu-id="2ae0e-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="2ae0e-105">Wartość SKI jest zwykle częścią certyfikatu X. 509 jako *rozszerzenia certyfikatu x. 509*.</span><span class="sxs-lookup"><span data-stu-id="2ae0e-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> <span data-ttu-id="2ae0e-106">Windows Communication Foundation (WCF) ma domyślny *styl odwoływania* się, który używa wystawcy i numeru seryjnego, jeśli w certyfikacie brakuje rozszerzenia Ski.</span><span class="sxs-lookup"><span data-stu-id="2ae0e-106">Windows Communication Foundation (WCF) has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="2ae0e-107">Jeśli certyfikat zawiera rozszerzenie SKI, domyślny styl odwoływania używa do nadawania certyfikatu certyfikat.</span><span class="sxs-lookup"><span data-stu-id="2ae0e-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="2ae0e-108">W przypadku korzystania z rozwiązania do tworzenia aplikacji można przełączać się za pomocą certyfikatów, które nie używają rozszerzenia NARCIARSKIe w przypadku certyfikatów korzystających z tego rozszerzenia, ale również zmiany stylu odwołania użytego w komunikatach generowanych przez program WCF.</span><span class="sxs-lookup"><span data-stu-id="2ae0e-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in WCF-generated messages also changes.</span></span>  
  
 <span data-ttu-id="2ae0e-109">Jeśli spójny styl odwołania jest wymagany niezależnie od obecności rozszerzenia NARCIARSKIego, możliwe jest skonfigurowanie żądanego stylu odwołania, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="2ae0e-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ae0e-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="2ae0e-110">Example</span></span>  

 <span data-ttu-id="2ae0e-111">Poniższy przykład tworzy niestandardowy element powiązania zabezpieczeń, który używa pojedynczego spójnego stylu odniesienia, nazwy wystawcy i numeru seryjnego.</span><span class="sxs-lookup"><span data-stu-id="2ae0e-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ae0e-112">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="2ae0e-112">Compiling the Code</span></span>  

 <span data-ttu-id="2ae0e-113">Do skompilowania kodu wymagane są następujące przestrzenie nazw:</span><span class="sxs-lookup"><span data-stu-id="2ae0e-113">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="2ae0e-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2ae0e-114">See also</span></span>

- [<span data-ttu-id="2ae0e-115">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="2ae0e-115">Working with Certificates</span></span>](working-with-certificates.md)
