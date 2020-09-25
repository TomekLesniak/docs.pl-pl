---
title: <claimTypeRequirements> dla <message>
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: e70b036fddbc706c8c16de9a0834140f600aa5ef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173799"
---
# <a name="claimtyperequirements-for-message"></a>\<claimTypeRequirements> dla \<message>

Określa kolekcję wymaganych typów roszczeń.  
  
 Kolekcja jest używana przez usługę do określenia wymaganych i opcjonalnych oświadczeń, które muszą znajdować się w wystawionym tokenie używanym przez klienta w celu uzyskania dostępu do usługi. Usługa uwidacznia wymagane typy roszczeń w metadanych, jeśli jest włączona funkcja publikowania WSDL, ale program WCF nie wymaga, aby wystawiony token zawierał określone typy roszczeń. Usługi, które chcą wymusić wymagane typy zgłoszeń, powinny używać zasad autoryzacji.  
  
 W przypadku klientów federacyjnych ta kolekcja zawiera listę wymaganych i opcjonalnych oświadczeń, które są wysyłane do usługi tokenu zabezpieczającego w żądaniu klienta dla wystawionego tokenu.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
