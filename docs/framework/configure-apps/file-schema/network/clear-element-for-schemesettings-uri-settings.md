---
title: <clear>, element dla schemeSettings (ustawienia identyfikatora URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 17069a56a8647871e98d70826a97a8fe407a0887
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205064"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="56a7a-102">\<clear>, element dla schemeSettings (ustawienia identyfikatora URI)</span><span class="sxs-lookup"><span data-stu-id="56a7a-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="56a7a-103">Czyści wszystkie istniejące ustawienia schematu.</span><span class="sxs-lookup"><span data-stu-id="56a7a-103">Clears all existing scheme settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="56a7a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="56a7a-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56a7a-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="56a7a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="56a7a-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="56a7a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56a7a-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="56a7a-107">Attributes</span></span>  

 <span data-ttu-id="56a7a-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="56a7a-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="56a7a-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="56a7a-109">Child Elements</span></span>  

 <span data-ttu-id="56a7a-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="56a7a-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56a7a-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="56a7a-111">Parent Elements</span></span>  
  
|<span data-ttu-id="56a7a-112">Element</span><span class="sxs-lookup"><span data-stu-id="56a7a-112">Element</span></span>|<span data-ttu-id="56a7a-113">Opis</span><span class="sxs-lookup"><span data-stu-id="56a7a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56a7a-114">\<schemeSettings> — Element (ustawienia identyfikatora URI)</span><span class="sxs-lookup"><span data-stu-id="56a7a-114">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="56a7a-115">Określa, w jaki sposób <xref:System.Uri> będzie analizowana dla określonych schematów.</span><span class="sxs-lookup"><span data-stu-id="56a7a-115">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56a7a-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="56a7a-116">Remarks</span></span>  

 <span data-ttu-id="56a7a-117">Domyślnie <xref:System.Uri?displayProperty=nameWithType> Klasa cofa ograniczniki ścieżki kodowanej procentowo przed wykonaniem kompresji ścieżki.</span><span class="sxs-lookup"><span data-stu-id="56a7a-117">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="56a7a-118">Ta implementacja została zaimplementowana jako mechanizm zabezpieczeń przed atakami podobnymi do następujących:</span><span class="sxs-lookup"><span data-stu-id="56a7a-118">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="56a7a-119">Jeśli ten identyfikator URI zostanie przesłany do modułów, które nie obsługują poprawnie znaków zakodowanych procentowo, może to spowodować wykonanie następującego polecenia przez serwer:</span><span class="sxs-lookup"><span data-stu-id="56a7a-119">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="56a7a-120">Z tego powodu <xref:System.Uri?displayProperty=nameWithType> Klasa najpierw cofa ograniczniki ścieżki, a następnie stosuje kompresję ścieżki.</span><span class="sxs-lookup"><span data-stu-id="56a7a-120">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="56a7a-121">Wynikiem przekazania złośliwego adresu URL powyżej do <xref:System.Uri?displayProperty=nameWithType> konstruktora klasy są następujące identyfikatory URI:</span><span class="sxs-lookup"><span data-stu-id="56a7a-121">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="56a7a-122">To zachowanie domyślne można zmodyfikować, aby nie wycofać ograniczników ścieżki zakodowanej procentowo przy użyciu opcji konfiguracji schemeSettings dla określonego schematu.</span><span class="sxs-lookup"><span data-stu-id="56a7a-122">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="56a7a-123">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="56a7a-123">Configuration Files</span></span>  

 <span data-ttu-id="56a7a-124">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="56a7a-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56a7a-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="56a7a-125">Example</span></span>  

 <span data-ttu-id="56a7a-126">W poniższym przykładzie przedstawiono konfigurację używaną przez <xref:System.Uri> klasę, która czyści wszystkie ustawienia schematu, a następnie dodaje obsługę nieprawidłowych ograniczników Path (procentowo) dla schematu http.</span><span class="sxs-lookup"><span data-stu-id="56a7a-126">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56a7a-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="56a7a-127">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="56a7a-128">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="56a7a-128">Network Settings Schema</span></span>](index.md)
