---
title: <uri>, element (ustawienia identyfikatora URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 2f22d70407d10dbb38f0cb8d3a8ac74ff3fe8763
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190205"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="19dd0-102">\<uri>, element (ustawienia identyfikatora URI)</span><span class="sxs-lookup"><span data-stu-id="19dd0-102">\<uri> Element (Uri Settings)</span></span>

<span data-ttu-id="19dd0-103">Zawiera ustawienia, które określają, w jaki sposób .NET Framework obsługuje adresy sieci Web wyrażone przy użyciu Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="19dd0-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a><span data-ttu-id="19dd0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="19dd0-104">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19dd0-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="19dd0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="19dd0-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="19dd0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19dd0-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="19dd0-107">Attributes</span></span>  

 <span data-ttu-id="19dd0-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="19dd0-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="19dd0-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="19dd0-109">Child Elements</span></span>  
  
|<span data-ttu-id="19dd0-110">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="19dd0-110">**Element**</span></span>|<span data-ttu-id="19dd0-111">**Opis**</span><span class="sxs-lookup"><span data-stu-id="19dd0-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="19dd0-112">IDN</span><span class="sxs-lookup"><span data-stu-id="19dd0-112">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="19dd0-113">Określa, czy do nazw domen są stosowane analizowanie międzynarodowych nazw domen (IDN).</span><span class="sxs-lookup"><span data-stu-id="19dd0-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="19dd0-114">iriParsing</span><span class="sxs-lookup"><span data-stu-id="19dd0-114">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="19dd0-115">Określa, czy ma zostać zastosowana Analiza IRI (International Resource Identifier) <xref:System.Uri> i czy mają być stosowane IRI reguły analizy.</span><span class="sxs-lookup"><span data-stu-id="19dd0-115">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="19dd0-116">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="19dd0-116">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="19dd0-117">Określa, w jaki sposób <xref:System.Uri> będzie analizowana dla określonych schematów.</span><span class="sxs-lookup"><span data-stu-id="19dd0-117">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19dd0-118">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="19dd0-118">Parent Elements</span></span>  
  
|<span data-ttu-id="19dd0-119">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="19dd0-119">**Element**</span></span>|<span data-ttu-id="19dd0-120">**Opis**</span><span class="sxs-lookup"><span data-stu-id="19dd0-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="19dd0-121">skonfigurować</span><span class="sxs-lookup"><span data-stu-id="19dd0-121">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="19dd0-122">Zawiera ustawienia dla wszystkich przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="19dd0-122">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19dd0-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="19dd0-123">Remarks</span></span>  

 <span data-ttu-id="19dd0-124">`uri`Element zawiera ustawienia dla elementów członkowskich <xref:System.Uri> klasy używanej przez klasy w <xref:System.Net> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="19dd0-124">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="19dd0-125">Ustawienia umożliwiają skonfigurowanie obsługi IRI i IDN.</span><span class="sxs-lookup"><span data-stu-id="19dd0-125">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19dd0-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="19dd0-126">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="19dd0-127">Opis</span><span class="sxs-lookup"><span data-stu-id="19dd0-127">Description</span></span>  

 <span data-ttu-id="19dd0-128">W poniższym przykładzie przedstawiono konfigurację używaną przez <xref:System.Uri> klasę do obsługi analizy IRI i nazw IDN.</span><span class="sxs-lookup"><span data-stu-id="19dd0-128">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="19dd0-129">W przykładzie zostanie również wyczyszczone wszystkie ustawienia schematu, a następnie dodano obsługę ograniczników ścieżek o wartości procentowo zakodowanych w schemacie protokołu HTTP.</span><span class="sxs-lookup"><span data-stu-id="19dd0-129">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="19dd0-130">Kod</span><span class="sxs-lookup"><span data-stu-id="19dd0-130">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19dd0-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="19dd0-131">See also</span></span>

- [<span data-ttu-id="19dd0-132">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="19dd0-132">Network Settings Schema</span></span>](index.md)
