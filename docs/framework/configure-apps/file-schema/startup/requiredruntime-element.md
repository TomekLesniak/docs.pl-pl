---
title: <requiredRuntime>, element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: 19fa1561ca3acd845918d952379c5227121465b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174072"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="8d15a-102">\<requiredRuntime>, element</span><span class="sxs-lookup"><span data-stu-id="8d15a-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="8d15a-103">Określa, że aplikacja obsługuje tylko wersję 1,0 środowiska uruchomieniowego języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="8d15a-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="8d15a-104">Ten element jest przestarzały i nie powinien już być używany.</span><span class="sxs-lookup"><span data-stu-id="8d15a-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="8d15a-105">[`supportedRuntime`](supportedruntime-element.md)Zamiast tego należy użyć elementu.</span><span class="sxs-lookup"><span data-stu-id="8d15a-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a><span data-ttu-id="8d15a-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="8d15a-106">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8d15a-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="8d15a-107">Attributes and elements</span></span>

<span data-ttu-id="8d15a-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="8d15a-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8d15a-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="8d15a-109">Attributes</span></span>

|<span data-ttu-id="8d15a-110">Atrybut</span><span class="sxs-lookup"><span data-stu-id="8d15a-110">Attribute</span></span>|<span data-ttu-id="8d15a-111">Opis</span><span class="sxs-lookup"><span data-stu-id="8d15a-111">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="8d15a-112">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="8d15a-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8d15a-113">Wartość ciągu określająca wersję .NET Framework obsługiwanej przez tę aplikację.</span><span class="sxs-lookup"><span data-stu-id="8d15a-113">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="8d15a-114">Wartość ciągu musi być zgodna z nazwą katalogu znajdującą się w katalogu głównym instalacji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8d15a-114">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="8d15a-115">Zawartość ciągu nie jest analizowana.</span><span class="sxs-lookup"><span data-stu-id="8d15a-115">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="8d15a-116">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="8d15a-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8d15a-117">Określa, czy kod uruchomienia środowiska uruchomieniowego przeszukuje rejestr w celu określenia wersji środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="8d15a-117">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="8d15a-118">safemode — atrybut</span><span class="sxs-lookup"><span data-stu-id="8d15a-118">safemode attribute</span></span>

|<span data-ttu-id="8d15a-119">Wartość</span><span class="sxs-lookup"><span data-stu-id="8d15a-119">Value</span></span>|<span data-ttu-id="8d15a-120">Opis</span><span class="sxs-lookup"><span data-stu-id="8d15a-120">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="8d15a-121">Kod uruchomienia środowiska uruchomieniowego przeszukuje rejestr.</span><span class="sxs-lookup"><span data-stu-id="8d15a-121">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="8d15a-122">Jest to wartość domyślna.</span><span class="sxs-lookup"><span data-stu-id="8d15a-122">This is the default value.</span></span>|
|`true`|<span data-ttu-id="8d15a-123">Kod uruchomienia środowiska uruchomieniowego nie przeszukuje rejestru.</span><span class="sxs-lookup"><span data-stu-id="8d15a-123">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="8d15a-124">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="8d15a-124">Child elements</span></span>

<span data-ttu-id="8d15a-125">Brak.</span><span class="sxs-lookup"><span data-stu-id="8d15a-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8d15a-126">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="8d15a-126">Parent elements</span></span>

|<span data-ttu-id="8d15a-127">Element</span><span class="sxs-lookup"><span data-stu-id="8d15a-127">Element</span></span>|<span data-ttu-id="8d15a-128">Opis</span><span class="sxs-lookup"><span data-stu-id="8d15a-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="8d15a-129">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8d15a-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="8d15a-130">Zawiera `<requiredRuntime>` element.</span><span class="sxs-lookup"><span data-stu-id="8d15a-130">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8d15a-131">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8d15a-131">Remarks</span></span>

 <span data-ttu-id="8d15a-132">Aplikacje skompilowane do obsługi tylko wersji 1,0 środowiska uruchomieniowego muszą używać `<requiredRuntime>` elementu.</span><span class="sxs-lookup"><span data-stu-id="8d15a-132">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="8d15a-133">Aplikacje skompilowane przy użyciu wersji 1,1 lub nowszej środowiska uruchomieniowego muszą używać `<supportedRuntime>` elementu.</span><span class="sxs-lookup"><span data-stu-id="8d15a-133">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="8d15a-134">Jeśli używasz funkcji [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) do określenia pliku konfiguracji, musisz użyć `<requiredRuntime>` elementu dla wszystkich wersji środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="8d15a-134">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="8d15a-135">`<supportedRuntime>`Element jest ignorowany w przypadku korzystania z [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="8d15a-135">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="8d15a-136">`version`Ciąg atrybutu musi być zgodny z nazwą folderu instalacji określonej wersji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8d15a-136">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="8d15a-137">Ten ciąg nie jest interpretowany.</span><span class="sxs-lookup"><span data-stu-id="8d15a-137">This string is not interpreted.</span></span> <span data-ttu-id="8d15a-138">Jeśli kod uruchomienia środowiska uruchomieniowego nie odnajdzie pasującego folderu, środowisko uruchomieniowe nie zostanie załadowane; kod uruchamiania pokazuje komunikat o błędzie i kończy pracę.</span><span class="sxs-lookup"><span data-stu-id="8d15a-138">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="8d15a-139">Kod uruchamiania aplikacji hostowanej w programie Microsoft Internet Explorer ignoruje `<requiredRuntime>` element.</span><span class="sxs-lookup"><span data-stu-id="8d15a-139">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="8d15a-140">Przykład</span><span class="sxs-lookup"><span data-stu-id="8d15a-140">Example</span></span>

<span data-ttu-id="8d15a-141">Poniższy przykład pokazuje, jak określić wersję środowiska uruchomieniowego w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="8d15a-141">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="8d15a-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8d15a-142">See also</span></span>

- [<span data-ttu-id="8d15a-143">Schemat ustawień uruchamiania</span><span class="sxs-lookup"><span data-stu-id="8d15a-143">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8d15a-144">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="8d15a-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8d15a-145">Instrukcje: Konfigurowanie aplikacji do obsługi .NET Framework 4 lub nowszej wersji</span><span class="sxs-lookup"><span data-stu-id="8d15a-145">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
