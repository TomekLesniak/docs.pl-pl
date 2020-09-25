---
title: <filter> Element dla <add> elementu <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: e140148a342e31d6ade7def8849d8a7738301704
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173929"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="023d6-102">\<filter> Element dla \<add> elementu \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="023d6-102">\<filter> Element for \<add> for \<sharedListeners></span></span>

<span data-ttu-id="023d6-103">Dodaje filtr do odbiornika w `sharedListeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="023d6-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="023d6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="023d6-104">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="023d6-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="023d6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="023d6-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="023d6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="023d6-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="023d6-107">Attributes</span></span>  
  
|<span data-ttu-id="023d6-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="023d6-108">Attribute</span></span>|<span data-ttu-id="023d6-109">Opis</span><span class="sxs-lookup"><span data-stu-id="023d6-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="023d6-110">**Wprowadź**</span><span class="sxs-lookup"><span data-stu-id="023d6-110">**type**</span></span>|<span data-ttu-id="023d6-111">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="023d6-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="023d6-112">Określa typ filtru.</span><span class="sxs-lookup"><span data-stu-id="023d6-112">Specifies the type of the filter.</span></span> <span data-ttu-id="023d6-113">Można użyć tylko pełnej nazwy typu (w formacie <xref:System.Type.FullName%2A?displayProperty=nameWithType> Właściwości) lub użyć w pełni kwalifikowanej nazwy typu, w tym informacji o zestawie (w formacie <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> Właściwości).</span><span class="sxs-lookup"><span data-stu-id="023d6-113">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="023d6-114">Aby uzyskać informacje na temat tworzenia w pełni kwalifikowanej nazwy typu, zobacz [Określanie w pełni kwalifikowanych nazw typów](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="023d6-114">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="023d6-115">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="023d6-115">**initializeData**</span></span>|<span data-ttu-id="023d6-116">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="023d6-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="023d6-117">Ciąg przesłany do konstruktora dla określonej klasy.</span><span class="sxs-lookup"><span data-stu-id="023d6-117">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="023d6-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="023d6-118">Child Elements</span></span>  

 <span data-ttu-id="023d6-119">Brak.</span><span class="sxs-lookup"><span data-stu-id="023d6-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="023d6-120">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="023d6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="023d6-121">Element</span><span class="sxs-lookup"><span data-stu-id="023d6-121">Element</span></span>|<span data-ttu-id="023d6-122">Opis</span><span class="sxs-lookup"><span data-stu-id="023d6-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="023d6-123">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="023d6-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="023d6-124">Określa detektory śledzenia, które zbierają, przechowują i rozsyłają komunikaty oraz poziom, w którym ustawiono przełącznik śledzenia.</span><span class="sxs-lookup"><span data-stu-id="023d6-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="023d6-125">Kolekcja detektorów, które mogą odwoływać się do każdego elementu źródłowego lub śledzenia.</span><span class="sxs-lookup"><span data-stu-id="023d6-125">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="023d6-126">Dodaje odbiornik do kolekcji **sharedListeners** .</span><span class="sxs-lookup"><span data-stu-id="023d6-126">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="023d6-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="023d6-127">Remarks</span></span>  

 <span data-ttu-id="023d6-128">Jeśli odbiornik jest zdefiniowany w `<add>` elemencie `<sharedListeners>` elementu, filtr dla tego odbiornika powinien być zdefiniowany w `<filter>` elemencie, który jest elementem podrzędnym `<add>` elementu.</span><span class="sxs-lookup"><span data-stu-id="023d6-128">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="023d6-129">Tego elementu można użyć w pliku konfiguracji komputera (Machine.config) i pliku konfiguracyjnym aplikacji.</span><span class="sxs-lookup"><span data-stu-id="023d6-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="023d6-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="023d6-130">Example</span></span>  

 <span data-ttu-id="023d6-131">Poniższy przykład pokazuje, jak za pomocą `<filter>` elementu dodać filtr do odbiornika śledzenia `console` w `sharedListeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="023d6-131">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="023d6-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="023d6-132">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="023d6-133">Schemat ustawień śledzenia i debugowania</span><span class="sxs-lookup"><span data-stu-id="023d6-133">Trace and Debug Settings Schema</span></span>](index.md)
