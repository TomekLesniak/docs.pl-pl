---
title: <qualifyAssembly> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
ms.openlocfilehash: 26b265996a059d8e52901557603bcf5e7636e596
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195223"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="708ab-102">\<qualifyAssembly> Element</span><span class="sxs-lookup"><span data-stu-id="708ab-102">\<qualifyAssembly> Element</span></span>

<span data-ttu-id="708ab-103">Określa pełną nazwę zestawu, który ma być dynamicznie ładowany, gdy zostanie użyta nazwa częściowa.</span><span class="sxs-lookup"><span data-stu-id="708ab-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="708ab-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="708ab-104">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="708ab-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="708ab-105">Attributes and Elements</span></span>  

 <span data-ttu-id="708ab-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="708ab-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="708ab-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="708ab-107">Attributes</span></span>  
  
|<span data-ttu-id="708ab-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="708ab-108">Attribute</span></span>|<span data-ttu-id="708ab-109">Opis</span><span class="sxs-lookup"><span data-stu-id="708ab-109">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="708ab-110">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="708ab-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="708ab-111">Określa częściową nazwę zestawu, która pojawia się w kodzie.</span><span class="sxs-lookup"><span data-stu-id="708ab-111">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="708ab-112">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="708ab-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="708ab-113">Określa pełną nazwę zestawu, która pojawia się w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="708ab-113">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="708ab-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="708ab-114">Child Elements</span></span>  

 <span data-ttu-id="708ab-115">Brak.</span><span class="sxs-lookup"><span data-stu-id="708ab-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="708ab-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="708ab-116">Parent Elements</span></span>  
  
|<span data-ttu-id="708ab-117">Element</span><span class="sxs-lookup"><span data-stu-id="708ab-117">Element</span></span>|<span data-ttu-id="708ab-118">Opis</span><span class="sxs-lookup"><span data-stu-id="708ab-118">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="708ab-119">Zawiera informacje o przekierowaniu wersji zestawu i lokalizacji zestawów.</span><span class="sxs-lookup"><span data-stu-id="708ab-119">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="708ab-120">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="708ab-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="708ab-121">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="708ab-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="708ab-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="708ab-122">Remarks</span></span>  

 <span data-ttu-id="708ab-123">Wywołanie <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> metody przy użyciu częściowych nazw zestawów powoduje, że środowisko uruchomieniowe języka wspólnego szuka zestawu tylko w katalogu podstawowym aplikacji.</span><span class="sxs-lookup"><span data-stu-id="708ab-123">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="708ab-124">Użyj **\<qualifyAssembly>** elementu w pliku konfiguracji aplikacji, aby podać pełne informacje o zestawie (nazwę, wersję, token klucza publicznego i kulturę) i spowodować wyszukanie zestawu w globalnej pamięci podręcznej zestawów przez środowisko uruchomieniowe języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="708ab-124">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="708ab-125">Atrybut **FullName** musi zawierać cztery pola tożsamości zestawu: nazwę, wersję, token klucza publicznego i kulturę.</span><span class="sxs-lookup"><span data-stu-id="708ab-125">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="708ab-126">Atrybut **częściname** musi częściowo odwoływać się do zestawu.</span><span class="sxs-lookup"><span data-stu-id="708ab-126">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="708ab-127">Należy określić co najmniej nazwę tekstu zestawu (najbardziej typowe), ale można również dołączyć wersję, token klucza publicznego lub kulturę (lub dowolną kombinację czterech, ale nie wszystkie cztery).</span><span class="sxs-lookup"><span data-stu-id="708ab-127">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="708ab-128">**Część częściowa** musi być zgodna z nazwą określoną w wywołaniu.</span><span class="sxs-lookup"><span data-stu-id="708ab-128">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="708ab-129">Na przykład nie można określić `"math"` jako atrybutu **częściname** w pliku konfiguracji i wywołać `Assembly.Load("math, Version=3.3.3.3")` w kodzie.</span><span class="sxs-lookup"><span data-stu-id="708ab-129">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="708ab-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="708ab-130">Example</span></span>  

 <span data-ttu-id="708ab-131">Poniższy przykład logicznie włącza wywołania `Assembly.Load("math")` do `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")` .</span><span class="sxs-lookup"><span data-stu-id="708ab-131">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="708ab-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="708ab-132">See also</span></span>

- [<span data-ttu-id="708ab-133">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="708ab-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="708ab-134">Sposoby lokalizowania zestawów przez środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="708ab-134">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="708ab-135">[Odwołania do zestawów częściowych](/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="708ab-135">[Partial Assembly References](/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
