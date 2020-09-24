---
title: <remove>, element dla schemeSettings (ustawienia identyfikatora URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: 018a08693a39bb297bdaa468ba59d4bf097f6922
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151392"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="daadf-102">\<remove>, element dla schemeSettings (ustawienia identyfikatora URI)</span><span class="sxs-lookup"><span data-stu-id="daadf-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="daadf-103">Usuwa ustawienie schematu dla nazwy schematu.</span><span class="sxs-lookup"><span data-stu-id="daadf-103">Removes a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="daadf-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="daadf-104">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="daadf-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="daadf-105">Attributes and Elements</span></span>  

 <span data-ttu-id="daadf-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="daadf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="daadf-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="daadf-107">Attributes</span></span>  
  
|<span data-ttu-id="daadf-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="daadf-108">Attribute</span></span>|<span data-ttu-id="daadf-109">Opis</span><span class="sxs-lookup"><span data-stu-id="daadf-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="daadf-110">name</span><span class="sxs-lookup"><span data-stu-id="daadf-110">name</span></span>|<span data-ttu-id="daadf-111">Nazwa schematu, dla którego jest stosowane to ustawienie.</span><span class="sxs-lookup"><span data-stu-id="daadf-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="daadf-112">Jedyne obsługiwane wartości to Name = "http" i Name = "https".</span><span class="sxs-lookup"><span data-stu-id="daadf-112">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="daadf-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="daadf-113">Child Elements</span></span>  

 <span data-ttu-id="daadf-114">Brak.</span><span class="sxs-lookup"><span data-stu-id="daadf-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="daadf-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="daadf-115">Parent Elements</span></span>  
  
|<span data-ttu-id="daadf-116">Element</span><span class="sxs-lookup"><span data-stu-id="daadf-116">Element</span></span>|<span data-ttu-id="daadf-117">Opis</span><span class="sxs-lookup"><span data-stu-id="daadf-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="daadf-118">\<schemeSettings> — Element (ustawienia identyfikatora URI)</span><span class="sxs-lookup"><span data-stu-id="daadf-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="daadf-119">Określa, w jaki sposób <xref:System.Uri> będzie analizowana dla określonych schematów.</span><span class="sxs-lookup"><span data-stu-id="daadf-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="daadf-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="daadf-120">Remarks</span></span>  

 <span data-ttu-id="daadf-121">Domyślnie <xref:System.Uri?displayProperty=nameWithType> Klasa cofa ograniczniki ścieżki kodowanej procentowo przed wykonaniem kompresji ścieżki.</span><span class="sxs-lookup"><span data-stu-id="daadf-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="daadf-122">Ta implementacja została zaimplementowana jako mechanizm zabezpieczeń przed atakami podobnymi do następujących:</span><span class="sxs-lookup"><span data-stu-id="daadf-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="daadf-123">Jeśli ten identyfikator URI zostanie przesłany do modułów, które nie obsługują poprawnie znaków zakodowanych procentowo, może to spowodować wykonanie następującego polecenia przez serwer:</span><span class="sxs-lookup"><span data-stu-id="daadf-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="daadf-124">Z tego powodu <xref:System.Uri?displayProperty=nameWithType> Klasa najpierw cofa ograniczniki ścieżki, a następnie stosuje kompresję ścieżki.</span><span class="sxs-lookup"><span data-stu-id="daadf-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="daadf-125">Wynikiem przekazania złośliwego adresu URL powyżej do <xref:System.Uri?displayProperty=nameWithType> konstruktora klasy są następujące identyfikatory URI:</span><span class="sxs-lookup"><span data-stu-id="daadf-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="daadf-126">To zachowanie domyślne można zmodyfikować, aby nie wycofać ograniczników ścieżki zakodowanej procentowo przy użyciu opcji konfiguracji schemeSettings dla określonego schematu.</span><span class="sxs-lookup"><span data-stu-id="daadf-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="daadf-127">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="daadf-127">Configuration Files</span></span>  

 <span data-ttu-id="daadf-128">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="daadf-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="daadf-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="daadf-129">Example</span></span>  

 <span data-ttu-id="daadf-130">W poniższym przykładzie przedstawiono konfigurację używaną przez <xref:System.Uri> klasę, która usuwa wszystkie ustawienia schematu dla schematu http.</span><span class="sxs-lookup"><span data-stu-id="daadf-130">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="daadf-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="daadf-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="daadf-132">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="daadf-132">Network Settings Schema</span></span>](index.md)
