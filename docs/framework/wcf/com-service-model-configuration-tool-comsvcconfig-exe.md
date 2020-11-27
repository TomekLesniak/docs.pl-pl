---
title: Narzędzie konfiguracji modelu usług COM+ (ComSvcConfig.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
ms.openlocfilehash: ee0fb5f08446b03485f97de0037e898415016fea
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295278"
---
# <a name="com-service-model-configuration-tool-comsvcconfigexe"></a>Narzędzie konfiguracji modelu usług COM+ (ComSvcConfig.exe)

Narzędzie wiersza polecenia konfiguracji modelu usług modelu COM+ (ComSvcConfig.exe) umożliwia konfigurowanie interfejsów COM+, które mają być udostępniane jako usługi sieci Web.  
  
## <a name="syntax"></a>Składnia  
  
```console  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Aby używać ComSvcConfig.exe, musisz być administratorem na komputerze lokalnym.  
  
 Narzędzie można znaleźć w następującej lokalizacji  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation \  
  
 Aby uzyskać więcej informacji na temat ComSvcConfig.exe, zobacz [How to: use a com+ Service Model Configuration Tool](./feature-details/how-to-use-the-com-service-model-configuration-tool.md).  
  
 W poniższej tabeli opisano tryby, które mogą być używane z ComSvcConfig.exe.  
  
|Opcja|Opis|  
|------------|-----------------|  
|`install`|Instaluje konfigurację interfejsu COM+ dla integracji modelu usług.<br /><br /> Krótka forma `/i` .|  
|`uninstall`|Odinstalowuje konfigurację interfejsu COM+ z integracji modelu usług.<br /><br /> Krótka forma `/u` .|  
|`list`|Wyświetla listę informacji dotyczących aplikacji i składników modelu COM+ z interfejsami skonfigurowanymi do integracji z modelem usług.<br /><br /> Krótka forma `/l` .|  
  
 W poniższej tabeli opisano flagi, które mogą być używane z ComSvcConfig.exe.  
  
|Opcja|Opis|  
|------------|-----------------|  
|`/application:` \<*ApplicationID* &#124; *ApplicationName*\>|Określa aplikację COM+ do skonfigurowania.<br /><br /> Krótka forma `/a` .|  
|`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\>|Określa składnik i interfejs modelu COM+, który zostanie skonfigurowany jako kontrakt dla usługi.<br /><br /> Krótka forma `/c` .<br /><br /> Chociaż symbol wieloznaczny ( \* ) może być używany podczas określania nazw składników i interfejsów, zalecamy, aby nie używać go, ponieważ mogą ujawniać interfejsy, które nie zostały zamierzone.|  
|`/hosting:` \<*complus*  &#124; *was*\>|Określa, czy ma być używany tryb hostingu modelu COM+ czy tryb hostingu w sieci Web.<br /><br /> Krótka forma `/h` .<br /><br /> Użycie trybu hostingu modelu COM+ wymaga jawnej aktywacji aplikacji modelu COM+. Użycie trybu hostingu w sieci Web umożliwia automatyczne Aktywowanie aplikacji COM+ w razie potrzeby. Jeśli aplikacja modelu COM+ jest aplikacją biblioteki, działa w procesie Internet Information Services (IIS). Jeśli aplikacja COM+ jest aplikacją serwerową, jest uruchamiana w procesie Dllhost.exe.|  
|`/webSite:` \<*WebsiteName*\>|Określa witrynę sieci Web do hostowania, gdy jest używany tryb hostingu w sieci Web (zobacz `/hosting` flagę).<br /><br /> Krótka forma `/w` .<br /><br /> Jeśli żadna witryna sieci Web nie zostanie określona, zostanie użyta domyślna witryna sieci Web.|  
|`/webDirectory:` \<*WebDirectoryName*\>|Określa katalog wirtualny do hostowania, gdy jest używany hosting w sieci Web (zobacz `/hosting` flagę).<br /><br /> Krótka forma `/d` .|  
|`/mex`|Dodaje punkt końcowy usługi wymiany metadanych (MEX) do domyślnej konfiguracji usługi w celu obsługi klientów, którzy chcą pobrać definicję kontraktu z usługi.<br /><br /> Krótka forma `/x` .|  
|`/id`|Wyświetla informacje o aplikacji, składniku i interfejsie jako identyfikatory.<br /><br /> Krótka forma `/k` .|  
|`/nologo`|Zapobiega wyświetlaniu logo przez ComSvcConfig.exe.<br /><br /> Krótka forma `/n` .|  
|`/verbose`|Oprócz napotkanych błędów są wyprowadzane wszystkie ostrzeżenia lub tekst informacyjny.<br /><br /> Krótka forma `/v` .|  
|`/help`|Wyświetla komunikat o użyciu.<br /><br /> Krótka forma `/?` .|  
|`/partial`|Generuje konfigurację usługi, gdy określony interfejs zawiera jeden lub więcej podpisów metod, które mogą być uwidocznione. W czasie inicjalizacji usługi zgodne metody są wyświetlane jako operacje w kontrakcie usługi, a niezgodne metody są ignorowane i nie są obecne w kontrakcie usługi.<br /><br /> W przypadku braku tej flagi narzędzie nie generuje konfiguracji usługi, gdy określony interfejs zawiera co najmniej jedną niezgodną metodę.|  
  
## <a name="examples"></a>Przykłady  
  
### <a name="description"></a>Opis  

 Poniższy przykład dodaje `IFinances` Interfejs `ItemOrders.IFinancial` składnika (z aplikacji OnlineStore com+) do zestawu interfejsów, które są udostępniane jako usługi sieci Web, przy użyciu trybu hostingu modelu com+. Wszystkie ostrzeżenia będą dodatkowo wykrytymi błędami.  
  
### <a name="code"></a>Kod  
  
```console  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### <a name="description"></a>Opis  

 Poniższy przykład dodaje `IStockLevels` Interfejs `ItemInventory.Warehouse` składnika (z aplikacji OnlineWarehouse com+) do zestawu interfejsów, które są udostępniane jako usługi sieci Web, przy użyciu trybu hostingu w sieci Web. Usługa sieci Web jest hostowana w sieci Web w katalogu wirtualnym OnlineWarehouse usług IIS.  
  
### <a name="code"></a>Kod  
  
```console  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### <a name="description"></a>Opis  

 Poniższy przykład usuwa `IFinances` Interfejs `ItemOrders.Financial` składnika (z aplikacji OnlineStore com+) z zestawu interfejsów, które są udostępniane jako usługi sieci Web.  
  
### <a name="code"></a>Kod  
  
```console  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### <a name="description"></a>Opis  

 W poniższym przykładzie przedstawiono aktualnie uwidocznione interfejsy obsługiwane przez model COM+ oraz odpowiednie adresy i szczegóły dotyczące powiązań dla aplikacji OnlineStore COM+ na komputerze lokalnym.  
  
### <a name="code"></a>Kod  
  
```console  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: używanie narzędzia konfiguracji modelu usług COM+](./feature-details/how-to-use-the-com-service-model-configuration-tool.md)
