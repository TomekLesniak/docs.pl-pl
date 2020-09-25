---
title: <publisherPolicy> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
ms.openlocfilehash: bd6ab1123ef3f84f7e8a06b25ce48aed37e4bef7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195262"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="37925-102">\<publisherPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="37925-102">\<publisherPolicy> Element</span></span>

<span data-ttu-id="37925-103">Określa, czy środowisko uruchomieniowe stosuje zasady wydawcy.</span><span class="sxs-lookup"><span data-stu-id="37925-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="37925-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="37925-104">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37925-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="37925-105">Attributes and Elements</span></span>  

 <span data-ttu-id="37925-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="37925-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37925-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="37925-107">Attributes</span></span>  
  
|<span data-ttu-id="37925-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="37925-108">Attribute</span></span>|<span data-ttu-id="37925-109">Opis</span><span class="sxs-lookup"><span data-stu-id="37925-109">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="37925-110">Określa, czy mają być stosowane zasady wydawcy.</span><span class="sxs-lookup"><span data-stu-id="37925-110">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="37925-111">Zastosuj atrybut</span><span class="sxs-lookup"><span data-stu-id="37925-111">apply Attribute</span></span>  
  
|<span data-ttu-id="37925-112">Wartość</span><span class="sxs-lookup"><span data-stu-id="37925-112">Value</span></span>|<span data-ttu-id="37925-113">Opis</span><span class="sxs-lookup"><span data-stu-id="37925-113">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="37925-114">Stosuje zasady wydawcy.</span><span class="sxs-lookup"><span data-stu-id="37925-114">Applies publisher policy.</span></span> <span data-ttu-id="37925-115">Jest to ustawienie domyślne.</span><span class="sxs-lookup"><span data-stu-id="37925-115">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="37925-116">Nie stosuje zasad wydawcy.</span><span class="sxs-lookup"><span data-stu-id="37925-116">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37925-117">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="37925-117">Child Elements</span></span>  

<span data-ttu-id="37925-118">Brak.</span><span class="sxs-lookup"><span data-stu-id="37925-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37925-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="37925-119">Parent Elements</span></span>  
  
|<span data-ttu-id="37925-120">Element</span><span class="sxs-lookup"><span data-stu-id="37925-120">Element</span></span>|<span data-ttu-id="37925-121">Opis</span><span class="sxs-lookup"><span data-stu-id="37925-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="37925-122">Zawiera informacje o przekierowaniu wersji zestawu i lokalizacji zestawów.</span><span class="sxs-lookup"><span data-stu-id="37925-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="37925-123">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="37925-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="37925-124">Hermetyzuje zasady powiązań oraz lokalizację zestawu dla każdego zestawu.</span><span class="sxs-lookup"><span data-stu-id="37925-124">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="37925-125">Użyj jednego `<dependentAssembly>` elementu dla każdego zestawu.</span><span class="sxs-lookup"><span data-stu-id="37925-125">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="37925-126">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="37925-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37925-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="37925-127">Remarks</span></span>  

 <span data-ttu-id="37925-128">Gdy dostawca składnika zwalnia nową wersję zestawu, dostawca może uwzględnić zasady wydawcy, aby aplikacje używające starej wersji używały teraz nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="37925-128">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="37925-129">Aby określić, czy zastosować zasady wydawcy dla określonego zestawu, umieść **\<publisherPolicy>** element w **\<dependentAssembly>** elemencie.</span><span class="sxs-lookup"><span data-stu-id="37925-129">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="37925-130">Ustawieniem domyślnym dla atrybutu **apply** jest **tak**.</span><span class="sxs-lookup"><span data-stu-id="37925-130">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="37925-131">Ustawienie atrybutu **Zastosuj** do **nie** zastępuje żadnych poprzednich ustawień **tak** dla zestawu.</span><span class="sxs-lookup"><span data-stu-id="37925-131">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="37925-132">Aby aplikacja jawnie ignorował zasady wydawcy przy użyciu [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) elementu w pliku konfiguracyjnym aplikacji, wymagane jest uprawnienie.</span><span class="sxs-lookup"><span data-stu-id="37925-132">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="37925-133">Uprawnienie jest udzielane przez ustawienie <xref:System.Security.Permissions.SecurityPermissionFlag> flagi na <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="37925-133">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="37925-134">Aby uzyskać więcej informacji, zobacz [uprawnienia zabezpieczeń przekierowania powiązania zestawu](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="37925-134">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37925-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="37925-135">Example</span></span>  

 <span data-ttu-id="37925-136">Poniższy przykład powoduje wyłączenie zasad wydawcy dla zestawu `myAssembly` .</span><span class="sxs-lookup"><span data-stu-id="37925-136">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="37925-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="37925-137">See also</span></span>

- [<span data-ttu-id="37925-138">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="37925-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="37925-139">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="37925-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="37925-140">Sposoby lokalizowania zestawów przez środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="37925-140">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="37925-141">Przekierowywanie wersji zestawu</span><span class="sxs-lookup"><span data-stu-id="37925-141">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
