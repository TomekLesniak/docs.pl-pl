---
title: <applicationPool>, element (ustawienia internetowe)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: ca474cdcaeaac7b1c32efa5c58f4b5bb5b7f7895
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557245"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="c0f1f-102">\<applicationPool>, element (ustawienia internetowe)</span><span class="sxs-lookup"><span data-stu-id="c0f1f-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="c0f1f-103">Określa ustawienia konfiguracji, które są używane przez ASP.NET do zarządzania zachowaniem całego procesu, gdy aplikacja ASP.NET działa w trybie zintegrowanym w usługach IIS 7,0 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c0f1f-104">Ten element i funkcja, które obsługuje, działają tylko wtedy, gdy aplikacja ASP.NET jest hostowana w usługach IIS 7,0 lub nowszych.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**  
  
## <a name="syntax"></a><span data-ttu-id="c0f1f-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c0f1f-105">Syntax</span></span>  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0f1f-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c0f1f-106">Attributes and Elements</span></span>  

<span data-ttu-id="c0f1f-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0f1f-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c0f1f-108">Attributes</span></span>  
  
|<span data-ttu-id="c0f1f-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="c0f1f-109">Attribute</span></span>|<span data-ttu-id="c0f1f-110">Opis</span><span class="sxs-lookup"><span data-stu-id="c0f1f-110">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="c0f1f-111">Określa liczbę równoczesnych żądań ASP.NET na procesor CPU.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-111">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="c0f1f-112">Określa, ile równoczesnych wątków może być uruchomionych dla puli aplikacji dla każdego procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-112">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="c0f1f-113">Zapewnia to alternatywny sposób kontrolowania współbieżności ASP.NET, ponieważ można ograniczyć liczbę zarządzanych wątków, które mogą być używane na potrzeby procesora, aby obsłużyć żądania.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-113">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="c0f1f-114">Domyślnie to ustawienie ma wartość 0, co oznacza, że ASP.NET nie ogranicza liczby wątków, które mogą być tworzone na procesor, chociaż Pula wątków CLR ogranicza liczbę wątków, które można utworzyć.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-114">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="c0f1f-115">Określa maksymalną liczbę żądań, które mogą być umieszczone w kolejce dla ASP.NET w pojedynczym procesie.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-115">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="c0f1f-116">Gdy co najmniej dwie aplikacje ASP.NET są uruchamiane w jednej puli aplikacji, zestaw zbiorczy żądań wysyłanych do dowolnej aplikacji w puli aplikacji podlega temu ustawieniu.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-116">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0f1f-117">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c0f1f-117">Child Elements</span></span>  
 <span data-ttu-id="c0f1f-118">Brak.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0f1f-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c0f1f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c0f1f-120">Element</span><span class="sxs-lookup"><span data-stu-id="c0f1f-120">Element</span></span>|<span data-ttu-id="c0f1f-121">Opis</span><span class="sxs-lookup"><span data-stu-id="c0f1f-121">Description</span></span>|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|<span data-ttu-id="c0f1f-122">Zawiera informacje o tym, jak ASP.NET współdziała z aplikacją hosta.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-122">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0f1f-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c0f1f-123">Remarks</span></span>  

