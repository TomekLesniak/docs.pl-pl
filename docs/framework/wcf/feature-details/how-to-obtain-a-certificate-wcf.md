---
title: 'Instrukcje: Uzyskiwanie certyfikatu (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: b1fea1a7357b937bd15517b313948ead6aab894d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557856"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="1bfe5-102">Instrukcje: Uzyskiwanie certyfikatu (WCF)</span><span class="sxs-lookup"><span data-stu-id="1bfe5-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="1bfe5-103">Aby używać dowolnych funkcji programu Windows Communication Foundation (WCF), które używają certyfikatów X. 509, wystarczy najpierw uzyskać certyfikaty.</span><span class="sxs-lookup"><span data-stu-id="1bfe5-103">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="1bfe5-104">Aby uzyskać certyfikat X. 509</span><span class="sxs-lookup"><span data-stu-id="1bfe5-104">To obtain an X.509 certificate</span></span>  
  
1. <span data-ttu-id="1bfe5-105">Wybierz jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="1bfe5-105">Choose one of the following:</span></span>  
  
    - <span data-ttu-id="1bfe5-106">Kup certyfikat od urzędu certyfikacji, na przykład VeriSign, Inc.</span><span class="sxs-lookup"><span data-stu-id="1bfe5-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    - <span data-ttu-id="1bfe5-107">Skonfiguruj własną usługę certyfikatów i przygotuj certyfikaty przy użyciu urzędu certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="1bfe5-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> <span data-ttu-id="1bfe5-108">Wszystkie systemy Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter i Windows 2000 Datacenter Server obejmują usługi certyfikatów obsługujące infrastrukturę kluczy publicznych (PKI).</span><span class="sxs-lookup"><span data-stu-id="1bfe5-108">Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="1bfe5-109">W systemie Windows Server 2008 Użyj roli [usługi certyfikatów Active Directory](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) do zarządzania urzędem certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="1bfe5-109">In Windows Server 2008, use the [Active Directory Certificate Services](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) role to manage a certification authority.</span></span>  
  
    - <span data-ttu-id="1bfe5-110">Skonfiguruj własną usługę certyfikatów i nie masz podpisanych certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="1bfe5-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1bfe5-111">Niezależnie od tego, jakie podejście zostanie wykonane, odbiorca żądania protokołu SOAP, który zawiera certyfikat X. 509, musi ufać certyfikatowi X. 509.</span><span class="sxs-lookup"><span data-stu-id="1bfe5-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="1bfe5-112">Oznacza to, że certyfikat X. 509 lub wystawca w łańcuchu certyfikatów znajduje się w magazynie certyfikatów osoby zaufane i certyfikat X. 509 nie znajduje się w magazynie certyfikatów niezaufanych.</span><span class="sxs-lookup"><span data-stu-id="1bfe5-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfe5-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1bfe5-113">See also</span></span>

- [<span data-ttu-id="1bfe5-114">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="1bfe5-114">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="1bfe5-115">Instrukcje: tworzenie certyfikatów tymczasowych do używania w trakcie opracowywania</span><span class="sxs-lookup"><span data-stu-id="1bfe5-115">How to: Create Temporary Certificates for Use During Development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
