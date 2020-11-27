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
# <a name="how-to-consistently-reference-x509-certificates"></a>Instrukcje: spójne odwoływanie się do certyfikatów X.509

Certyfikat można zidentyfikować na kilka sposobów: przez skrót certyfikatu, wystawcy i numer seryjny lub identyfikator klucza podmiotu (narciarski). NARCIARSKIe informacje zapewniają unikatową identyfikację klucza publicznego podmiotu certyfikatu i często są używane podczas pracy z podpisywaniem cyfrowym XML. Wartość SKI jest zwykle częścią certyfikatu X. 509 jako *rozszerzenia certyfikatu x. 509*. Windows Communication Foundation (WCF) ma domyślny *styl odwoływania* się, który używa wystawcy i numeru seryjnego, jeśli w certyfikacie brakuje rozszerzenia Ski. Jeśli certyfikat zawiera rozszerzenie SKI, domyślny styl odwoływania używa do nadawania certyfikatu certyfikat. W przypadku korzystania z rozwiązania do tworzenia aplikacji można przełączać się za pomocą certyfikatów, które nie używają rozszerzenia NARCIARSKIe w przypadku certyfikatów korzystających z tego rozszerzenia, ale również zmiany stylu odwołania użytego w komunikatach generowanych przez program WCF.  
  
 Jeśli spójny styl odwołania jest wymagany niezależnie od obecności rozszerzenia NARCIARSKIego, możliwe jest skonfigurowanie żądanego stylu odwołania, jak pokazano w poniższym kodzie.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład tworzy niestandardowy element powiązania zabezpieczeń, który używa pojedynczego spójnego stylu odniesienia, nazwy wystawcy i numeru seryjnego.  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

 Do skompilowania kodu wymagane są następujące przestrzenie nazw:  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a>Zobacz też

- [Praca z certyfikatami](working-with-certificates.md)
