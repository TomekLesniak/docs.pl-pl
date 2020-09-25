---
title: <httpWebRequest>, element (ustawienia sieci)
description: <httpWebRequest>Element ustawień sieci dostosowuje parametry żądania sieci Web w .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 86960a33d0924013e2bfbfa743eab372181033b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195431"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="b29ae-103">\<httpWebRequest>, element (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="b29ae-103">\<httpWebRequest> Element (Network Settings)</span></span>

<span data-ttu-id="b29ae-104">Dostosowuje parametry żądania sieci Web.</span><span class="sxs-lookup"><span data-stu-id="b29ae-104">Customizes Web request parameters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a><span data-ttu-id="b29ae-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b29ae-105">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b29ae-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="b29ae-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b29ae-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="b29ae-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b29ae-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="b29ae-108">Attributes</span></span>  
  
|<span data-ttu-id="b29ae-109">**Atrybut**</span><span class="sxs-lookup"><span data-stu-id="b29ae-109">**Attribute**</span></span>|<span data-ttu-id="b29ae-110">**Opis**</span><span class="sxs-lookup"><span data-stu-id="b29ae-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="b29ae-111">Określa maksymalną długość nagłówka odpowiedzi w kilobajtach.</span><span class="sxs-lookup"><span data-stu-id="b29ae-111">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="b29ae-112">Wartość domyślna to 64.</span><span class="sxs-lookup"><span data-stu-id="b29ae-112">The default is 64.</span></span> <span data-ttu-id="b29ae-113">Wartość-1 oznacza, że w nagłówkach odpowiedzi nie zostanie wprowadzony limit rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="b29ae-113">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="b29ae-114">Określa maksymalną długość odpowiedzi na błąd w kilobajtach.</span><span class="sxs-lookup"><span data-stu-id="b29ae-114">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="b29ae-115">Wartość domyślna to 64.</span><span class="sxs-lookup"><span data-stu-id="b29ae-115">The default is 64.</span></span> <span data-ttu-id="b29ae-116">Wartość-1 oznacza, że w odpowiedzi na błąd nie zostanie wprowadzony limit rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="b29ae-116">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="b29ae-117">Określa maksymalną długość przekazywania w odpowiedzi na nieautoryzowany kod błędu w bajtach.</span><span class="sxs-lookup"><span data-stu-id="b29ae-117">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="b29ae-118">Wartość domyślna to-1.</span><span class="sxs-lookup"><span data-stu-id="b29ae-118">The default is -1.</span></span> <span data-ttu-id="b29ae-119">Wartość-1 oznacza, że żaden limit rozmiaru nie zostanie nałożony na przekazywanie.</span><span class="sxs-lookup"><span data-stu-id="b29ae-119">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="b29ae-120">Określa, czy jest włączone analizowanie niebezpiecznego nagłówka.</span><span class="sxs-lookup"><span data-stu-id="b29ae-120">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="b29ae-121">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="b29ae-121">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b29ae-122">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="b29ae-122">Child Elements</span></span>  

 <span data-ttu-id="b29ae-123">Brak.</span><span class="sxs-lookup"><span data-stu-id="b29ae-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b29ae-124">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="b29ae-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b29ae-125">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="b29ae-125">**Element**</span></span>|<span data-ttu-id="b29ae-126">**Opis**</span><span class="sxs-lookup"><span data-stu-id="b29ae-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b29ae-127">ustawienia</span><span class="sxs-lookup"><span data-stu-id="b29ae-127">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="b29ae-128">Konfiguruje podstawowe opcje sieci dla <xref:System.Net> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b29ae-128">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b29ae-129">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b29ae-129">Remarks</span></span>  

 <span data-ttu-id="b29ae-130">Domyślnie .NET Framework ściśle wymusza analizowanie identyfikatorów URI w dokumencie RFC 2616.</span><span class="sxs-lookup"><span data-stu-id="b29ae-130">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="b29ae-131">Niektóre odpowiedzi serwera mogą zawierać znaki kontrolne w zabronionych polach, co spowoduje, że <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> metoda wygeneruje <xref:System.Net.WebException> .</span><span class="sxs-lookup"><span data-stu-id="b29ae-131">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="b29ae-132">Jeśli **UseUnsafeHeaderParsing** ma **wartość true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> program nie będzie zgłaszany w tym przypadku, jednak aplikacja będzie narażona na kilka form ataków dotyczących analizy identyfikatorów URI.</span><span class="sxs-lookup"><span data-stu-id="b29ae-132">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="b29ae-133">Najlepszym rozwiązaniem jest zmiana serwera tak, aby odpowiedź nie zawierała znaków kontrolnych.</span><span class="sxs-lookup"><span data-stu-id="b29ae-133">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b29ae-134">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="b29ae-134">Configuration Files</span></span>  

 <span data-ttu-id="b29ae-135">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b29ae-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b29ae-136">Przykład</span><span class="sxs-lookup"><span data-stu-id="b29ae-136">Example</span></span>  

 <span data-ttu-id="b29ae-137">Poniższy przykład pokazuje, jak określić większą niż normalną maksymalną długość nagłówka.</span><span class="sxs-lookup"><span data-stu-id="b29ae-137">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b29ae-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b29ae-138">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="b29ae-139">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="b29ae-139">Network Settings Schema</span></span>](index.md)
