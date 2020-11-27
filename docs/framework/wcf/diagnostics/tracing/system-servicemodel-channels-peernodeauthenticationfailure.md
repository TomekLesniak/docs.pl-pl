---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: d8abfe6e34439ccf399e37c1285b7b71cebf9870
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258039"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a>System.ServiceModel.Channels.PeerNodeAuthenticationFailure

Uzgadnianie zabezpieczeń z potencjalnym sąsiadem nie powiodło się.  
  
## <a name="description"></a>Opis  

 Ten ślad występuje podczas próby nawiązania bezpiecznego połączenia sąsiada. Przyczyną może być niewystarczające lub nieprawidłowe poświadczenia.  
  
 PeerChannel rozpoznaje pojedynczy typ tokenu dla silnej identyfikacji, certyfikaty X. 509, które zapewniają silny model tożsamości na podstawie typu uwierzytelniania i autoryzacji, które mogą być implementowane. PeerChannel zapewnia również obsługę prostych aplikacji przy użyciu haseł. Haseł można używać tylko w celu zezwalania na wpis w sesji; nie można ich używać do uwierzytelniania wiadomości. Jest to spowodowane tym, że symetryczny token, który jest używany przez grupę elementów równorzędnych, jest trudny i nieodpowiedni do uwierzytelniania źródłowego.  
  
## <a name="troubleshooting"></a>Rozwiązywanie problemów  

 Upewnij się, że wszystkie sąsiedzi mają odpowiednie poświadczenia zabezpieczeń.  
  
## <a name="see-also"></a>Zobacz też

- [Zabezpieczenia kanału równorzędnego](../../feature-details/peer-channel-security.md)
- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
