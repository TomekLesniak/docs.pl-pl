---
title: 'Instrukcje: Personifikowanie klienta w usłudze'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, impersonation
- impersonation
- WCF, security
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
ms.openlocfilehash: 24a06df5b6fbb908aff3ef1b2166fd5162549ba2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290117"
---
# <a name="how-to-impersonate-a-client-on-a-service"></a>Instrukcje: Personifikowanie klienta w usłudze

Personifikowanie klienta w usłudze Windows Communication Foundation (WCF) umożliwia usłudze wykonywanie akcji w imieniu klienta. W przypadku akcji podlegających testom listy kontroli dostępu (ACL), takich jak dostęp do katalogów i plików na komputerze lub dostęp do bazy danych SQL Server, sprawdzanie listy ACL jest związane z kontem użytkownika klienta. W tym temacie przedstawiono podstawowe kroki wymagane do włączenia klienta w domenie systemu Windows w celu ustawienia poziomu personifikacji klienta. Aby zapoznać się z przykładem, zobacz [Personifikowanie klienta](./samples/impersonating-the-client.md). Aby uzyskać więcej informacji na temat personifikacji klientów, zobacz [delegowanie i personifikacja](./feature-details/delegation-and-impersonation-with-wcf.md).  
  
> [!NOTE]
> Gdy klient i usługa są uruchomione na tym samym komputerze, a klient jest uruchomiony przy użyciu konta systemowego (czyli `Local System` lub `Network Service` ), nie można spersonifikować klienta w przypadku ustanowienia bezpiecznej sesji z tokenami kontekstu zabezpieczeń stanowych. Kontrolki WinForm lub Aplikacja konsolowa są zwykle uruchamiane w ramach aktualnie zalogowanego konta, dzięki czemu konto może być domyślnie personifikowane. Jeśli jednak klient jest stroną ASP.NET, a ta strona jest hostowana w usługach IIS 6,0 lub IIS 7,0, klient domyślnie uruchamia się w ramach `Network Service` konta. Wszystkie powiązania dostarczone przez system obsługujące bezpieczne sesje domyślnie korzystają z tokenu bezstanowego kontekstu zabezpieczeń. Jeśli jednak klient jest stroną ASP.NET i są używane bezpieczne sesje z tokenami kontekstu zabezpieczeń stanowe, nie można spersonifikować klienta. Aby uzyskać więcej informacji o korzystaniu z tokenów kontekstu zabezpieczeń stanowych w bezpiecznej sesji, zobacz [How to: Create a Security Context token for a Secure Session](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-enable-impersonation-of-a-client-from-a-cached-windows-token-on-a-service"></a>Aby włączyć personifikację klienta z poziomu buforowanego tokenu systemu Windows w usłudze  
  
1. Utwórz usługę. Aby zapoznać się z samouczkiem dotyczącym tej podstawowej procedury, zobacz [samouczek wprowadzenie](getting-started-tutorial.md).  
  
2. Użyj powiązania, które używa uwierzytelniania systemu Windows i tworzy sesję, taką jak <xref:System.ServiceModel.NetTcpBinding> lub <xref:System.ServiceModel.WSHttpBinding> .  
  
3. Podczas tworzenia implementacji interfejsu usługi należy zastosować <xref:System.ServiceModel.OperationBehaviorAttribute> klasę do metody wymagającej personifikacji klienta. Ustaw <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> Właściwość na wartość <xref:System.ServiceModel.ImpersonationOption.Required> .  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### <a name="to-set-the-allowed-impersonation-level-on-the-client"></a>Aby ustawić dozwolony poziom personifikacji na kliencie  
  
1. Utwórz kod klienta usługi przy użyciu [Narzędzia metadanych ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md). Aby uzyskać więcej informacji, zobacz [Uzyskiwanie dostępu do usług za pomocą klienta WCF](accessing-services-using-a-wcf-client.md).  
  
2. Po utworzeniu klienta WCF należy ustawić <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> Właściwość <xref:System.ServiceModel.Security.WindowsClientCredential> klasy na jedną z <xref:System.Security.Principal.TokenImpersonationLevel> wartości wyliczenia.  
  
    > [!NOTE]
    > Aby <xref:System.Security.Principal.TokenImpersonationLevel.Delegation> można było używać negocjowanego uwierzytelniania Kerberos (czasami nazywanego *wieloetapowym* lub *wieloetapowym* Kerberos). Aby uzyskać opis sposobu wdrażania tego rozwiązania, zobacz [najlepsze rozwiązania w zakresie zabezpieczeń](./feature-details/best-practices-for-security-in-wcf.md).  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.OperationBehaviorAttribute>
- <xref:System.Security.Principal.TokenImpersonationLevel>
- [Personifikowanie klienta](./samples/impersonating-the-client.md)
- [Delegowanie i personifikacja](./feature-details/delegation-and-impersonation-with-wcf.md)
