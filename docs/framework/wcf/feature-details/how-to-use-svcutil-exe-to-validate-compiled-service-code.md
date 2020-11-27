---
title: 'Instrukcje: weryfikacja skompilowanego kodu usługi za pomocą programu Svcutil.exe'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 21cd0c13cea764efb60b7b94b699e9a483269da8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280666"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a>Instrukcje: weryfikacja skompilowanego kodu usługi za pomocą programu Svcutil.exe

Za pomocą narzędzia do obsługi [metadanych ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) można wykrywać błędy w implementacjach i konfiguracjach usług bez konieczności obsługiwania usługi.  
  
### <a name="to-validate-a-service"></a>Aby sprawdzić poprawność usługi  
  
1. Skompiluj usługę do pliku wykonywalnego i jednego lub więcej zestawów zależnych.  
  
2. Otwórz wiersz polecenia zestawu SDK  
  
3. W wierszu polecenia Uruchom narzędzie Svcutil.exe w następującym formacie. Aby uzyskać więcej informacji na temat różnych parametrów, zobacz Validationsection usługi w temacie [Narzędzie metadanych ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) .  
  
    ```console
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     Musisz użyć opcji, `/serviceName` Aby wskazać nazwę konfiguracji usługi, którą chcesz zweryfikować.  
  
     `assemblyPath`Argument określa ścieżkę do pliku wykonywalnego usługi i co najmniej jeden zestaw zawierający typy usługi do zweryfikowania. Zestaw wykonywalny musi mieć skojarzony plik konfiguracji, aby zapewnić konfigurację usługi. Możesz użyć standardowych symboli wieloznacznych wiersza polecenia, aby udostępnić wiele zestawów.  
  
## <a name="example"></a>Przykład  

 Następujące polecenie usługi serviceservicename zaimplementowane w myServiceHost.exe pliku wykonywalnego.  Plik konfiguracji usługi (myServiceHost.exe.config) jest ładowany automatycznie.  
  
```console  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a>Zobacz też

- [Narzędzie do obsługi metadanych elementu ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
