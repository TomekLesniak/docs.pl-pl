---
title: <sources> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: 670fb359f892d83feac56c849361c4b980d9a922
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173812"
---
# <a name="sources-element"></a><span data-ttu-id="aedd6-102">\<sources> Element</span><span class="sxs-lookup"><span data-stu-id="aedd6-102">\<sources> Element</span></span>

<span data-ttu-id="aedd6-103">Określa źródła śledzenia, które inicjują komunikaty śledzenia.</span><span class="sxs-lookup"><span data-stu-id="aedd6-103">Specifies trace sources that initiate tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**

## <a name="syntax"></a><span data-ttu-id="aedd6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="aedd6-104">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aedd6-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="aedd6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="aedd6-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="aedd6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aedd6-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="aedd6-107">Attributes</span></span>  

 <span data-ttu-id="aedd6-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="aedd6-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aedd6-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="aedd6-109">Child Elements</span></span>  
  
|<span data-ttu-id="aedd6-110">Element</span><span class="sxs-lookup"><span data-stu-id="aedd6-110">Element</span></span>|<span data-ttu-id="aedd6-111">Opis</span><span class="sxs-lookup"><span data-stu-id="aedd6-111">Description</span></span>|  
|-------------|-----------------|  
|[\<source>](source-element.md)|<span data-ttu-id="aedd6-112">Element wymagany.</span><span class="sxs-lookup"><span data-stu-id="aedd6-112">Required element.</span></span><br /><br /> <span data-ttu-id="aedd6-113">Określa źródło śledzenia, które inicjuje komunikaty śledzenia.</span><span class="sxs-lookup"><span data-stu-id="aedd6-113">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aedd6-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="aedd6-114">Parent Elements</span></span>  
  
|<span data-ttu-id="aedd6-115">Element</span><span class="sxs-lookup"><span data-stu-id="aedd6-115">Element</span></span>|<span data-ttu-id="aedd6-116">Opis</span><span class="sxs-lookup"><span data-stu-id="aedd6-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="aedd6-117">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aedd6-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="aedd6-118">Określa detektory śledzenia, które zbierają, przechowują i rozsyłają komunikaty oraz poziom, w którym ustawiono przełącznik śledzenia.</span><span class="sxs-lookup"><span data-stu-id="aedd6-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aedd6-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="aedd6-119">Remarks</span></span>  

 <span data-ttu-id="aedd6-120">Tego elementu można użyć w pliku konfiguracji komputera (Machine.config) i pliku konfiguracyjnym aplikacji.</span><span class="sxs-lookup"><span data-stu-id="aedd6-120">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aedd6-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="aedd6-121">Example</span></span>  

 <span data-ttu-id="aedd6-122">Poniższy przykład pokazuje, jak użyć elementu, `<sources>` Aby dodać Źródło śledzenia `mySource` i ustawić poziom dla przełącznika źródła o nazwie `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="aedd6-122">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="aedd6-123">Dodano odbiornik śledzenia konsoli, który zapisuje informacje o śledzeniu do konsoli.</span><span class="sxs-lookup"><span data-stu-id="aedd6-123">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"
                     initializeData="Error" />  
               </add>  
               <remove name="Default" />  
            </listeners>  
         </source>  
      </sources>  
      <switches>  
         <add name="sourceSwitch" value="Warning" />  
      </switches>
   </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aedd6-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aedd6-124">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="aedd6-125">Schemat ustawień śledzenia i debugowania</span><span class="sxs-lookup"><span data-stu-id="aedd6-125">Trace and Debug Settings Schema</span></span>](index.md)
- [\<source>](source-element.md)
