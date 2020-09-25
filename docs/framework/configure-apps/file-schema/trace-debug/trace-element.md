---
title: <trace> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 617b42a0be2be272a78b33be997cce632d1c6dcb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198928"
---
# <a name="trace-element"></a><span data-ttu-id="95a89-102">\<trace> Element</span><span class="sxs-lookup"><span data-stu-id="95a89-102">\<trace> Element</span></span>

<span data-ttu-id="95a89-103">Zawiera detektory, które zbierają, przechowują i rozsyłają komunikaty śledzenia.</span><span class="sxs-lookup"><span data-stu-id="95a89-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**  
  
## <a name="syntax"></a><span data-ttu-id="95a89-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="95a89-104">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95a89-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="95a89-105">Attributes and Elements</span></span>  

 <span data-ttu-id="95a89-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="95a89-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95a89-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="95a89-107">Attributes</span></span>  
  
|<span data-ttu-id="95a89-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="95a89-108">Attribute</span></span>|<span data-ttu-id="95a89-109">Opis</span><span class="sxs-lookup"><span data-stu-id="95a89-109">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="95a89-110">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="95a89-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="95a89-111">Określa, czy odbiorniki śledzenia automatycznie opróżniają bufor wyjściowy po każdej operacji zapisu.</span><span class="sxs-lookup"><span data-stu-id="95a89-111">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="95a89-112">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="95a89-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="95a89-113">Określa liczbę spacji do wcięcia.</span><span class="sxs-lookup"><span data-stu-id="95a89-113">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="95a89-114">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="95a89-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="95a89-115">Wskazuje, czy globalna blokada powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="95a89-115">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="95a89-116">AutoFlush — atrybut</span><span class="sxs-lookup"><span data-stu-id="95a89-116">autoflush Attribute</span></span>  
  
|<span data-ttu-id="95a89-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="95a89-117">Value</span></span>|<span data-ttu-id="95a89-118">Opis</span><span class="sxs-lookup"><span data-stu-id="95a89-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="95a89-119">Nie opróżnia bufora wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="95a89-119">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="95a89-120">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="95a89-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="95a89-121">Automatycznie opróżnia bufor wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="95a89-121">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="95a89-122">useGlobalLock — Atrybut</span><span class="sxs-lookup"><span data-stu-id="95a89-122">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="95a89-123">Wartość</span><span class="sxs-lookup"><span data-stu-id="95a89-123">Value</span></span>|<span data-ttu-id="95a89-124">Opis</span><span class="sxs-lookup"><span data-stu-id="95a89-124">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="95a89-125">Nie używa blokady globalnej, jeśli odbiornik jest bezpieczny wątkowo; w przeciwnym razie używa blokady globalnej.</span><span class="sxs-lookup"><span data-stu-id="95a89-125">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="95a89-126">Używa blokady globalnej niezależnie od tego, czy odbiornik jest bezpieczny wątkowo.</span><span class="sxs-lookup"><span data-stu-id="95a89-126">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="95a89-127">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="95a89-127">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95a89-128">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="95a89-128">Child Elements</span></span>  
  
|<span data-ttu-id="95a89-129">Element</span><span class="sxs-lookup"><span data-stu-id="95a89-129">Element</span></span>|<span data-ttu-id="95a89-130">Opis</span><span class="sxs-lookup"><span data-stu-id="95a89-130">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|<span data-ttu-id="95a89-131">Określa odbiornik, który zbiera, przechowuje i kieruje komunikaty.</span><span class="sxs-lookup"><span data-stu-id="95a89-131">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95a89-132">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="95a89-132">Parent Elements</span></span>  
  
|<span data-ttu-id="95a89-133">Element</span><span class="sxs-lookup"><span data-stu-id="95a89-133">Element</span></span>|<span data-ttu-id="95a89-134">Opis</span><span class="sxs-lookup"><span data-stu-id="95a89-134">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="95a89-135">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="95a89-135">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="95a89-136">Określa detektory śledzenia, które zbierają, przechowują i rozsyłają komunikaty oraz poziom, w którym ustawiono przełącznik śledzenia.</span><span class="sxs-lookup"><span data-stu-id="95a89-136">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95a89-137">Przykład</span><span class="sxs-lookup"><span data-stu-id="95a89-137">Example</span></span>  

 <span data-ttu-id="95a89-138">Poniższy przykład pokazuje, jak użyć elementu, `<trace>` Aby dodać odbiornik `MyListener` do `Listeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="95a89-138">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="95a89-139">`MyListener` tworzy plik o nazwie `MyListener.log` i zapisuje dane wyjściowe do pliku.</span><span class="sxs-lookup"><span data-stu-id="95a89-139">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="95a89-140">`useGlobalLock`Atrybut jest ustawiony na `false` , co powoduje, że globalna blokada nie zostanie użyta, jeśli odbiornik śledzenia jest bezpieczny wątkowo.</span><span class="sxs-lookup"><span data-stu-id="95a89-140">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="95a89-141">`autoflush`Atrybut jest ustawiony na `true` , co powoduje, że odbiornik śledzenia ma zapisywać do pliku bez względu na to, czy <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> Metoda jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="95a89-141">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="95a89-142">`indentsize`Atrybut jest ustawiony na 0 (zero), co powoduje, że odbiornik ma wcięcie zerowej spacji, gdy <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> wywoływana jest metoda.</span><span class="sxs-lookup"><span data-stu-id="95a89-142">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95a89-143">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="95a89-143">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="95a89-144">Schemat ustawień śledzenia i debugowania</span><span class="sxs-lookup"><span data-stu-id="95a89-144">Trace and Debug Settings Schema</span></span>](index.md)
