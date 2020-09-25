---
title: <loadFromRemoteSources> Element
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: 568c0c814dcc57be0f5be435bb7750c970ffec19
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192454"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="f9101-102">\<loadFromRemoteSources>, element</span><span class="sxs-lookup"><span data-stu-id="f9101-102">\<loadFromRemoteSources> element</span></span>

<span data-ttu-id="f9101-103">Określa, czy zestawy ładowane ze źródeł zdalnych powinny mieć przyznane pełne zaufanie w .NET Framework 4 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="f9101-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9101-104">Jeśli nastąpiło przekierowanie do tego artykułu ze względu na komunikat o błędzie na liście błędów projektu programu Visual Studio lub błąd kompilacji, zobacz [How to: use a Assembly from a Web w Visual Studio](/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f9101-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**  
  
## <a name="syntax"></a><span data-ttu-id="f9101-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f9101-105">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9101-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="f9101-106">Attributes and elements</span></span>

 <span data-ttu-id="f9101-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="f9101-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9101-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="f9101-108">Attributes</span></span>  
  
|<span data-ttu-id="f9101-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="f9101-109">Attribute</span></span>|<span data-ttu-id="f9101-110">Opis</span><span class="sxs-lookup"><span data-stu-id="f9101-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f9101-111">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="f9101-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="f9101-112">Określa, czy zestaw, który jest ładowany ze źródła zdalnego, powinien mieć przyznane pełne zaufanie.</span><span class="sxs-lookup"><span data-stu-id="f9101-112">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f9101-113">włączony atrybut</span><span class="sxs-lookup"><span data-stu-id="f9101-113">enabled attribute</span></span>  
  
|<span data-ttu-id="f9101-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="f9101-114">Value</span></span>|<span data-ttu-id="f9101-115">Opis</span><span class="sxs-lookup"><span data-stu-id="f9101-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="f9101-116">Nie należy przyznawać pełnego zaufania do aplikacji ze źródeł zdalnych.</span><span class="sxs-lookup"><span data-stu-id="f9101-116">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="f9101-117">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="f9101-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="f9101-118">Przyznaj pełne zaufanie do aplikacji ze źródeł zdalnych.</span><span class="sxs-lookup"><span data-stu-id="f9101-118">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9101-119">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="f9101-119">Child elements</span></span>  

 <span data-ttu-id="f9101-120">Brak.</span><span class="sxs-lookup"><span data-stu-id="f9101-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9101-121">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="f9101-121">Parent elements</span></span>  
  
|<span data-ttu-id="f9101-122">Element</span><span class="sxs-lookup"><span data-stu-id="f9101-122">Element</span></span>|<span data-ttu-id="f9101-123">Opis</span><span class="sxs-lookup"><span data-stu-id="f9101-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f9101-124">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9101-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f9101-125">Zawiera informacje dotyczące opcji inicjowania środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="f9101-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9101-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f9101-126">Remarks</span></span>

<span data-ttu-id="f9101-127">W .NET Framework 3,5 i starszych wersjach, Jeśli ładujesz zestaw z lokalizacji zdalnej, kod w zestawie jest uruchamiany w częściowej relacji zaufania z zestawem uprawnień, który zależy od strefy, z której jest załadowana.</span><span class="sxs-lookup"><span data-stu-id="f9101-127">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="f9101-128">Na przykład, Jeśli ładujesz zestaw z witryny sieci Web, zostanie on załadowany do strefy Internet i przyznany zestaw uprawnień internetowych.</span><span class="sxs-lookup"><span data-stu-id="f9101-128">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="f9101-129">Innymi słowy, jest wykonywana w piaskownicy internetowej.</span><span class="sxs-lookup"><span data-stu-id="f9101-129">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="f9101-130">Począwszy od .NET Framework 4, zasady zabezpieczeń dostępu kodu (CAS) są wyłączone, a zestawy są ładowane w trybie pełnego zaufania.</span><span class="sxs-lookup"><span data-stu-id="f9101-130">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="f9101-131">Zwykle pozwala to na pełne zaufanie do zestawów ładowanych przy użyciu <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> metody, która wcześniej była w trybie piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="f9101-131">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="f9101-132">Aby tego uniknąć, możliwość uruchamiania kodu w zestawach załadowanych ze zdalnego źródła jest domyślnie wyłączona.</span><span class="sxs-lookup"><span data-stu-id="f9101-132">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="f9101-133">Domyślnie, jeśli próbujesz załadować zestaw zdalny, zostanie <xref:System.IO.FileLoadException> zgłoszony komunikat o wyjątku podobny do następującego:</span><span class="sxs-lookup"><span data-stu-id="f9101-133">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="f9101-134">Aby załadować zestaw i wykonać jego kod, musisz:</span><span class="sxs-lookup"><span data-stu-id="f9101-134">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="f9101-135">Jawnie Utwórz piaskownicę zestawu (zobacz [jak: uruchamianie częściowo zaufanego kodu w piaskownicy](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="f9101-135">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="f9101-136">Uruchom kod zestawu w trybie pełnego zaufania.</span><span class="sxs-lookup"><span data-stu-id="f9101-136">Run the assembly's code in full trust.</span></span> <span data-ttu-id="f9101-137">W tym celu należy skonfigurować `<loadFromRemoteSources>` element.</span><span class="sxs-lookup"><span data-stu-id="f9101-137">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="f9101-138">Pozwala określić, że zestawy, które działają w częściowej relacji zaufania we wcześniejszych wersjach .NET Framework, są teraz uruchamiane w trybie pełnego zaufania w .NET Framework 4 i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="f9101-138">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9101-139">Jeśli zestaw nie powinien działać w trybie pełnego zaufania, nie ustawiaj tego elementu konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="f9101-139">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="f9101-140">Zamiast tego należy utworzyć piaskownicę, <xref:System.AppDomain> w której ma zostać załadowany zestaw.</span><span class="sxs-lookup"><span data-stu-id="f9101-140">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="f9101-141">`enabled`Atrybut dla `<loadFromRemoteSources>` elementu jest obowiązujący tylko wtedy, gdy zabezpieczenia dostępu kodu (CAS) są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="f9101-141">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="f9101-142">Domyślnie zasady CAS są wyłączone w .NET Framework 4 i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="f9101-142">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="f9101-143">Jeśli ustawisz `enabled` `true` opcję, zdalne zestawy mają przyznane pełne zaufanie.</span><span class="sxs-lookup"><span data-stu-id="f9101-143">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="f9101-144">Jeśli `enabled` parametr nie jest ustawiony na `true` , <xref:System.IO.FileLoadException> zwracany jest następujący warunek:</span><span class="sxs-lookup"><span data-stu-id="f9101-144">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="f9101-145">Zachowanie w piaskownicy bieżącej domeny różni się od zachowania w .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="f9101-145">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="f9101-146">Wymaga to wyłączenia zasad CAS i bieżącej domeny nie należy do piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="f9101-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="f9101-147">Ładowany zestaw nie należy do `MyComputer` strefy.</span><span class="sxs-lookup"><span data-stu-id="f9101-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="f9101-148">Ustawianie `<loadFromRemoteSources>` elementu, aby `true` zapobiec zgłaszaniu tego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="f9101-148">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="f9101-149">Pozwala to określić, że nie korzystasz z aparatu plików wykonywalnych języka wspólnego do piaskownicy załadowanych zestawów pod kątem zabezpieczeń, i że mogą one być wykonywane w trybie pełnego zaufania.</span><span class="sxs-lookup"><span data-stu-id="f9101-149">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="f9101-150">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f9101-150">Notes</span></span>

- <span data-ttu-id="f9101-151">W .NET Framework 4,5 i nowszych wersjach zestawy w lokalnych udziałach sieciowych są domyślnie uruchamiane w trybie pełnego zaufania; nie musisz włączać `<loadFromRemoteSources>` elementu.</span><span class="sxs-lookup"><span data-stu-id="f9101-151">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="f9101-152">Jeśli aplikacja została skopiowana z sieci Web, jest oflagowana przez system Windows jako aplikacja sieci Web, nawet jeśli znajduje się na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="f9101-152">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="f9101-153">Można zmienić to oznaczenie, zmieniając jego właściwości pliku, lub można użyć `<loadFromRemoteSources>` elementu, aby nadać zestawowi pełne zaufanie.</span><span class="sxs-lookup"><span data-stu-id="f9101-153">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="f9101-154">Alternatywnie można użyć <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> metody do załadowania lokalnego zestawu, który został oflagowany przez system operacyjny jako załadowany z sieci Web.</span><span class="sxs-lookup"><span data-stu-id="f9101-154">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="f9101-155">Użytkownik może uzyskać dostęp do <xref:System.IO.FileLoadException> aplikacji działającej w aplikacji na komputerze wirtualnym z systemem Windows.</span><span class="sxs-lookup"><span data-stu-id="f9101-155">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="f9101-156">Taka sytuacja może wystąpić podczas próby załadowania pliku z folderów połączonych na komputerze hostującym.</span><span class="sxs-lookup"><span data-stu-id="f9101-156">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="f9101-157">Może również wystąpić podczas próby załadowania pliku z folderu połączonego za pośrednictwem [usługi pulpitu zdalnego](/windows/win32/termserv/terminal-services-portal) (usługi terminalowe).</span><span class="sxs-lookup"><span data-stu-id="f9101-157">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="f9101-158">Aby uniknąć wyjątku, ustaw `enabled` jako `true` .</span><span class="sxs-lookup"><span data-stu-id="f9101-158">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="f9101-159">Plik konfiguracji</span><span class="sxs-lookup"><span data-stu-id="f9101-159">Configuration file</span></span>

<span data-ttu-id="f9101-160">Ten element jest zazwyczaj używany w pliku konfiguracyjnym aplikacji, ale może być używany w innych plikach konfiguracji w zależności od kontekstu.</span><span class="sxs-lookup"><span data-stu-id="f9101-160">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="f9101-161">Aby uzyskać więcej informacji, zobacz artykuł [bardziej niejawne zastosowania zasad CAS: loadFromRemoteSources](/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) w blogu dotyczącym zabezpieczeń programu .NET.</span><span class="sxs-lookup"><span data-stu-id="f9101-161">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="f9101-162">Przykład</span><span class="sxs-lookup"><span data-stu-id="f9101-162">Example</span></span>

<span data-ttu-id="f9101-163">Poniższy przykład pokazuje, jak udzielić pełnego zaufania do zestawów ładowanych ze źródeł zdalnych.</span><span class="sxs-lookup"><span data-stu-id="f9101-163">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="f9101-164">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f9101-164">See also</span></span>

- [<span data-ttu-id="f9101-165">Bardziej niejawne zastosowania zasad CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="f9101-165">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="f9101-166">Instrukcje: uruchamianie częściowo zaufanego kodu w piaskownicy</span><span class="sxs-lookup"><span data-stu-id="f9101-166">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="f9101-167">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="f9101-167">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f9101-168">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="f9101-168">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
