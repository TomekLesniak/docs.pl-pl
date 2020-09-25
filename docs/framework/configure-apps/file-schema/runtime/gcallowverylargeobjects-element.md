---
title: <gcAllowVeryLargeObjects> Element
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 78a42596aae6c3ea0d94ac759d11ed52d0ace539
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178232"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="3b20d-102">\<gcAllowVeryLargeObjects> Element</span><span class="sxs-lookup"><span data-stu-id="3b20d-102">\<gcAllowVeryLargeObjects> Element</span></span>

<span data-ttu-id="3b20d-103">Na platformach 64-bitowych program umożliwia korzystanie z tablic o rozmiarze większym niż 2 gigabajty (GB).</span><span class="sxs-lookup"><span data-stu-id="3b20d-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="3b20d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3b20d-104">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b20d-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="3b20d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3b20d-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="3b20d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b20d-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="3b20d-107">Attributes</span></span>  
  
|<span data-ttu-id="3b20d-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="3b20d-108">Attribute</span></span>|<span data-ttu-id="3b20d-109">Opis</span><span class="sxs-lookup"><span data-stu-id="3b20d-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3b20d-110">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="3b20d-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="3b20d-111">Określa, czy tablice o rozmiarze większym niż 2 GB są włączone na platformach 64-bitowych.</span><span class="sxs-lookup"><span data-stu-id="3b20d-111">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3b20d-112">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="3b20d-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="3b20d-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="3b20d-113">Value</span></span>|<span data-ttu-id="3b20d-114">Opis</span><span class="sxs-lookup"><span data-stu-id="3b20d-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3b20d-115">Tablice o rozmiarze większym niż 2 GB nie są włączone.</span><span class="sxs-lookup"><span data-stu-id="3b20d-115">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="3b20d-116">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="3b20d-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="3b20d-117">Tablice o rozmiarze większym niż 2 GB są włączone na platformach 64-bitowych.</span><span class="sxs-lookup"><span data-stu-id="3b20d-117">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b20d-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="3b20d-118">Child Elements</span></span>  

 <span data-ttu-id="3b20d-119">Brak.</span><span class="sxs-lookup"><span data-stu-id="3b20d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3b20d-120">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="3b20d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3b20d-121">Element</span><span class="sxs-lookup"><span data-stu-id="3b20d-121">Element</span></span>|<span data-ttu-id="3b20d-122">Opis</span><span class="sxs-lookup"><span data-stu-id="3b20d-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3b20d-123">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3b20d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3b20d-124">Zawiera informacje dotyczące opcji inicjowania środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="3b20d-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b20d-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3b20d-125">Remarks</span></span>  

 <span data-ttu-id="3b20d-126">Użycie tego elementu w pliku konfiguracji aplikacji umożliwia korzystanie z tablic o rozmiarze większym niż 2 GB, ale nie powoduje zmiany innych limitów rozmiaru obiektu lub rozmiaru tablicy:</span><span class="sxs-lookup"><span data-stu-id="3b20d-126">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="3b20d-127">Maksymalna liczba elementów w tablicy to <xref:System.UInt32.MaxValue?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3b20d-127">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="3b20d-128">Maksymalny indeks w dowolnym pojedynczym wymiarze to 2 147 483 591 (0x7FFFFFC7) dla tablic bajtowych i tablic jednobajtowych struktur oraz 2 146 435 071 (0X7FEFFFFF) dla innych typów.</span><span class="sxs-lookup"><span data-stu-id="3b20d-128">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="3b20d-129">Maksymalny rozmiar ciągów i innych obiektów niebędących tablicami jest niezmieniony.</span><span class="sxs-lookup"><span data-stu-id="3b20d-129">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="3b20d-130">Przed włączeniem tej funkcji upewnij się, że aplikacja nie zawiera niebezpiecznego kodu, który zakłada, że wszystkie tablice mają rozmiar mniejszy niż 2 GB.</span><span class="sxs-lookup"><span data-stu-id="3b20d-130">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="3b20d-131">Na przykład kod niebezpieczny używający tablic jako bufory może być podatny na przepełnienia buforu, jeśli zostanie zapisany w założeniu, że tablice nie przekroczą 2 GB.</span><span class="sxs-lookup"><span data-stu-id="3b20d-131">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b20d-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="3b20d-132">Example</span></span>  

 <span data-ttu-id="3b20d-133">Poniższy przykład pokazuje, jak włączyć tę funkcję dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="3b20d-133">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="3b20d-134">Obsługiwane w</span><span class="sxs-lookup"><span data-stu-id="3b20d-134">Supported in</span></span>

<span data-ttu-id="3b20d-135">.NET Framework 4,5 i nowsze wersje</span><span class="sxs-lookup"><span data-stu-id="3b20d-135">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="3b20d-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3b20d-136">See also</span></span>

- [<span data-ttu-id="3b20d-137">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="3b20d-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3b20d-138">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="3b20d-138">Configuration File Schema</span></span>](../index.md)
