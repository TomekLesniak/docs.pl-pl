---
title: <add>, element dla schemeSettings (ustawienia identyfikatora URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 55fcba41d4dabf8937ebaa11235e9309bcb57952
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149464"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="b00e4-102">\<add>, element dla schemeSettings (ustawienia identyfikatora URI)</span><span class="sxs-lookup"><span data-stu-id="b00e4-102">\<add> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="b00e4-103">Dodaje ustawienie schematu dla nazwy schematu.</span><span class="sxs-lookup"><span data-stu-id="b00e4-103">Adds a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="b00e4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b00e4-104">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b00e4-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="b00e4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b00e4-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="b00e4-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b00e4-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="b00e4-107">Attributes</span></span>  
  
|<span data-ttu-id="b00e4-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="b00e4-108">Attribute</span></span>|<span data-ttu-id="b00e4-109">Opis</span><span class="sxs-lookup"><span data-stu-id="b00e4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b00e4-110">name</span><span class="sxs-lookup"><span data-stu-id="b00e4-110">name</span></span>|<span data-ttu-id="b00e4-111">Nazwa schematu, dla którego jest stosowane to ustawienie.</span><span class="sxs-lookup"><span data-stu-id="b00e4-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="b00e4-112">Jedyne obsługiwane wartości to Name = "http" i Name = "https".</span><span class="sxs-lookup"><span data-stu-id="b00e4-112">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="b00e4-113">{Nazwa atrybutu} Przypisane</span><span class="sxs-lookup"><span data-stu-id="b00e4-113">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="b00e4-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="b00e4-114">Value</span></span>|<span data-ttu-id="b00e4-115">Opis</span><span class="sxs-lookup"><span data-stu-id="b00e4-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b00e4-116">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="b00e4-116">genericUriParserOptions</span></span>|<span data-ttu-id="b00e4-117">Opcje parsera dla tego schematu.</span><span class="sxs-lookup"><span data-stu-id="b00e4-117">The parser options for this scheme.</span></span> <span data-ttu-id="b00e4-118">Jedyna obsługiwana wartość to genericUriParserOptions = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="b00e4-118">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b00e4-119">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="b00e4-119">Child Elements</span></span>  

 <span data-ttu-id="b00e4-120">Brak</span><span class="sxs-lookup"><span data-stu-id="b00e4-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b00e4-121">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="b00e4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b00e4-122">Element</span><span class="sxs-lookup"><span data-stu-id="b00e4-122">Element</span></span>|<span data-ttu-id="b00e4-123">Opis</span><span class="sxs-lookup"><span data-stu-id="b00e4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b00e4-124">\<schemeSettings> — Element (ustawienia identyfikatora URI)</span><span class="sxs-lookup"><span data-stu-id="b00e4-124">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="b00e4-125">Określa, w jaki sposób <xref:System.Uri> będzie analizowana dla określonych schematów.</span><span class="sxs-lookup"><span data-stu-id="b00e4-125">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b00e4-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b00e4-126">Remarks</span></span>  

 <span data-ttu-id="b00e4-127">Domyślnie <xref:System.Uri?displayProperty=nameWithType> Klasa cofa ograniczniki ścieżki kodowanej procentowo przed wykonaniem kompresji ścieżki.</span><span class="sxs-lookup"><span data-stu-id="b00e4-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="b00e4-128">Ta implementacja została zaimplementowana jako mechanizm zabezpieczeń przed atakami podobnymi do następujących:</span><span class="sxs-lookup"><span data-stu-id="b00e4-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b00e4-129">Jeśli ten identyfikator URI zostanie przesłany do modułów, które nie obsługują poprawnie znaków zakodowanych procentowo, może to spowodować wykonanie następującego polecenia przez serwer:</span><span class="sxs-lookup"><span data-stu-id="b00e4-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="b00e4-130">Z tego powodu <xref:System.Uri?displayProperty=nameWithType> Klasa najpierw cofa ograniczniki ścieżki, a następnie stosuje kompresję ścieżki.</span><span class="sxs-lookup"><span data-stu-id="b00e4-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="b00e4-131">Wynikiem przekazania złośliwego adresu URL powyżej do <xref:System.Uri?displayProperty=nameWithType> konstruktora klasy są następujące identyfikatory URI:</span><span class="sxs-lookup"><span data-stu-id="b00e4-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b00e4-132">To zachowanie domyślne można zmodyfikować, aby nie wycofać ograniczników ścieżki zakodowanej procentowo przy użyciu opcji konfiguracji schemeSettings dla określonego schematu.</span><span class="sxs-lookup"><span data-stu-id="b00e4-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b00e4-133">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="b00e4-133">Configuration Files</span></span>  

 <span data-ttu-id="b00e4-134">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b00e4-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b00e4-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="b00e4-135">Example</span></span>  

 <span data-ttu-id="b00e4-136">W poniższym przykładzie przedstawiono konfigurację używaną przez <xref:System.Uri> klasę do obsługi nieprawidłowych ograniczników ścieżki w kodzie procentowym dla schematu http.</span><span class="sxs-lookup"><span data-stu-id="b00e4-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b00e4-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b00e4-137">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="b00e4-138">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="b00e4-138">Network Settings Schema</span></span>](index.md)
