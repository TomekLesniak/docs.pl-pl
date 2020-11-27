---
title: 'Instrukcje: eksportowanie metadanych ze skompilowanego kodu usługi za pomocą programu Svcutil.exe'
ms.date: 03/30/2017
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
ms.openlocfilehash: f60d0c9ad3f6fc4e9596d466b5eabdaab0f4822f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280614"
---
# <a name="how-to-use-svcutilexe-to-export-metadata-from-compiled-service-code"></a>Instrukcje: eksportowanie metadanych ze skompilowanego kodu usługi za pomocą programu Svcutil.exe

Svcutil.exe mogą eksportować metadane usług, kontraktów i typów danych w skompilowanych zestawach w następujący sposób:  
  
- Aby wyeksportować metadane dla wszystkich skompilowanych kontraktów usług dla zestawu zestawów przy użyciu Svcutil.exe, określ zestawy jako parametry wejściowe. Jest to zachowanie domyślne.  
  
- Aby wyeksportować metadane dla skompilowanej usługi przy użyciu Svcutil.exe, określ zestaw usług lub zestawy jako parametry wejściowe. Należy użyć opcji, `/serviceName` Aby wskazać nazwę konfiguracji usługi, która ma zostać wyeksportowana. Svcutil.exe automatycznie ładuje plik konfiguracyjny dla określonego zestawu wykonywalnego.  
  
- Aby wyeksportować wszystkie typy kontraktów danych w zestawie zestawów, użyj `/dataContractOnly` opcji.  
  
> [!NOTE]
> Użyj `/reference` opcji, aby określić ścieżki do wszystkich zestawów zależnych.  
  
### <a name="to-export-metadata-for-compiled-service-contracts"></a>Aby wyeksportować metadane dla skompilowanych kontraktów usługi  
  
1. Kompiluj implementacje kontraktu usługi do co najmniej jednej biblioteki klas. 1  
  
2. Uruchom Svcutil.exe w skompilowanych zestawach.  
  
    > [!NOTE]
    > Może być konieczne użycie przełącznika, `/reference` Aby określić ścieżkę pliku do wszystkich zestawów zależnych.  
  
    ```console
    svcutil.exe Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-a-compiled-service"></a>Aby wyeksportować metadane dla skompilowanej usługi  
  
1. Kompiluj implementację usługi do zestawu wykonywalnego.  
  
2. Utwórz plik konfiguracji dla pliku wykonywalnego usługi i Dodaj konfigurację usługi.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="MyService" >  
            <endpoint address="finder" contract="IPeopleFinder" binding="wsHttpBinding" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
3. Uruchom Svcutil.exe w skompilowanym pliku wykonywalnym usługi przy użyciu `/serviceName` przełącznika, aby określić nazwę konfiguracji usługi.  
  
    > [!NOTE]
    > Może być konieczne użycie przełącznika, `/reference` Aby określić ścieżkę pliku do wszystkich zestawów zależnych.  
  
    ```console  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-compiled-data-contracts"></a>Aby wyeksportować metadane dla skompilowanych kontraktów danych  
  
1. Kompiluj implementacje kontraktu danych do co najmniej jednej biblioteki klas.  
  
2. Uruchom Svcutil.exe na skompilowanych zestawach przy użyciu `/dataContract` przełącznika, aby określić, że mają być generowane tylko metadane dla kontraktów danych.  
  
    > [!NOTE]
    > Może być konieczne użycie przełącznika, `/reference` Aby określić ścieżkę pliku do wszystkich zestawów zależnych.  
  
    ```console  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie pokazano, jak generować metadane dla prostej implementacji usługi i konfiguracji.  
  
 Aby wyeksportować metadane dla kontraktu usługi.  
  
```console  
svcutil.exe Contracts.dll  
```  
  
 Eksportowanie metadanych dla kontraktów danych.  
  
```console  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 Aby wyeksportować metadane dla implementacji usługi.  
  
```console  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 `<path>`Jest to ścieżka do Contracts.dll.  
  
```csharp
// The following service contract and data contracts are compiled into
// Contracts.dll.  
[ServiceContract(ConfigurationName="IPeopleFinder")]  
public interface IPersonFinder  
{  
    [OperationContract]  
    Address GetAddress(Person s);  
}  
  
[DataContract]  
public class Person  
{  
    [DataMember]  
    public string firstName;  
    [DataMember]  
    public string lastName;  
    [DataMember]  
    public int age;  
}  
  
[DataContract]  
public class Address  
{  
    [DataMember]  
    public string city;  
    [DataMember]  
    public string state;  
    [DataMember]  
    public string street;  
    [DataMember]  
    public int zipCode;  
    [DataMember]  
    public Person person;  
}  
```

```csharp
// The following service implementation is compiled into Service.exe.
// This service uses the contracts specified in Contracts.dll.  
[ServiceBehavior(ConfigurationName = "MyService")]  
public class MyService : IPersonFinder  
{  
    public Address GetAddress(Person person)  
    {  
        Address address = new Address();  
        address.person = person;  
        return address;  
    }  
}  
```

```xml  
<!-- The following is the configuration file for Service.exe. -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="MyService">  
         <endpoint  address="finder"  
                    binding="basicHttpBinding"  
                    contract="IPeopleFinder"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też

- [Narzędzie do obsługi metadanych elementu ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Eksportowanie i importowanie metadanych](exporting-and-importing-metadata.md)
