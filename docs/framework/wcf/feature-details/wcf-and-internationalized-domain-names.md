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
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="31df0-102">Architektura WCF i międzynarodowe nazwy domen</span><span class="sxs-lookup"><span data-stu-id="31df0-102">WCF and Internationalized Domain Names</span></span>

<span data-ttu-id="31df0-103">Dodano obsługę usług WCF z międzynarodowymi nazwami domen (IDN).</span><span class="sxs-lookup"><span data-stu-id="31df0-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="31df0-104">Międzynarodowa nazwa domeny to nazwa domeny, która zawiera znaki inne niż ASCII.</span><span class="sxs-lookup"><span data-stu-id="31df0-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="31df0-105">Ta obsługa obejmuje zarówno możliwość hostowania usługi WCF przy użyciu nazwy IDN, jak i klienta WCF, aby komunikować się z usługą sieci Web przy użyciu nazwy IDN.</span><span class="sxs-lookup"><span data-stu-id="31df0-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="31df0-106">System. URI i IDN</span><span class="sxs-lookup"><span data-stu-id="31df0-106">System.Uri and IDN</span></span>  

 <span data-ttu-id="31df0-107"><xref:System.Uri> ma dwie właściwości <xref:System.Uri.Host%2A> i <xref:System.Uri.DnsSafeHost%2A> .</span><span class="sxs-lookup"><span data-stu-id="31df0-107"><xref:System.Uri> has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="31df0-108">Te właściwości zawierają wartości Unicode lub formacie Punycode w zależności od ustawień konfiguracji IDN.</span><span class="sxs-lookup"><span data-stu-id="31df0-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="31df0-109">IDN jest włączona w pliku konfiguracji aplikacji przy użyciu następującego kodu XML</span><span class="sxs-lookup"><span data-stu-id="31df0-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="31df0-110">\<idn>Element zawiera atrybut Enabled, który można ustawić na jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="31df0-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1. <span data-ttu-id="31df0-111">Dawaj</span><span class="sxs-lookup"><span data-stu-id="31df0-111">"None"</span></span>  
  
2. <span data-ttu-id="31df0-112">"AllExceptIntranet"</span><span class="sxs-lookup"><span data-stu-id="31df0-112">"AllExceptIntranet"</span></span>  
  
3. <span data-ttu-id="31df0-113">Całą</span><span class="sxs-lookup"><span data-stu-id="31df0-113">"All"</span></span>  
  
 <span data-ttu-id="31df0-114">Gdy ustawienie IDN ma wartość "none", nie są wykonywane żadne konwersje według identyfikatora URI. host lub URI. DnsSafeHost.</span><span class="sxs-lookup"><span data-stu-id="31df0-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="31df0-115">Gdy ustawienie IDN ma wartość "wszystkie", identyfikator URI. Host pozostanie w formacie Unicode i URI. DnsSafeHost jest konwertowany na formacie Punycode.</span><span class="sxs-lookup"><span data-stu-id="31df0-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="31df0-116">Gdy ustawienie IDN ma wartość "AllExceptIntranet", identyfikator URI. DnsSafeHost jest konwertowany na formacie Punycode dla adresów internetowych i pozostaje Unicode dla adresów intranetowych.</span><span class="sxs-lookup"><span data-stu-id="31df0-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="31df0-117">To ustawienie jest ważne w przypadku poprawnego rozpoznawania nazw DNS.</span><span class="sxs-lookup"><span data-stu-id="31df0-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="31df0-118">Należy pamiętać, że to ustawienie nie jest wymagane do skonfigurowania dla systemu Windows 8 i nowszych wersji.</span><span class="sxs-lookup"><span data-stu-id="31df0-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="31df0-119">Nigdy nie należy nakodować adresu przy użyciu formacie Punycode.</span><span class="sxs-lookup"><span data-stu-id="31df0-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="31df0-120">Program WCF przekonwertuje go na podstawie stosowanych ustawień konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="31df0-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="31df0-121">Podczas dodawania znaków Unicode do applicationHost.exe.config Zapisz plik przy użyciu kodowania UTF-8.</span><span class="sxs-lookup"><span data-stu-id="31df0-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31df0-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="31df0-122">See also</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
