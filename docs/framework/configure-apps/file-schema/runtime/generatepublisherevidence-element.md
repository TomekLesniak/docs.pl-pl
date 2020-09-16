---
title: <generatePublisherEvidence> Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 11592b055641c0fa2d2b968547dcc5aa40c94600
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541787"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="e6448-102">\<generatePublisherEvidence> Element</span><span class="sxs-lookup"><span data-stu-id="e6448-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="e6448-103">Określa, czy środowisko uruchomieniowe tworzy <xref:System.Security.Policy.Publisher> dowód dla zabezpieczeń dostępu kodu (CAS).</span><span class="sxs-lookup"><span data-stu-id="e6448-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a><span data-ttu-id="e6448-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e6448-104">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6448-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e6448-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e6448-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e6448-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6448-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e6448-107">Attributes</span></span>  
  
|<span data-ttu-id="e6448-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="e6448-108">Attribute</span></span>|<span data-ttu-id="e6448-109">Opis</span><span class="sxs-lookup"><span data-stu-id="e6448-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e6448-110">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="e6448-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="e6448-111">Określa, czy środowisko uruchomieniowe tworzy <xref:System.Security.Policy.Publisher> dowód.</span><span class="sxs-lookup"><span data-stu-id="e6448-111">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e6448-112">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="e6448-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="e6448-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="e6448-113">Value</span></span>|<span data-ttu-id="e6448-114">Opis</span><span class="sxs-lookup"><span data-stu-id="e6448-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e6448-115">Nie tworzy <xref:System.Security.Policy.Publisher> dowodów.</span><span class="sxs-lookup"><span data-stu-id="e6448-115">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="e6448-116">Tworzy <xref:System.Security.Policy.Publisher> dowód.</span><span class="sxs-lookup"><span data-stu-id="e6448-116">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="e6448-117">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="e6448-117">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6448-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e6448-118">Child Elements</span></span>  
 <span data-ttu-id="e6448-119">Brak.</span><span class="sxs-lookup"><span data-stu-id="e6448-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6448-120">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e6448-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e6448-121">Element</span><span class="sxs-lookup"><span data-stu-id="e6448-121">Element</span></span>|<span data-ttu-id="e6448-122">Opis</span><span class="sxs-lookup"><span data-stu-id="e6448-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e6448-123">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6448-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e6448-124">Zawiera informacje dotyczące opcji inicjowania środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="e6448-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6448-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e6448-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6448-126">W .NET Framework 4 i nowszych ten element nie ma wpływu na czasy ładowania zestawu.</span><span class="sxs-lookup"><span data-stu-id="e6448-126">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="e6448-127">Aby uzyskać więcej informacji, zobacz sekcję "uproszczenie zasad zabezpieczeń" w temacie [zmiany zabezpieczeń](/previous-versions/dotnet/framework/security/security-changes).</span><span class="sxs-lookup"><span data-stu-id="e6448-127">For more information, see the "Security Policy Simplification" section in [Security Changes](/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="e6448-128">Środowisko uruchomieniowe języka wspólnego (CLR) próbuje zweryfikować podpis Authenticode w czasie ładowania, aby utworzyć <xref:System.Security.Policy.Publisher> dowód dla zestawu.</span><span class="sxs-lookup"><span data-stu-id="e6448-128">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="e6448-129">Jednak domyślnie większość aplikacji nie potrzebuje <xref:System.Security.Policy.Publisher> dowodu.</span><span class="sxs-lookup"><span data-stu-id="e6448-129">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="e6448-130">Standardowe zasady CAS nie bazują na <xref:System.Security.Policy.PublisherMembershipCondition> .</span><span class="sxs-lookup"><span data-stu-id="e6448-130">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="e6448-131">Należy unikać niepotrzebnego kosztu uruchomienia związanego z weryfikacją podpisu wydawcy, chyba że aplikacja jest wykonywana na komputerze z niestandardowymi zasadami CAS lub nie spełnia wymagań dotyczących <xref:System.Security.Permissions.PublisherIdentityPermission> w środowisku częściowego zaufania.</span><span class="sxs-lookup"><span data-stu-id="e6448-131">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="e6448-132">(Wymagania dotyczące uprawnień tożsamości zawsze powiodło się w środowisku pełnego zaufania).</span><span class="sxs-lookup"><span data-stu-id="e6448-132">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6448-133">Zalecamy, aby usługi korzystały z `<generatePublisherEvidence>` elementu, aby zwiększyć wydajność uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="e6448-133">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="e6448-134">Za pomocą tego elementu można także uniknąć opóźnień, które mogą spowodować przekroczenie limitu czasu i anulowanie uruchamiania usługi.</span><span class="sxs-lookup"><span data-stu-id="e6448-134">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="e6448-135">Plik konfiguracji</span><span class="sxs-lookup"><span data-stu-id="e6448-135">Configuration File</span></span>  
 <span data-ttu-id="e6448-136">Tego elementu można używać tylko w pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e6448-136">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6448-137">Przykład</span><span class="sxs-lookup"><span data-stu-id="e6448-137">Example</span></span>  
 <span data-ttu-id="e6448-138">Poniższy przykład pokazuje, jak użyć elementu, `<generatePublisherEvidence>` Aby wyłączyć sprawdzanie zasad wydawcy CAS dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e6448-138">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6448-139">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e6448-139">See also</span></span>

- [<span data-ttu-id="e6448-140">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="e6448-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e6448-141">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="e6448-141">Configuration File Schema</span></span>](../index.md)
