---
title: Element <Crst_DisableSpinWait>
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 45052d99bb297ac39d058fa405fe57a7c991f738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151353"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="2d20c-102">\<Crst_DisableSpinWait>, element</span><span class="sxs-lookup"><span data-stu-id="2d20c-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="2d20c-103">Określa, czy należy wyłączyć funkcję "oczekiwanie" podczas oczekiwania na sekcję krytyczną.</span><span class="sxs-lookup"><span data-stu-id="2d20c-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="2d20c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2d20c-104">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d20c-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="2d20c-105">Attributes and Elements</span></span>

<span data-ttu-id="2d20c-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="2d20c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d20c-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="2d20c-107">Attributes</span></span>  
  
|<span data-ttu-id="2d20c-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="2d20c-108">Attribute</span></span>|<span data-ttu-id="2d20c-109">Opis</span><span class="sxs-lookup"><span data-stu-id="2d20c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d20c-110">**dostępny**</span><span class="sxs-lookup"><span data-stu-id="2d20c-110">**enabled**</span></span>|<span data-ttu-id="2d20c-111">Określa, czy oczekiwanie na przejście na sekcje krytyczne, gdy są one z nimi związane, jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="2d20c-111">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2d20c-112">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="2d20c-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="2d20c-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="2d20c-113">Value</span></span>|<span data-ttu-id="2d20c-114">Opis</span><span class="sxs-lookup"><span data-stu-id="2d20c-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2d20c-115">1</span><span class="sxs-lookup"><span data-stu-id="2d20c-115">1</span></span>|<span data-ttu-id="2d20c-116">Wyłączenie pokrętła — oczekiwanie, jeśli nie można uzyskać sekcji krytycznej.</span><span class="sxs-lookup"><span data-stu-id="2d20c-116">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="2d20c-117">0</span><span class="sxs-lookup"><span data-stu-id="2d20c-117">0</span></span>|<span data-ttu-id="2d20c-118">Nie należy wyłączać elementu "oczekiwanie", jeśli nie można uzyskać sekcji krytycznej.</span><span class="sxs-lookup"><span data-stu-id="2d20c-118">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="2d20c-119">Jest to wartość domyślna.</span><span class="sxs-lookup"><span data-stu-id="2d20c-119">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d20c-120">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="2d20c-120">Child Elements</span></span>  

 <span data-ttu-id="2d20c-121">Brak.</span><span class="sxs-lookup"><span data-stu-id="2d20c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d20c-122">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="2d20c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2d20c-123">Element</span><span class="sxs-lookup"><span data-stu-id="2d20c-123">Element</span></span>|<span data-ttu-id="2d20c-124">Opis</span><span class="sxs-lookup"><span data-stu-id="2d20c-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2d20c-125">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2d20c-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2d20c-126">Zawiera informacje o różnych ustawieniach konfiguracji środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="2d20c-126">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2d20c-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="2d20c-127">Example</span></span>  

<span data-ttu-id="2d20c-128">W poniższym przykładzie jest wyłączone obracanie w sekcji o kluczowym znaczeniu.</span><span class="sxs-lookup"><span data-stu-id="2d20c-128">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d20c-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2d20c-129">See also</span></span>

- [<span data-ttu-id="2d20c-130">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="2d20c-130">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2d20c-131">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="2d20c-131">Configuration File Schema</span></span>](../index.md)
