---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 7d8eb27b8a569b1ca6b65a7c8c70c6fb82f701a4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201580"
---
# \<authorizationPolicies>

Ta sekcja konfiguracji zawiera kolekcję typów zasad autoryzacji, które można dodać za pomocą `add` słowa kluczowego. Każda zasada autoryzacji zawiera jeden wymagany `policyType` atrybut, który jest ciągiem. Ten atrybut określa zasady autoryzacji, które umożliwiają przekształcanie jednego zestawu oświadczeń wejściowych w inny zestaw oświadczeń. Na podstawie tego można udzielić lub odmówić kontroli dostępu. Aby uzyskać więcej informacji na temat działania zasad autoryzacji, zobacz <xref:System.IdentityModel.Policy.IAuthorizationPolicy> i [zasady autoryzacji](../../../wcf/samples/authorization-policy.md).  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [Autoryzowanie dostępu do operacji usługi](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [Instrukcje: tworzenie menedżera autoryzacji niestandardowej dla usługi](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [Zasady autoryzacji](../../../wcf/samples/authorization-policy.md)