<span data-ttu-id="c0f1f-124">Po uruchomieniu usług IIS 7,0 lub nowszej wersji w trybie zintegrowanym Ta kombinacja elementów umożliwia skonfigurowanie sposobu, w jaki ASP.NET zarządza wątkami i kolejkami żądań, gdy aplikacja jest hostowana w puli aplikacji IIS.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-124">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="c0f1f-125">W przypadku uruchomienia usług IIS 6 lub uruchamiania usług IIS 7,0 w trybie klasycznym lub w trybie ISAPI te ustawienia są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-125">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="c0f1f-126">`applicationPool`Ustawienia dotyczą wszystkich pul aplikacji, które są uruchamiane w określonej wersji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-126">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="c0f1f-127">Ustawienia są zawarte w pliku aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-127">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="c0f1f-128">Istnieje wersja tego pliku dla wersji 2,0 i 4,0 .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-128">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="c0f1f-129">(Wersje 3,0 i 3,5 .NET Framework współdzielą plik aspnet.config z wersją 2,0).</span><span class="sxs-lookup"><span data-stu-id="c0f1f-129">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c0f1f-130">W przypadku uruchamiania usług IIS 7,0 w systemie Windows 7 można skonfigurować oddzielny plik aspnet.config dla każdej puli aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-130">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="c0f1f-131">Pozwala to na dostosowanie wydajności wątków dla każdej puli aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-131">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="c0f1f-132">Dla `maxConcurrentRequestsPerCPU` Ustawienia domyślne ustawienie "5000" w .NET Framework 4 skutecznie wyłącza ograniczanie żądań, które jest kontrolowane przez ASP.NET, chyba że rzeczywiście masz 5000 lub więcej żądań na procesor.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-132">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="c0f1f-133">Ustawienie domyślne jest zależne od tego, czy w puli wątków CLR w celu automatycznego zarządzania współbieżnością na procesor CPU.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-133">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="c0f1f-134">Aplikacje, które znacznie wykorzystują asynchroniczne przetwarzanie żądań lub mają wiele długotrwałych żądań zablokowanych we/wy sieci, będą korzystać z zwiększonego limitu domyślnego w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-134">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="c0f1f-135">Ustawienie `maxConcurrentRequestsPerCPU` wartości zero powoduje wyłączenie używania zarządzanych wątków do przetwarzania żądań ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-135">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="c0f1f-136">Gdy aplikacja jest uruchamiana w puli aplikacji IIS, żądania pozostają w wątku we/wy usług IIS i w związku z tym współbieżność jest ograniczana przez ustawienia wątku IIS.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-136">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="c0f1f-137">`requestQueueLimit`Ustawienie działa tak samo jak `requestQueueLimit` atrybut elementu [processModel](/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) , który jest ustawiany w plikach Web.config dla aplikacji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-137">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="c0f1f-138">Jednak `requestQueueLimit` ustawienie w pliku aspnet.config przesłania `requestQueueLimit` Ustawienia w pliku Web.config.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-138">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="c0f1f-139">Innymi słowy, jeśli oba atrybuty są ustawione (domyślnie jest to prawdziwe), `requestQueueLimit` ustawienie w pliku aspnet.config ma pierwszeństwo.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-139">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0f1f-140">Przykład</span><span class="sxs-lookup"><span data-stu-id="c0f1f-140">Example</span></span>  

<span data-ttu-id="c0f1f-141">Poniższy przykład pokazuje, jak skonfigurować zachowanie ASP.NET całego procesu w pliku aspnet.config w następujących okolicznościach:</span><span class="sxs-lookup"><span data-stu-id="c0f1f-141">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="c0f1f-142">Aplikacja jest hostowana w puli aplikacji usług IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-142">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="c0f1f-143">Usługi IIS 7,0 są uruchomione w trybie zintegrowanym.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-143">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="c0f1f-144">Aplikacja korzysta z .NET Framework 3,5 z dodatkiem SP1 lub nowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-144">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="c0f1f-145">Wartości w przykładzie są wartościami domyślnymi.</span><span class="sxs-lookup"><span data-stu-id="c0f1f-145">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="c0f1f-146">Informacje o elementach</span><span class="sxs-lookup"><span data-stu-id="c0f1f-146">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c0f1f-147">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="c0f1f-147">Namespace</span></span>||  
|<span data-ttu-id="c0f1f-148">Nazwa schematu</span><span class="sxs-lookup"><span data-stu-id="c0f1f-148">Schema Name</span></span>||  
|<span data-ttu-id="c0f1f-149">Plik walidacji</span><span class="sxs-lookup"><span data-stu-id="c0f1f-149">Validation File</span></span>||  
|<span data-ttu-id="c0f1f-150">Może być puste</span><span class="sxs-lookup"><span data-stu-id="c0f1f-150">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="c0f1f-151">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c0f1f-151">See also</span></span>

- [<span data-ttu-id="c0f1f-152">\<system.web> — Element (Ustawienia sieci Web)</span><span class="sxs-lookup"><span data-stu-id="c0f1f-152">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
