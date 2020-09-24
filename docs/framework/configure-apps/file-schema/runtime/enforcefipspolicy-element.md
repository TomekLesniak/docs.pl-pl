---
title: <enforceFIPSPolicy> Element
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
ms.openlocfilehash: 864a371d4ad10585e672452ad85cc09d4b684068
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158841"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="96cd3-102">\<enforceFIPSPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="96cd3-102">\<enforceFIPSPolicy> Element</span></span>

<span data-ttu-id="96cd3-103">Określa, czy należy wymusić wymaganie konfiguracji komputera, że algorytmy kryptograficzne muszą być zgodne z FIPS (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="96cd3-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="96cd3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="96cd3-104">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96cd3-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="96cd3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="96cd3-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="96cd3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96cd3-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="96cd3-107">Attributes</span></span>  
  
|<span data-ttu-id="96cd3-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="96cd3-108">Attribute</span></span>|<span data-ttu-id="96cd3-109">Opis</span><span class="sxs-lookup"><span data-stu-id="96cd3-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="96cd3-110">enabled</span><span class="sxs-lookup"><span data-stu-id="96cd3-110">enabled</span></span>|<span data-ttu-id="96cd3-111">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="96cd3-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="96cd3-112">Określa, czy należy włączyć wymuszanie wymagania konfiguracji komputera, że algorytmy kryptograficzne muszą być zgodne ze standardem FIPS.</span><span class="sxs-lookup"><span data-stu-id="96cd3-112">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="96cd3-113">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="96cd3-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="96cd3-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="96cd3-114">Value</span></span>|<span data-ttu-id="96cd3-115">Opis</span><span class="sxs-lookup"><span data-stu-id="96cd3-115">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="96cd3-116">Jeśli komputer jest skonfigurowany tak, aby wymagania algorytmów kryptograficznych były zgodne ze standardem FIPS, to wymaganie jest wymuszane.</span><span class="sxs-lookup"><span data-stu-id="96cd3-116">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="96cd3-117">Jeśli klasa implementuje algorytm, który nie jest zgodny z FIPS, konstruktory lub `Create` metody dla tej klasy generują wyjątki, gdy są uruchamiane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="96cd3-117">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="96cd3-118">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="96cd3-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="96cd3-119">Algorytmy kryptograficzne używane przez aplikację nie są wymagane do zgodności ze standardem FIPS, niezależnie od konfiguracji komputera.</span><span class="sxs-lookup"><span data-stu-id="96cd3-119">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96cd3-120">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="96cd3-120">Child Elements</span></span>  

 <span data-ttu-id="96cd3-121">Brak.</span><span class="sxs-lookup"><span data-stu-id="96cd3-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96cd3-122">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="96cd3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="96cd3-123">Element</span><span class="sxs-lookup"><span data-stu-id="96cd3-123">Element</span></span>|<span data-ttu-id="96cd3-124">Opis</span><span class="sxs-lookup"><span data-stu-id="96cd3-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="96cd3-125">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="96cd3-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="96cd3-126">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="96cd3-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96cd3-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="96cd3-127">Remarks</span></span>  

 <span data-ttu-id="96cd3-128">Począwszy od .NET Framework 2,0, tworzenie klas implementujących algorytmy kryptograficzne jest kontrolowane przez konfigurację komputera.</span><span class="sxs-lookup"><span data-stu-id="96cd3-128">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="96cd3-129">Jeśli komputer jest skonfigurowany tak, aby wymagał zgodności algorytmów z FIPS, a Klasa implementuje algorytm, który nie jest zgodny ze standardem FIPS, każda próba utworzenia wystąpienia tej klasy zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="96cd3-129">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="96cd3-130">Konstruktory zgłaszają <xref:System.InvalidOperationException> wyjątek, a metody zgłaszają `Create` <xref:System.Reflection.TargetInvocationException> wyjątek z <xref:System.InvalidOperationException> wyjątkiem wewnętrznym.</span><span class="sxs-lookup"><span data-stu-id="96cd3-130">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="96cd3-131">Jeśli aplikacja jest uruchamiana na komputerach, których konfiguracje wymagają zgodności ze standardem FIPS, a aplikacja używa algorytmu, który nie jest zgodny z FIPS, można użyć tego elementu w pliku konfiguracji, aby uniemożliwić środowisko uruchomieniowe języka wspólnego (CLR) Wymuszanie zgodności ze standardem FIPS.</span><span class="sxs-lookup"><span data-stu-id="96cd3-131">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="96cd3-132">Ten element został wprowadzony w dodatku Service Pack 1 .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="96cd3-132">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96cd3-133">Przykład</span><span class="sxs-lookup"><span data-stu-id="96cd3-133">Example</span></span>  

 <span data-ttu-id="96cd3-134">Poniższy przykład pokazuje, jak uniemożliwić środowisku CLR Wymuszanie zgodności ze standardem FIPS.</span><span class="sxs-lookup"><span data-stu-id="96cd3-134">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96cd3-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96cd3-135">See also</span></span>

- [<span data-ttu-id="96cd3-136">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="96cd3-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="96cd3-137">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="96cd3-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="96cd3-138">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="96cd3-138">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
