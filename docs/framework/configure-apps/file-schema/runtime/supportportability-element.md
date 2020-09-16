---
title: <supportPortability> Element
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
ms.openlocfilehash: 99fa51238040f21d998a8c6c2aef7c13d288104a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551588"
---
# <a name="supportportability-element"></a><span data-ttu-id="9c8b6-102">\<supportPortability> Element</span><span class="sxs-lookup"><span data-stu-id="9c8b6-102">\<supportPortability> Element</span></span>
<span data-ttu-id="9c8b6-103">Określa, że aplikacja może odwoływać się do tego samego zestawu w dwóch różnych implementacjach .NET Framework, przez wyłączenie domyślnego zachowania, które traktuje zestawy jako równoważne do celów przenośności aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<supportPortability>**  
  
## <a name="syntax"></a><span data-ttu-id="9c8b6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9c8b6-104">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c8b6-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="9c8b6-105">Attributes and Elements</span></span>  

<span data-ttu-id="9c8b6-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c8b6-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="9c8b6-107">Attributes</span></span>  
  
|<span data-ttu-id="9c8b6-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="9c8b6-108">Attribute</span></span>|<span data-ttu-id="9c8b6-109">Opis</span><span class="sxs-lookup"><span data-stu-id="9c8b6-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c8b6-110">PKT</span><span class="sxs-lookup"><span data-stu-id="9c8b6-110">PKT</span></span>|<span data-ttu-id="9c8b6-111">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="9c8b6-112">Określa token klucza publicznego zestawu, którego to dotyczy, jako ciąg znaków.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-112">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="9c8b6-113">enabled</span><span class="sxs-lookup"><span data-stu-id="9c8b6-113">enabled</span></span>|<span data-ttu-id="9c8b6-114">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9c8b6-115">Określa, czy obsługa przenośności między implementacjami określonego zestawu .NET Framework powinna być włączona.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-115">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9c8b6-116">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="9c8b6-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="9c8b6-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="9c8b6-117">Value</span></span>|<span data-ttu-id="9c8b6-118">Opis</span><span class="sxs-lookup"><span data-stu-id="9c8b6-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9c8b6-119">true</span><span class="sxs-lookup"><span data-stu-id="9c8b6-119">true</span></span>|<span data-ttu-id="9c8b6-120">Włącz obsługę przenośności między implementacjami określonego zestawu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-120">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="9c8b6-121">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-121">This is the default.</span></span>|  
|<span data-ttu-id="9c8b6-122">fałsz</span><span class="sxs-lookup"><span data-stu-id="9c8b6-122">false</span></span>|<span data-ttu-id="9c8b6-123">Wyłącz obsługę przenośności między implementacjami określonego zestawu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-123">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="9c8b6-124">Dzięki temu aplikacja może mieć odwołania do wielu implementacji określonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-124">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c8b6-125">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="9c8b6-125">Child Elements</span></span>  

<span data-ttu-id="9c8b6-126">Brak.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c8b6-127">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="9c8b6-127">Parent Elements</span></span>  
  
|<span data-ttu-id="9c8b6-128">Element</span><span class="sxs-lookup"><span data-stu-id="9c8b6-128">Element</span></span>|<span data-ttu-id="9c8b6-129">Opis</span><span class="sxs-lookup"><span data-stu-id="9c8b6-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9c8b6-130">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9c8b6-131">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-131">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="9c8b6-132">Zawiera informacje o przekierowaniu wersji zestawu i lokalizacji zestawów.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-132">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c8b6-133">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9c8b6-133">Remarks</span></span>  

<span data-ttu-id="9c8b6-134">Począwszy od .NET Framework 4, pomoc techniczna jest świadczona automatycznie dla aplikacji, które mogą korzystać z jednej z dwóch implementacji .NET Framework, na przykład implementacji .NET Framework lub .NET Framework dla implementacji Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-134">Beginning with the .NET Framework 4, support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="9c8b6-135">Dwie implementacje określonego zestawu .NET Framework są uważane za równoważne przez spinacz zestawu.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-135">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="9c8b6-136">W kilku scenariuszach ta funkcja przenośności aplikacji powoduje problemy.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-136">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="9c8b6-137">W tych scenariuszach `<supportPortability>` element może być używany do wyłączania tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-137">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
<span data-ttu-id="9c8b6-138">Taki scenariusz jest zestawem, który musi odwoływać się zarówno do implementacji .NET Framework, jak i .NET Framework do implementacji Silverlight dla określonego zestawu odwołania.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-138">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="9c8b6-139">Na przykład Projektant XAML zapisany w Windows Presentation Foundation (WPF) może potrzebować odwoływać się zarówno do implementacji pulpitu WPF, interfejsu użytkownika projektanta, jak i podzbioru WPF, który jest zawarty w implementacji Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-139">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="9c8b6-140">Domyślnie oddzielne odwołania powodują wystąpienie błędu kompilatora, ponieważ powiązanie zestawu widzi dwa zestawy jako równoważne.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-140">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="9c8b6-141">Ten element wyłącza zachowanie domyślne i zezwala na pomyślne Kompilowanie.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-141">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9c8b6-142">Aby kompilator przeszedł informacje do logiki wiązania zestawu środowiska uruchomieniowego języka wspólnego, należy użyć `/appconfig` opcji kompilatora, aby określić lokalizację pliku app.config zawierającego ten element.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-142">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c8b6-143">Przykład</span><span class="sxs-lookup"><span data-stu-id="9c8b6-143">Example</span></span>  

<span data-ttu-id="9c8b6-144">Poniższy przykład umożliwia aplikacji odwoływanie się do implementacji .NET Framework i .NET Framework dla implementacji Silverlight dowolnego zestawu .NET Framework, który istnieje w obu implementacjach.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-144">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="9c8b6-145">`/appconfig`Aby określić lokalizację tego pliku app.config, należy użyć opcji kompilatora.</span><span class="sxs-lookup"><span data-stu-id="9c8b6-145">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c8b6-146">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9c8b6-146">See also</span></span>

- [<span data-ttu-id="9c8b6-147">-AppConfig (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="9c8b6-147">-appconfig (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="9c8b6-148">[Przegląd dezjednoczenia zestawu .NET Framework](/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9c8b6-148">[.NET Framework Assembly Unification Overview](/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
