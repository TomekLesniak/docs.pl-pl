---
title: Architektura WCF i międzynarodowe nazwy domen
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: 2d93bbb0c284c2227a4d03acf1ad9a801df57bd8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281992"
---
# <a name="wcf-and-internationalized-domain-names"></a>Architektura WCF i międzynarodowe nazwy domen

Dodano obsługę usług WCF z międzynarodowymi nazwami domen (IDN). Międzynarodowa nazwa domeny to nazwa domeny, która zawiera znaki inne niż ASCII. Ta obsługa obejmuje zarówno możliwość hostowania usługi WCF przy użyciu nazwy IDN, jak i klienta WCF, aby komunikować się z usługą sieci Web przy użyciu nazwy IDN.  
  
## <a name="systemuri-and-idn"></a>System. URI i IDN  

 <xref:System.Uri> ma dwie właściwości <xref:System.Uri.Host%2A> i <xref:System.Uri.DnsSafeHost%2A> . Te właściwości zawierają wartości Unicode lub formacie Punycode w zależności od ustawień konfiguracji IDN.  
  
 IDN jest włączona w pliku konfiguracji aplikacji przy użyciu następującego kodu XML  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 \<idn>Element zawiera atrybut Enabled, który można ustawić na jedną z następujących wartości:  
  
1. Dawaj  
  
2. "AllExceptIntranet"  
  
3. Całą  
  
 Gdy ustawienie IDN ma wartość "none", nie są wykonywane żadne konwersje według identyfikatora URI. host lub URI. DnsSafeHost. Gdy ustawienie IDN ma wartość "wszystkie", identyfikator URI. Host pozostanie w formacie Unicode i URI. DnsSafeHost jest konwertowany na formacie Punycode. Gdy ustawienie IDN ma wartość "AllExceptIntranet", identyfikator URI. DnsSafeHost jest konwertowany na formacie Punycode dla adresów internetowych i pozostaje Unicode dla adresów intranetowych. To ustawienie jest ważne w przypadku poprawnego rozpoznawania nazw DNS. Należy pamiętać, że to ustawienie nie jest wymagane do skonfigurowania dla systemu Windows 8 i nowszych wersji.  
  
> [!WARNING]
> Nigdy nie należy nakodować adresu przy użyciu formacie Punycode. Program WCF przekonwertuje go na podstawie stosowanych ustawień konfiguracji.  
  
> [!WARNING]
> Podczas dodawania znaków Unicode do applicationHost.exe.config Zapisz plik przy użyciu kodowania UTF-8.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Uri?displayProperty=nameWithType>
