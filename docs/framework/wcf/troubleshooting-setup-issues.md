---
title: Rozwiązywanie problemów dotyczących konfiguracji
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: fb687e9975ab9ac763030f10d54c7744dc02c9e0
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720455"
---
# <a name="troubleshoot-setup-issues"></a>Rozwiązywanie problemów z instalacją

W tym artykule opisano sposób rozwiązywania problemów z instalacją programu Windows Communication Foundation (WCF).  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Niektóre Windows Communication Foundation klucze rejestru nie są naprawiane przez wykonanie operacji naprawy MSI na .NET Framework 3,0  
 W przypadku usunięcia dowolnego z następujących kluczy rejestru:  
  
- HKEY_LOCAL_MACHINE \SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE \SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE \SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE \SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE \SYSTEM\CurrentControlSet\Services\MSDTC 3.0.0.0 Bridge  
  
 Klucze nie są ponownie tworzone w przypadku uruchomienia naprawy przy użyciu Instalatora .NET Framework 3,0 uruchomionego z apletu **Dodaj/Usuń programy** w **Panelu sterowania**. Aby poprawnie utworzyć te klucze, użytkownik musi odinstalować i ponownie zainstalować .NET Framework 3,0.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-wmi-provider"></a>Usługa WMI blokuje instalację dostawcy usługi WMI

 Uszkodzenie usługi WMI może blokować instalację dostawcy usługi WMI Windows Communication Foundation podczas instalowania pakietu .NET Framework 3,0. Podczas instalacji Instalator Windows Communication Foundation nie może zarejestrować pliku WCF *. MOF* przy użyciu składnika *mofcomp.exe* . Poniżej znajduje się lista objawów:  
  
1. Instalacja .NET Framework 3,0 zakończyła się pomyślnie, ale dostawca WMI WCF nie jest zarejestrowany.  
  
2. W dzienniku zdarzeń aplikacji pojawia się zdarzenie błędu, które odwołuje się do problemów z rejestrowaniem dostawcy WMI dla programu WCF lub uruchamiania mofcomp.exe.  
  
3. Plik dziennika Instalatora o nazwie dd_wcf_retCA * w katalogu% Temp% użytkownika zawiera odwołania do błędu rejestracji dostawcy WMI usługi WCF.  
  
4. Wyjątek, taki jak jeden z poniższych, może zostać wyświetlony w dzienniku zdarzeń lub w pliku dziennika śledzenia konfiguracji:  
  
     ServiceModelReg [11:09:59:046]: System. ApplicationException: nieoczekiwany wynik 3 wykonywania E:\WINDOWS\system32\wbem\mofcomp.exe przy użyciu "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"  
  
     lub:  
  
     ServiceModelReg [07:19:33:843]: System. TypeInitializationException: inicjator typu dla elementu "System. Management. ManagementPath" zgłosił wyjątek. ---> system. Runtime. InteropServices. COMException (0x80040154): pobieranie fabryki klas COM dla składnika o identyfikatorze CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} nie powiodło się z powodu następującego błędu: 80040154.  
  
     lub:  
  
     ServiceModelReg [07:19:32:750]: System. IO. FileNotFoundException: nie można załadować pliku lub zestawu "C:\WINDOWS\system32\wbem\mofcomp.exe" lub jednej z jego zależności. W systemie nie można odnaleźć określonego pliku.  
  
     Nazwa pliku: "C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Należy postępować zgodnie z poniższymi krokami, aby rozwiązać opisany wcześniej problem.  
  
1. Uruchom Narzędzie diagnostyczne WMI, aby naprawić usługę WMI. Aby uzyskać więcej informacji na temat korzystania z tego narzędzia, zobacz [Narzędzie diagnostyczne WMI](/previous-versions/tn-archive/ff404265(v%3dmsdn.10)).  
  
 Napraw instalację .NET Framework 3,0 przy użyciu apletu **Dodaj/Usuń programy** znajdującego się w **Panelu sterowania**lub odinstaluj/ponownie zainstaluj .NET Framework 3,0.  
  
## <a name="repair-net-framework-30-after-net-framework-35-installation"></a>Naprawa .NET Framework 3,0 po zainstalowaniu .NET Framework 3,5

 W przypadku naprawienia .NET Framework 3,0 po zainstalowaniu .NET Framework 3,5 elementy konfiguracji wprowadzone przez .NET Framework 3,5 w *machine.config* zostaną usunięte. Jednak plik *web.config* pozostaje nienaruszony. Obejście polega na naprawieniu .NET Framework 3,5 po tym za pośrednictwem protokołu ARP lub użyciu [narzędzia rejestracji usługi przepływu pracy (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) z `/c` przełącznikiem.  
  
 [Narzędzie rejestracji usługi przepływu pracy (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) można znaleźć pod adresem%windir%\Microsoft.NET\framework\v3.5\ lub%windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Skonfiguruj prawidłowo usługi IIS dla programu WCF/WF webhost po zainstalowaniu .NET Framework 3,5  
 W przypadku instalacji .NET Framework 3,5 nie można skonfigurować dodatkowych ustawień konfiguracji usług IIS związanych z WCF, rejestruje błąd w dzienniku instalacji i kontynuuje działanie. Każda próba uruchomienia aplikacji obiektów WorkflowService zakończy się niepowodzeniem, ponieważ brakuje wymaganych ustawień konfiguracji. Na przykład ładowanie usługi xoml lub reguł może zakończyć się niepowodzeniem.  
  
 Aby obejść ten problem, użyj [narzędzia rejestracji usługi przepływu pracy (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) z `/c` przełącznikiem, aby prawidłowo skonfigurować mapy skryptów usług IIS na tym komputerze. [Narzędzie rejestracji usługi przepływu pracy (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) można znaleźć pod adresem%windir%\Microsoft.NET\framework\v3.5\ lub%windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule"></a>Nie można załadować typu "System. ServiceModel. Activation. HttpModule"

**Nie można załadować typu "System. ServiceModel. Activation. HttpModule" z zestawu "System. ServiceModel, Version 3.0.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089"**

 Ten błąd występuje, gdy zainstalowano .NET Framework 4, a następnie Aktywacja HTTP WCF jest włączona. Aby rozwiązać ten problem, uruchom następujące polecenie z wewnątrz wiersz polecenia dla deweloperów dla programu Visual Studio:  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje dotyczące konfiguracji](./samples/set-up-instructions.md)
