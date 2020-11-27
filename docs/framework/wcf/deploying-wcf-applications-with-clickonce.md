---
title: Wdrażanie aplikacji WCF za pomocą technologii ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: ad4c603d07885aa16640b71d43038746d3702b05
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260861"
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Wdrażanie aplikacji WCF za pomocą technologii ClickOnce

Aplikacje klienckie korzystające z Windows Communication Foundation (WCF) można wdrożyć przy użyciu technologii ClickOnce. Ta technologia pozwala im wykorzystać ochronę zabezpieczeń środowiska uruchomieniowego zapewnianą przez zabezpieczenia dostępu kodu, pod warunkiem, że są podpisane cyfrowo za pomocą zaufanego certyfikatu. Certyfikat używany do podpisywania aplikacji ClickOnce musi znajdować się w magazynie zaufanych wydawców, a zasady zabezpieczeń lokalnych na komputerze klienckim muszą być skonfigurowane tak, aby przyznać pełne uprawnienia zaufania do aplikacji podpisanych za pomocą certyfikatu wydawcy.  
  
 Aby uzyskać informacje na temat konfigurowania aplikacji ClickOnce i zaufanych wydawców, zobacz [Konfigurowanie zaufanych wydawców ClickOnce](/previous-versions/dotnet/articles/ms996418(v=msdn.10)).  
  
## <a name="see-also"></a>Zobacz też

- [Omówienie wdrażania zaufanych aplikacji](/visualstudio/deployment/trusted-application-deployment-overview)
- [Wdrożenie ClickOnce dla aplikacji Windows Forms](/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))
