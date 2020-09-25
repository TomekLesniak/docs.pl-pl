---
title: <listeners>, element dla <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 59d078f8dc573a1ce949d225f497dd4500fe808f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173864"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="ac188-102">\<listeners>, element dla \<trace></span><span class="sxs-lookup"><span data-stu-id="ac188-102">\<listeners> Element for \<trace></span></span>

<span data-ttu-id="ac188-103">Określa odbiornik, który zbiera, przechowuje i kieruje komunikaty.</span><span class="sxs-lookup"><span data-stu-id="ac188-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="ac188-104">Odbiorniki kierują dane wyjściowe śledzenia do odpowiedniego obiektu docelowego.</span><span class="sxs-lookup"><span data-stu-id="ac188-104">Listeners direct the tracing output to an appropriate target.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**

## <a name="syntax"></a><span data-ttu-id="ac188-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ac188-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac188-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="ac188-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ac188-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="ac188-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac188-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="ac188-108">Attributes</span></span>  

 <span data-ttu-id="ac188-109">Brak.</span><span class="sxs-lookup"><span data-stu-id="ac188-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ac188-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="ac188-110">Child Elements</span></span>  
  
|<span data-ttu-id="ac188-111">Element</span><span class="sxs-lookup"><span data-stu-id="ac188-111">Element</span></span>|<span data-ttu-id="ac188-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ac188-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="ac188-113">Dodaje odbiornik do `Listeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="ac188-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="ac188-114">Czyści `Listeners` kolekcję do śledzenia.</span><span class="sxs-lookup"><span data-stu-id="ac188-114">Clears the `Listeners` collection for trace.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="ac188-115">Usuwa odbiornik z `Listeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="ac188-115">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac188-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="ac188-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ac188-117">Element</span><span class="sxs-lookup"><span data-stu-id="ac188-117">Element</span></span>|<span data-ttu-id="ac188-118">Opis</span><span class="sxs-lookup"><span data-stu-id="ac188-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ac188-119">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac188-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ac188-120">Określa element główny dla sekcji konfiguracji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ac188-120">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="ac188-121">Zawiera detektory, które zbierają, przechowują i rozsyłają komunikaty śledzenia.</span><span class="sxs-lookup"><span data-stu-id="ac188-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac188-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ac188-122">Remarks</span></span>  

 <span data-ttu-id="ac188-123"><xref:System.Diagnostics.Debug>Klasy i <xref:System.Diagnostics.Trace> współużytkują tę samą kolekcję **detektorów** .</span><span class="sxs-lookup"><span data-stu-id="ac188-123">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="ac188-124">Jeśli dodasz obiekt odbiornika do kolekcji w jednej z tych klas, inna Klasa używa tego samego odbiornika.</span><span class="sxs-lookup"><span data-stu-id="ac188-124">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="ac188-125">Klasy odbiornika dostarczane z .NET Framework pochodzą od <xref:System.Diagnostics.TraceListener> klasy.</span><span class="sxs-lookup"><span data-stu-id="ac188-125">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="ac188-126">Plik konfiguracji</span><span class="sxs-lookup"><span data-stu-id="ac188-126">Configuration File</span></span>  

 <span data-ttu-id="ac188-127">Tego elementu można użyć w pliku konfiguracji komputera (Machine.config) i pliku konfiguracyjnym aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ac188-127">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac188-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="ac188-128">Example</span></span>  

 <span data-ttu-id="ac188-129">Poniższy przykład pokazuje, jak użyć elementu, **\<listeners>** Aby dodać detektory `MyListener` i `MyEventListener` do kolekcji **odbiorników** .</span><span class="sxs-lookup"><span data-stu-id="ac188-129">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="ac188-130">`MyListener` tworzy plik o nazwie `MyListener.log` i zapisuje dane wyjściowe do pliku.</span><span class="sxs-lookup"><span data-stu-id="ac188-130">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="ac188-131">`MyEventListener` tworzy wpis w dzienniku zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="ac188-131">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"
          type="System.Diagnostics.TextWriterTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac188-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ac188-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="ac188-133">Schemat ustawień śledzenia i debugowania</span><span class="sxs-lookup"><span data-stu-id="ac188-133">Trace and Debug Settings Schema</span></span>](index.md)
