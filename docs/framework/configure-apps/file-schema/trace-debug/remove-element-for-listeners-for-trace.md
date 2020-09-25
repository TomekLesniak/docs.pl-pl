---
title: <remove> Element dla <listeners> elementu <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 01b797e1fb62d32e9f0d44c54b803dd969615361
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173838"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="a4117-102">\<remove> Element dla \<listeners> elementu \<trace></span><span class="sxs-lookup"><span data-stu-id="a4117-102">\<remove> Element for \<listeners> for \<trace></span></span>

<span data-ttu-id="a4117-103">Usuwa odbiornik z kolekcji **odbiorników** .</span><span class="sxs-lookup"><span data-stu-id="a4117-103">Removes a listener from the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="a4117-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a4117-104">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4117-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a4117-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a4117-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a4117-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4117-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a4117-107">Attributes</span></span>  
  
|<span data-ttu-id="a4117-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a4117-108">Attribute</span></span>|<span data-ttu-id="a4117-109">Opis</span><span class="sxs-lookup"><span data-stu-id="a4117-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4117-110">**Nazwij**</span><span class="sxs-lookup"><span data-stu-id="a4117-110">**name**</span></span>|<span data-ttu-id="a4117-111">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="a4117-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="a4117-112">Nazwa odbiornika, który ma zostać usunięty z kolekcji **odbiorników** .</span><span class="sxs-lookup"><span data-stu-id="a4117-112">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4117-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a4117-113">Child Elements</span></span>  

 <span data-ttu-id="a4117-114">Brak.</span><span class="sxs-lookup"><span data-stu-id="a4117-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4117-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a4117-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a4117-116">Element</span><span class="sxs-lookup"><span data-stu-id="a4117-116">Element</span></span>|<span data-ttu-id="a4117-117">Opis</span><span class="sxs-lookup"><span data-stu-id="a4117-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a4117-118">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a4117-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="a4117-119">Określa odbiornik, który zbiera, przechowuje i kieruje komunikaty.</span><span class="sxs-lookup"><span data-stu-id="a4117-119">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="a4117-120">Odbiorniki kierują dane wyjściowe śledzenia do odpowiedniego obiektu docelowego.</span><span class="sxs-lookup"><span data-stu-id="a4117-120">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a4117-121">Określa detektory śledzenia, które zbierają, przechowują i rozsyłają komunikaty oraz poziom, w którym ustawiono przełącznik śledzenia.</span><span class="sxs-lookup"><span data-stu-id="a4117-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="a4117-122">Konfiguruje usługę śledzenia ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4117-122">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4117-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a4117-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4117-124">Usunięcie <xref:System.Diagnostics.DefaultTraceListener> z `Listeners` kolekcji powoduje zmianę zachowania <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> metod,, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> i <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a4117-124">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="a4117-125">Wywołanie `Assert` metody lub `Fail` zwykle powoduje wyświetlenie okna komunikatu, ale okno komunikatu nie jest wyświetlane, jeśli <xref:System.Diagnostics.DefaultTraceListener> nie znajduje się w `Listeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="a4117-125">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4117-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="a4117-126">Example</span></span>  

 <span data-ttu-id="a4117-127">Poniższy przykład pokazuje, jak usunąć domyślny odbiornik śledzenia z kolekcji **detektorów** śledzenia.</span><span class="sxs-lookup"><span data-stu-id="a4117-127">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4117-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a4117-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="a4117-129">Schemat ustawień śledzenia i debugowania</span><span class="sxs-lookup"><span data-stu-id="a4117-129">Trace and Debug Settings Schema</span></span>](index.md)
