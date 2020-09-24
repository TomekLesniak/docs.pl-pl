---
title: <clear> Element dla <listeners> elementu <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: d3e76496c82b508feabf8a46cf7bce7e3d54e8cf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149286"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="28df8-102">\<clear> Element dla \<listeners> elementu \<source></span><span class="sxs-lookup"><span data-stu-id="28df8-102">\<clear> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="28df8-103">Czyści `Listeners` kolekcję dla źródła śledzenia.</span><span class="sxs-lookup"><span data-stu-id="28df8-103">Clears the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="28df8-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="28df8-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28df8-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="28df8-105">Attributes and Elements</span></span>  

 <span data-ttu-id="28df8-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="28df8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28df8-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="28df8-107">Attributes</span></span>  

 <span data-ttu-id="28df8-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="28df8-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="28df8-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="28df8-109">Child Elements</span></span>  

 <span data-ttu-id="28df8-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="28df8-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28df8-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="28df8-111">Parent Elements</span></span>  
  
|<span data-ttu-id="28df8-112">Element</span><span class="sxs-lookup"><span data-stu-id="28df8-112">Element</span></span>|<span data-ttu-id="28df8-113">Opis</span><span class="sxs-lookup"><span data-stu-id="28df8-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="28df8-114">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="28df8-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="28df8-115">Określa detektory śledzenia, które zbierają, przechowują i rozsyłają komunikaty oraz poziom, w którym ustawiono przełącznik śledzenia.</span><span class="sxs-lookup"><span data-stu-id="28df8-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="28df8-116">Zawiera źródła śledzenia, które inicjują komunikaty śledzenia.</span><span class="sxs-lookup"><span data-stu-id="28df8-116">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="28df8-117">Określa źródło śledzenia, które inicjuje komunikaty śledzenia.</span><span class="sxs-lookup"><span data-stu-id="28df8-117">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="28df8-118">Określa detektory, które zbierają, przechowują i rozsyłają komunikaty.</span><span class="sxs-lookup"><span data-stu-id="28df8-118">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28df8-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="28df8-119">Remarks</span></span>  

 <span data-ttu-id="28df8-120">`<clear>`Element usuwa wszystkie odbiorniki z `Listeners` kolekcji dla źródła śledzenia, włącznie z <xref:System.Diagnostics.DefaultTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="28df8-120">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="28df8-121">Możesz użyć `<clear>` elementu przed użyciem `<add>` elementu, aby mieć pewność, że w kolekcji nie ma żadnych innych aktywnych odbiorników.</span><span class="sxs-lookup"><span data-stu-id="28df8-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="28df8-122">Plik konfiguracji</span><span class="sxs-lookup"><span data-stu-id="28df8-122">Configuration File</span></span>  

 <span data-ttu-id="28df8-123">Tego elementu można użyć w pliku konfiguracji komputera (Machine.config) i pliku konfiguracyjnym aplikacji.</span><span class="sxs-lookup"><span data-stu-id="28df8-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28df8-124">Przykład</span><span class="sxs-lookup"><span data-stu-id="28df8-124">Example</span></span>  

 <span data-ttu-id="28df8-125">Poniższy przykład pokazuje, jak używać `<clear>` elementu przed użyciem `<add>` elementów, aby dodać detektory `console` oraz `textListener` do `Listeners` kolekcji dla źródła śledzenia `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="28df8-125">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"
        type="System.Diagnostics.TextWriterTraceListener"
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="28df8-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="28df8-126">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="28df8-127">Schemat ustawień śledzenia i debugowania</span><span class="sxs-lookup"><span data-stu-id="28df8-127">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="28df8-128">Obiekty nasłuchujące śledzenia</span><span class="sxs-lookup"><span data-stu-id="28df8-128">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
