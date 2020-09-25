---
title: <disableCommitThreadStack> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
ms.openlocfilehash: f717f57fe8670b126ed1468713a2114aaa772762
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198993"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="2a780-102">\<disableCommitThreadStack> Element</span><span class="sxs-lookup"><span data-stu-id="2a780-102">\<disableCommitThreadStack> Element</span></span>

<span data-ttu-id="2a780-103">Określa, czy pełny stos wątków jest zatwierdzany podczas uruchamiania wątku.</span><span class="sxs-lookup"><span data-stu-id="2a780-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**  
  
## <a name="syntax"></a><span data-ttu-id="2a780-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2a780-104">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a780-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="2a780-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2a780-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="2a780-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a780-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="2a780-107">Attributes</span></span>  
  
|<span data-ttu-id="2a780-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="2a780-108">Attribute</span></span>|<span data-ttu-id="2a780-109">Opis</span><span class="sxs-lookup"><span data-stu-id="2a780-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a780-110">enabled</span><span class="sxs-lookup"><span data-stu-id="2a780-110">enabled</span></span>|<span data-ttu-id="2a780-111">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="2a780-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="2a780-112">Określa, czy zatwierdzanie pełnego stosu wątków podczas uruchamiania wątku (zachowanie domyślne) jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="2a780-112">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2a780-113">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="2a780-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="2a780-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="2a780-114">Value</span></span>|<span data-ttu-id="2a780-115">Opis</span><span class="sxs-lookup"><span data-stu-id="2a780-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2a780-116">0</span><span class="sxs-lookup"><span data-stu-id="2a780-116">0</span></span>|<span data-ttu-id="2a780-117">Nie należy wyłączać domyślnego zachowania środowiska uruchomieniowego języka wspólnego, czyli zatwierdzić pełny stos wątków podczas uruchamiania wątku.</span><span class="sxs-lookup"><span data-stu-id="2a780-117">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="2a780-118">1</span><span class="sxs-lookup"><span data-stu-id="2a780-118">1</span></span>|<span data-ttu-id="2a780-119">Wyłączenie domyślnego zachowania środowiska uruchomieniowego języka wspólnego, które polega na zatwierdzeniu pełnego stosu wątków podczas uruchamiania wątku.</span><span class="sxs-lookup"><span data-stu-id="2a780-119">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a780-120">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="2a780-120">Child Elements</span></span>  

 <span data-ttu-id="2a780-121">Brak.</span><span class="sxs-lookup"><span data-stu-id="2a780-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a780-122">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="2a780-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2a780-123">Element</span><span class="sxs-lookup"><span data-stu-id="2a780-123">Element</span></span>|<span data-ttu-id="2a780-124">Opis</span><span class="sxs-lookup"><span data-stu-id="2a780-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2a780-125">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2a780-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2a780-126">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="2a780-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a780-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2a780-127">Remarks</span></span>  

 <span data-ttu-id="2a780-128">Domyślne zachowanie środowiska uruchomieniowego języka wspólnego polega na zatwierdzeniu pełnego stosu wątków podczas uruchamiania wątku.</span><span class="sxs-lookup"><span data-stu-id="2a780-128">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="2a780-129">Jeśli na serwerze, który ma ograniczoną ilość pamięci, należy utworzyć dużą liczbę wątków, a większość z nich będzie używać bardzo małej ilości miejsca na stosie, serwer może działać lepiej, jeśli środowisko uruchomieniowe języka wspólnego nie zatwierdzi pełnego stosu wątków natychmiast po rozpoczęciu wątku.</span><span class="sxs-lookup"><span data-stu-id="2a780-129">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a780-130">Hosty niezarządzane mogą używać `STARTUP_DISABLE_COMMITTHREADSTACK` flagi uruchamiania w wyliczeniu [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) , aby osiągnąć ten sam wynik.</span><span class="sxs-lookup"><span data-stu-id="2a780-130">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a780-131">Przykład</span><span class="sxs-lookup"><span data-stu-id="2a780-131">Example</span></span>  

 <span data-ttu-id="2a780-132">Poniższy przykład pokazuje, jak wyłączyć domyślne zachowanie środowiska uruchomieniowego języka wspólnego, czyli zatwierdzić pełny stos wątków podczas uruchamiania wątku.</span><span class="sxs-lookup"><span data-stu-id="2a780-132">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a780-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2a780-133">See also</span></span>

- [<span data-ttu-id="2a780-134">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="2a780-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2a780-135">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="2a780-135">Configuration File Schema</span></span>](../index.md)
