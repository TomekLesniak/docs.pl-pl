---
title: <generatePublisherEvidence> Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 506e7873fab8e41fce121587c22d85600a8b1760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158776"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence> Element

Określa, czy środowisko uruchomieniowe tworzy <xref:System.Security.Policy.Publisher> dowód dla zabezpieczeń dostępu kodu (CAS).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`enabled`|Atrybut wymagany.<br /><br /> Określa, czy środowisko uruchomieniowe tworzy <xref:System.Security.Policy.Publisher> dowód.|  
  
## <a name="enabled-attribute"></a>Atrybut włączony  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`false`|Nie tworzy <xref:System.Security.Policy.Publisher> dowodów.|  
|`true`|Tworzy <xref:System.Security.Policy.Publisher> dowód. Jest to opcja domyślna.|  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
|`runtime`|Zawiera informacje dotyczące opcji inicjowania środowiska uruchomieniowego.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> W .NET Framework 4 i nowszych ten element nie ma wpływu na czasy ładowania zestawu. Aby uzyskać więcej informacji, zobacz sekcję "uproszczenie zasad zabezpieczeń" w temacie [zmiany zabezpieczeń](/previous-versions/dotnet/framework/security/security-changes).  
  
 Środowisko uruchomieniowe języka wspólnego (CLR) próbuje zweryfikować podpis Authenticode w czasie ładowania, aby utworzyć <xref:System.Security.Policy.Publisher> dowód dla zestawu. Jednak domyślnie większość aplikacji nie potrzebuje <xref:System.Security.Policy.Publisher> dowodu. Standardowe zasady CAS nie bazują na <xref:System.Security.Policy.PublisherMembershipCondition> . Należy unikać niepotrzebnego kosztu uruchomienia związanego z weryfikacją podpisu wydawcy, chyba że aplikacja jest wykonywana na komputerze z niestandardowymi zasadami CAS lub nie spełnia wymagań dotyczących <xref:System.Security.Permissions.PublisherIdentityPermission> w środowisku częściowego zaufania. (Wymagania dotyczące uprawnień tożsamości zawsze powiodło się w środowisku pełnego zaufania).  
  
> [!NOTE]
> Zalecamy, aby usługi korzystały z `<generatePublisherEvidence>` elementu, aby zwiększyć wydajność uruchamiania.  Za pomocą tego elementu można także uniknąć opóźnień, które mogą spowodować przekroczenie limitu czasu i anulowanie uruchamiania usługi.  
  
## <a name="configuration-file"></a>Plik konfiguracji  

 Tego elementu można używać tylko w pliku konfiguracji aplikacji.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak użyć elementu, `<generatePublisherEvidence>` Aby wyłączyć sprawdzanie zasad wydawcy CAS dla aplikacji.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też

- [Schemat ustawień środowiska uruchomieniowego](index.md)
- [Schemat pliku konfiguracji](../index.md)
