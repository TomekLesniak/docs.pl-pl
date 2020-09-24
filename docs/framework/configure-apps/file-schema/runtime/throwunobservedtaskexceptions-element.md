---
title: <ThrowUnobservedTaskExceptions> Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
ms.openlocfilehash: 012c2e70e66015bc317606a7eea07812b5df26e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183926"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="e8bee-102">\<ThrowUnobservedTaskExceptions> Element</span><span class="sxs-lookup"><span data-stu-id="e8bee-102">\<ThrowUnobservedTaskExceptions> Element</span></span>

<span data-ttu-id="e8bee-103">Określa, czy Nieobsłużone wyjątki zadań powinny kończyć uruchomiony proces.</span><span class="sxs-lookup"><span data-stu-id="e8bee-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**  
  
## <a name="syntax"></a><span data-ttu-id="e8bee-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e8bee-104">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8bee-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e8bee-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e8bee-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e8bee-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8bee-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e8bee-107">Attributes</span></span>  
  
|<span data-ttu-id="e8bee-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="e8bee-108">Attribute</span></span>|<span data-ttu-id="e8bee-109">Opis</span><span class="sxs-lookup"><span data-stu-id="e8bee-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e8bee-110">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="e8bee-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="e8bee-111">Określa, czy Nieobsłużone wyjątki zadań powinny kończyć uruchomiony proces.</span><span class="sxs-lookup"><span data-stu-id="e8bee-111">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e8bee-112">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="e8bee-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="e8bee-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="e8bee-113">Value</span></span>|<span data-ttu-id="e8bee-114">Opis</span><span class="sxs-lookup"><span data-stu-id="e8bee-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e8bee-115">Nie przerywa uruchomionego procesu dla nieobsłużonego wyjątku zadania.</span><span class="sxs-lookup"><span data-stu-id="e8bee-115">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="e8bee-116">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="e8bee-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="e8bee-117">Kończy uruchomiony proces dla nieobsłużonego wyjątku zadania.</span><span class="sxs-lookup"><span data-stu-id="e8bee-117">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8bee-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e8bee-118">Child Elements</span></span>  

 <span data-ttu-id="e8bee-119">Brak.</span><span class="sxs-lookup"><span data-stu-id="e8bee-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8bee-120">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e8bee-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e8bee-121">Element</span><span class="sxs-lookup"><span data-stu-id="e8bee-121">Element</span></span>|<span data-ttu-id="e8bee-122">Opis</span><span class="sxs-lookup"><span data-stu-id="e8bee-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e8bee-123">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8bee-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e8bee-124">Zawiera informacje dotyczące opcji inicjowania środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="e8bee-124">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="e8bee-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e8bee-125">Remarks</span></span>  

 <span data-ttu-id="e8bee-126">Jeśli nie zaobserwowano wyjątku, który jest skojarzony z programem, nie ma <xref:System.Threading.Tasks.Task> żadnej <xref:System.Threading.Tasks.Task.Wait%2A> operacji, element nadrzędny nie jest dołączony i <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> Właściwość nie została odczytana, ponieważ wyjątek zadania jest traktowany jako nieobserwowany.</span><span class="sxs-lookup"><span data-stu-id="e8bee-126">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="e8bee-127">W .NET Framework 4 domyślnie, jeśli dla, <xref:System.Threading.Tasks.Task> który ma niezauważalny wyjątek jest odzyskiwany, finalizator zgłasza wyjątek i kończy proces.</span><span class="sxs-lookup"><span data-stu-id="e8bee-127">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="e8bee-128">Zakończenie procesu zależy od chronometrażu wyrzucania elementów bezużytecznych i finalizacji.</span><span class="sxs-lookup"><span data-stu-id="e8bee-128">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="e8bee-129">Aby ułatwić deweloperom pisanie kodu asynchronicznego na podstawie zadań, .NET Framework 4,5 zmienia to zachowanie domyślne dla nieobserwowanych wyjątków.</span><span class="sxs-lookup"><span data-stu-id="e8bee-129">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="e8bee-130">Niezauważalne wyjątki nadal powodują <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> , że zdarzenie zostanie wywołane, ale domyślnie proces nie zostanie zakończony.</span><span class="sxs-lookup"><span data-stu-id="e8bee-130">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="e8bee-131">Zamiast tego wyjątek jest ignorowany po wywołaniu zdarzenia, niezależnie od tego, czy program obsługi zdarzeń obserwuje wyjątek.</span><span class="sxs-lookup"><span data-stu-id="e8bee-131">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="e8bee-132">W .NET Framework 4,5 można użyć [ \<ThrowUnobservedTaskExceptions> elementu](throwunobservedtaskexceptions-element.md) w pliku konfiguracyjnym aplikacji, aby włączyć .NET Framework 4 zachowanie zgłaszania wyjątku.</span><span class="sxs-lookup"><span data-stu-id="e8bee-132">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="e8bee-133">Możesz również określić zachowanie wyjątku w jeden z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="e8bee-133">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="e8bee-134">Ustawiając zmienną środowiskową `COMPlus_ThrowUnobservedTaskExceptions` ( `set COMPlus_ThrowUnobservedTaskExceptions=1` ).</span><span class="sxs-lookup"><span data-stu-id="e8bee-134">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="e8bee-135">Ustawiając wartość DWORD rejestru ThrowUnobservedTaskExceptions = 1 w HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft \\ . Klucz NETFramework.</span><span class="sxs-lookup"><span data-stu-id="e8bee-135">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8bee-136">Przykład</span><span class="sxs-lookup"><span data-stu-id="e8bee-136">Example</span></span>  

 <span data-ttu-id="e8bee-137">Poniższy przykład pokazuje, jak włączyć zgłaszanie wyjątków w zadaniach przy użyciu pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e8bee-137">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="e8bee-138">Przykład</span><span class="sxs-lookup"><span data-stu-id="e8bee-138">Example</span></span>  

 <span data-ttu-id="e8bee-139">Poniższy przykład demonstruje, jak wyjątek niezauważalny jest generowany z zadania.</span><span class="sxs-lookup"><span data-stu-id="e8bee-139">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="e8bee-140">Aby program działał prawidłowo, kod musi być uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="e8bee-140">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e8bee-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e8bee-141">See also</span></span>

- [<span data-ttu-id="e8bee-142">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="e8bee-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e8bee-143">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="e8bee-143">Configuration File Schema</span></span>](../index.md)
