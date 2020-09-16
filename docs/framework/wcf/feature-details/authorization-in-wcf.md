---
title: Autoryzacja w programie WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: c86a07b96b15963af9f078b52bc0d28e9a38187a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556261"
---
# <a name="authorization-in-wcf"></a>Autoryzacja w programie WCF
Autoryzacja to proces kontroli dostępu i praw do zasobów, takich jak usługi lub pliki. W tematach w tej sekcji pokazano, jak wykonać to podstawowe zadanie w programie Windows Communication Foundation (WCF) na wiele sposobów.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Mechanizmy kontroli dostępu](access-control-mechanisms.md)  
 Zawiera krótki zarys mechanizmów autoryzacji w programie WCF oraz Sugerowane zastosowania.  
  
 [Instrukcje: Ograniczanie dostępu przy użyciu klasy PrincipalPermissionAttribute](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Pokazuje proces ograniczania dostępu do usługi za pomocą programu <xref:System.Security.Permissions.PrincipalPermissionAttribute> .  
  
 [Instrukcje: używanie dostawcy ról ASP.NET razem z usługą](how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Przeprowadzi procedurę konfigurowania usługi, aby umożliwić jej korzystanie z funkcji dostawcy roli programu ASP.NET.  
  
 [Instrukcje: używanie dostawcy roli menedżera autoryzacji platformy ASP.NET za pomocą usługi](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 ASP.NET może używać Menedżera autoryzacji do zarządzania autoryzacją witryny sieci Web. Usługa WCF może w podobny sposób korzystać z kombinacji ASP.NET/Authorization Manager na potrzeby autoryzacji klientów.  
  
 [Zarządzanie oświadczeniami i autoryzacją za pomocą modelu tożsamości](managing-claims-and-authorization-with-the-identity-model.md)  
 Wyjaśnia podstawowe informacje dotyczące korzystania z infrastruktury modelu tożsamości na potrzeby autoryzacji opartej na oświadczeniach.  
  
 [Delegowanie i personifikacja](delegation-and-impersonation-with-wcf.md)  
 Wyjaśnia różnicę między delegowaniem a personifikacją.  
  
## <a name="reference"></a>Tematy pomocy  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Authentication](authentication-in-wcf.md)  
  
## <a name="see-also"></a>Zobacz także

- [Przegląd zabezpieczeń](security-overview.md)
- [Model zabezpieczeń dla sieci szkieletowej aplikacji systemu Windows Server](/previous-versions/appfabric/ee677202(v=azure.10))
