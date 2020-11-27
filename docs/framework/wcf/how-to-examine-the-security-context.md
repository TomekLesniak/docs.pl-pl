---
title: 'Instrukcje: Badanie kontekstu zabezpieczeń'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
ms.openlocfilehash: 40950614892ddfd4eb24194f0389e057a5a13378
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272947"
---
# <a name="how-to-examine-the-security-context"></a>Instrukcje: Badanie kontekstu zabezpieczeń

Podczas programowania usług Windows Communication Foundation (WCF) kontekst zabezpieczenia usługi umożliwia określenie szczegółowych informacji o poświadczeniach klienta i oświadczeniach używanych do uwierzytelniania w usłudze. Jest to realizowane przy użyciu właściwości <xref:System.ServiceModel.ServiceSecurityContext> klasy.  
  
 Na przykład można pobrać tożsamość bieżącego klienta przy użyciu <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> lub <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> właściwości. Aby określić, czy klient jest anonimowy, użyj <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> właściwości.  
  
 Można również określić, jakie oświadczenia są wykonywane w imieniu klienta przez iterację kolekcji oświadczeń we <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> właściwości.  
  
### <a name="to-get-the-current-security-context"></a>Aby uzyskać bieżący kontekst zabezpieczeń  
  
- Uzyskaj dostęp do właściwości statycznej, <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> Aby uzyskać bieżący kontekst zabezpieczeń. Przeanalizuj wszystkie właściwości bieżącego kontekstu z odwołania.  
  
### <a name="to-determine-the-identity-of-the-caller"></a>Aby określić tożsamość obiektu wywołującego  
  
1. Drukuj wartość <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> właściwości i.  
  
### <a name="to-parse-the-claims-of-a-caller"></a>Aby przeanalizować oświadczenia obiektu wywołującego  
  
1. Zwróć bieżącą <xref:System.IdentityModel.Policy.AuthorizationContext> klasę. Użyj <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> właściwości, aby zwrócić bieżący kontekst zabezpieczeń usługi, a następnie Zwróć wartość `AuthorizationContext` przy użyciu <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> właściwości.  
  
2. Przeanalizuj kolekcję <xref:System.IdentityModel.Claims.ClaimSet> obiektów zwracanych przez <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> Właściwość <xref:System.IdentityModel.Policy.AuthorizationContext> klasy.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład drukuje wartości <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> właściwości i bieżącego kontekstu zabezpieczeń oraz <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> Właściwość, wartość zasobu dla żądania oraz <xref:System.IdentityModel.Claims.Claim.Right%2A> Właściwość każdego żądania w bieżącym kontekście zabezpieczeń.  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

 Kod używa następujących przestrzeni nazw:  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.IdentityModel.Policy>  
  
- <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a>Zobacz też

- [Zabezpieczanie usług](securing-services.md)
- [Uwierzytelnianie i tożsamość usług](./feature-details/service-identity-and-authentication.md)
