---
title: Przesłanianie tożsamości usługi na potrzeby uwierzytelniania
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: 3ac2d48962dd96535e1a08310570212121eca986
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555422"
---
# <a name="override-the-identity-of-a-service-for-authentication"></a>Zastępowanie tożsamości usługi do uwierzytelniania

Zazwyczaj nie trzeba ustawiać tożsamości w usłudze, ponieważ wybór typu poświadczeń klienta określa typ tożsamości uwidocznionej w metadanych usługi. Na przykład poniższy kod konfiguracyjny używa [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) elementu i ustawia `clientCredentialType` atrybut na Windows.  

 Poniższy fragment Web Services Description Language (WSDL) przedstawia tożsamość punktu końcowego zdefiniowanego wcześniej. W tym przykładzie usługa działa jako usługa samodzielna w ramach określonego konta użytkownika ( username@contoso.com ), w związku z czym tożsamość głównej nazwy użytkownika (UPN) zawiera nazwę konta. Nazwa UPN jest również nazywana nazwą logowania użytkownika w domenie systemu Windows.  

 Aby zapoznać się z przykładową aplikacją, która demonstruje ustawienie tożsamości, zobacz [przykład Identity Service](../samples/service-identity-sample.md). Aby uzyskać więcej informacji na temat tożsamości usługi, zobacz [tożsamość usługi i uwierzytelnianie](../feature-details/service-identity-and-authentication.md).  
  
## <a name="kerberos-authentication-and-identity"></a>Uwierzytelnianie i tożsamość Kerberos  
 Domyślnie, gdy usługa jest skonfigurowana do korzystania z poświadczeń systemu Windows, [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element zawierający [\<userPrincipalName>](../../configure-apps/file-schema/wcf/userprincipalname.md) [\<servicePrincipalName>](../../configure-apps/file-schema/wcf/serviceprincipalname.md) element lub jest generowany w języku WSDL. Jeśli usługa jest uruchomiona w ramach `LocalSystem` konta, `LocalService` lub, `NetworkService` Nazwa główna usługi (SPN) jest generowana domyślnie w postaci, `host/` \<*hostname*> ponieważ te konta mają dostęp do danych SPN komputera. Jeśli usługa jest uruchomiona przy użyciu innego konta, Windows Communication Foundation (WCF) generuje nazwę UPN w postaci \<*username*> @< *nazwa_domeny* `>` . Dzieje się tak, ponieważ uwierzytelnianie Kerberos wymaga, aby nazwa UPN lub nazwa SPN była dostarczana do klienta w celu uwierzytelnienia usługi.  
  
 Możesz również użyć narzędzia [Setspn](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731241(v=ws.10)) , aby zarejestrować dodatkową nazwę SPN z kontem usługi w domenie. Następnie można użyć nazwy SPN jako tożsamości usługi. Więcej informacji o narzędziu można znaleźć w temacie [Setspn Overview](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).  
  
> [!NOTE]
> Aby użyć typu poświadczeń systemu Windows bez negocjowania, konto użytkownika usługi musi mieć dostęp do nazwy SPN, która jest zarejestrowana w domenie Active Directory. Można to zrobić w następujący sposób:  
  
- Użyj konta NetworkService lub LocalSystem do uruchomienia usługi. Ponieważ te konta mają dostęp do nazwy SPN maszyny, która została ustanowiona, gdy komputer jest przyłączony do domeny Active Directory, funkcja WCF automatycznie generuje prawidłowy element SPN w ramach punktu końcowego usługi w metadanych usługi (WSDL).  
  
- Użyj dowolnego konta domeny Active Directory, aby uruchomić usługę. W takim przypadku należy ustanowić nazwę SPN dla tego konta domeny, którą można wykonać za pomocą narzędzia Setspn.exe narzędzie. Po utworzeniu nazwy SPN dla konta usługi Skonfiguruj program WCF do publikowania tej nazwy SPN na klientach usługi za pomocą metadanych (WSDL). W tym celu należy ustawić tożsamość punktu końcowego dla uwidocznionego punktu końcowego za pomocą pliku lub kodu konfiguracji aplikacji.  
  
 Aby uzyskać więcej informacji na temat nazw SPN, protokołu Kerberos i Active Directory, zobacz [dodatek dotyczący protokołu Kerberos dla systemu Windows](/previous-versions/msp-n-p/ff649429(v=pandp.10)).  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>Gdy nazwa SPN lub nazwa UPN jest równa pustemu ciągowi  
 Jeśli ustawisz nazwę SPN lub nazwę UPN równą pustemu ciągowi, następuje wiele różnych rzeczy, w zależności od poziomu zabezpieczeń i używanego trybu uwierzytelniania:  
  
- W przypadku korzystania z zabezpieczeń na poziomie transportu jest wybierane uwierzytelnianie NT LanMan (NTLM).  
  
- W przypadku korzystania z zabezpieczeń na poziomie komunikatów uwierzytelnianie może zakończyć się niepowodzeniem, w zależności od trybu uwierzytelniania:  
  
- Jeśli używasz trybu, `spnego` a `AllowNtlm` atrybut jest ustawiony na `false` , uwierzytelnianie kończy się niepowodzeniem.  
  
- Jeśli używasz `spnego` trybu `AllowNtlm` , a atrybut jest ustawiony na `true` , uwierzytelnianie kończy się niepowodzeniem, jeśli główna nazwa użytkownika jest pusta, ale zostanie ukończona, jeśli nazwa SPN jest pusta.  
  
- W przypadku korzystania z protokołu Kerberos Direct (znanego również jako "z pojedynczym zrzutem") uwierzytelnianie kończy się niepowodzeniem.  
  
### <a name="use-the-identity-element-in-configuration"></a>Użyj \<identity> elementu w konfiguracji  
 Jeśli zmienisz typ poświadczeń klienta w powiązaniu poprzednio pokazanym na `Certificate` , wówczas wygenerowany kod WSDL zawiera certyfikat X. 509 z serializowanym algorytmem Base64 dla wartości tożsamości, jak pokazano w poniższym kodzie. Jest to wartość domyślna dla wszystkich typów poświadczeń klienta innych niż Windows.  

 Można zmienić wartość domyślnej tożsamości usługi lub zmienić typ tożsamości przy użyciu <`identity` elementu> w konfiguracji lub przez ustawienie tożsamości w kodzie. Poniższy kod konfiguracji ustawia tożsamość systemu nazw domen (DNS) z wartością `contoso.com` .  

### <a name="set-identity-programmatically"></a>Ustaw tożsamość programowo  
 Usługa nie musi jawnie określać tożsamości, ponieważ funkcja WCF automatycznie ją określa. Jednak funkcja WCF pozwala na określenie tożsamości w punkcie końcowym, w razie potrzeby. Poniższy kod dodaje nowy punkt końcowy usługi z określoną tożsamością DNS.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>Zobacz także

- [Instrukcje: tworzenie niestandardowego weryfikatora tożsamości klienta](how-to-create-a-custom-client-identity-verifier.md)
- [Uwierzytelnianie i tożsamość usług](../feature-details/service-identity-and-authentication.md)
