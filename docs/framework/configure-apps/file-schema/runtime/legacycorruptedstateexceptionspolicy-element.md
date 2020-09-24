---
title: <legacyCorruptedStateExceptionsPolicy> Element
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: f36e27a1b85cff2ba8c7e838bace37890a5aa760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151210"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="8e781-102">\<legacyCorruptedStateExceptionsPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="8e781-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>

<span data-ttu-id="8e781-103">Określa, czy środowisko uruchomieniowe języka wspólnego umożliwia kodowi zarządzanemu przechwytywanie naruszeń dostępu i innych wyjątków uszkodzonych Stanów.</span><span class="sxs-lookup"><span data-stu-id="8e781-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="8e781-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8e781-104">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e781-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="8e781-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8e781-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="8e781-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e781-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="8e781-107">Attributes</span></span>  
  
|<span data-ttu-id="8e781-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="8e781-108">Attribute</span></span>|<span data-ttu-id="8e781-109">Opis</span><span class="sxs-lookup"><span data-stu-id="8e781-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8e781-110">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="8e781-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="8e781-111">Określa, że aplikacja będzie przechwytywać błędy wyjątku stanu, takie jak naruszenia zasad dostępu.</span><span class="sxs-lookup"><span data-stu-id="8e781-111">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8e781-112">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="8e781-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="8e781-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="8e781-113">Value</span></span>|<span data-ttu-id="8e781-114">Opis</span><span class="sxs-lookup"><span data-stu-id="8e781-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8e781-115">Aplikacja nie będzie przechwytywać uszkodzonych błędów wyjątku stanu, takich jak naruszenia zasad dostępu.</span><span class="sxs-lookup"><span data-stu-id="8e781-115">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="8e781-116">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="8e781-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="8e781-117">Aplikacja będzie przechwycić błędy wyjątku stanu, takie jak naruszenia zasad dostępu.</span><span class="sxs-lookup"><span data-stu-id="8e781-117">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e781-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="8e781-118">Child Elements</span></span>  

 <span data-ttu-id="8e781-119">Brak.</span><span class="sxs-lookup"><span data-stu-id="8e781-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e781-120">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="8e781-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8e781-121">Element</span><span class="sxs-lookup"><span data-stu-id="8e781-121">Element</span></span>|<span data-ttu-id="8e781-122">Opis</span><span class="sxs-lookup"><span data-stu-id="8e781-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8e781-123">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e781-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8e781-124">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="8e781-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e781-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8e781-125">Remarks</span></span>  

 <span data-ttu-id="8e781-126">W .NET Framework w wersji 3,5 i starszych środowisko uruchomieniowe języka wspólnego może przechwytywać wyjątki, które zostały zgłoszone przez uszkodzone Stany procesów.</span><span class="sxs-lookup"><span data-stu-id="8e781-126">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="8e781-127">Naruszenie zasad dostępu jest przykładem tego typu wyjątku.</span><span class="sxs-lookup"><span data-stu-id="8e781-127">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="8e781-128">Począwszy od .NET Framework 4, kod zarządzany nie przechwytuje już tych typów wyjątków w `catch` blokach.</span><span class="sxs-lookup"><span data-stu-id="8e781-128">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="8e781-129">Można jednak zastąpić tę zmianę i zachować obsługę wyjątków uszkodzonych Stanów na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="8e781-129">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="8e781-130">Ustaw `<legacyCorruptedStateExceptionsPolicy>` `enabled` atrybut elementu na `true` .</span><span class="sxs-lookup"><span data-stu-id="8e781-130">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="8e781-131">To ustawienie konfiguracji jest stosowane processwide i ma wpływ na wszystkie metody.</span><span class="sxs-lookup"><span data-stu-id="8e781-131">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="8e781-132">-lub-</span><span class="sxs-lookup"><span data-stu-id="8e781-132">-or-</span></span>  
  
- <span data-ttu-id="8e781-133">Zastosuj <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> atrybut do metody, która zawiera `catch` blok wyjątków.</span><span class="sxs-lookup"><span data-stu-id="8e781-133">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="8e781-134">Ten element konfiguracji jest dostępny tylko w .NET Framework 4 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="8e781-134">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e781-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="8e781-135">Example</span></span>  

 <span data-ttu-id="8e781-136">Poniższy przykład pokazuje, jak określić, że aplikacja ma zostać przywrócona do zachowania przed .NET Framework 4 i przechwycić wszystkie błędy wyjątków spowodowanych uszkodzeniem stanu.</span><span class="sxs-lookup"><span data-stu-id="8e781-136">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e781-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8e781-137">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="8e781-138">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="8e781-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8e781-139">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="8e781-139">Configuration File Schema</span></span>](../index.md)
