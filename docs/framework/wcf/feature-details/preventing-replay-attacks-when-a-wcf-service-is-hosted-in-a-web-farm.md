---
title: Zapobieganie atakom polegającym na odtwarzaniu, gdy usługa WCF jest hostowana na farmie sieci Web
ms.date: 03/30/2017
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
ms.openlocfilehash: 23d0ce32ea4c2450d669b8ca9d887a633f0d99ea
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244785"
---
# <a name="preventing-replay-attacks-when-a-wcf-service-is-hosted-in-a-web-farm"></a>Zapobieganie atakom polegającym na odtwarzaniu, gdy usługa WCF jest hostowana na farmie sieci Web

W przypadku korzystania z usługi WCF w celu zabezpieczenia komunikatów Zapobiegaj atakom metodą powtórzeń, tworząc identyfikator JEDNORAZOWy komunikatu przychodzącego i sprawdzając, `InMemoryNonceCache` czy wygenerowany identyfikator jednorazowy jest obecny. Jeśli tak jest, komunikat zostanie odrzucony jako odtwarzany. Gdy usługa WCF jest hostowana w kolektywie serwerów sieci Web, ponieważ `InMemoryNonceCache` nie jest ona współdzielona przez węzły w kolektywie serwerów sieci Web, usługa jest narażona na ataki metodą powtórzeń.  Aby wyeliminować ten scenariusz, środowisko WCF 4,5 zapewnia punkt rozszerzalności, który umożliwia zaimplementowanie własnej udostępnionej pamięci podręcznej NONCE przez wyjęcie klasy z klasy abstrakcyjnej <xref:System.ServiceModel.Security.NonceCache> .  
  
## <a name="noncecache-implementation"></a>Implementacja NonceCache  

 W celu zaimplementowania własnej udostępnionej pamięci podręcznej NONCE należy utworzyć klasę z <xref:System.ServiceModel.Security.NonceCache> i zastąpić <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> metody i. <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> sprawdzi, czy określony identyfikator JEDNORAZOWy istnieje w pamięci podręcznej. <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> spróbuje dodać identyfikator JEDNORAZOWy do pamięci podręcznej. Po zaimplementowaniu klasy należy ją podłączyć, tworząc wystąpienie wystąpienia i przypisując je do <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.NonceCache%2A> wykrywania powtarzania po stronie klienta oraz <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NonceCache%2A> do wykrywania powtarzania po stronie serwera. Ta funkcja nie zawiera żadnej z dostępnych konfiguracji usługi Box.  
  
## <a name="see-also"></a>Zobacz też

- [Zabezpieczenia komunikatów](message-security-in-wcf.md)
- [SymmetricSecurityBindingElement](../diagnostics/wmi/symmetricsecuritybindingelement.md)
