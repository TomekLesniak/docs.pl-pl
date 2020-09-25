---
title: <UseRandomizedStringHashAlgorithm> Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: 148d55c8b8a63737867c4bfdf3ab118dfdefd6f9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174098"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="a93c0-102">\<UseRandomizedStringHashAlgorithm> Element</span><span class="sxs-lookup"><span data-stu-id="a93c0-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>

<span data-ttu-id="a93c0-103">Określa, czy środowisko uruchomieniowe języka wspólnego oblicza kody skrótów dla ciągów na podstawie poszczególnych domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a93c0-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a><span data-ttu-id="a93c0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a93c0-104">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a93c0-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a93c0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a93c0-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a93c0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a93c0-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a93c0-107">Attributes</span></span>  
  
|<span data-ttu-id="a93c0-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a93c0-108">Attribute</span></span>|<span data-ttu-id="a93c0-109">Opis</span><span class="sxs-lookup"><span data-stu-id="a93c0-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a93c0-110">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="a93c0-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="a93c0-111">Określa, czy kody skrótów dla ciągów są obliczane na podstawie poszczególnych domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a93c0-111">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a93c0-112">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="a93c0-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="a93c0-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="a93c0-113">Value</span></span>|<span data-ttu-id="a93c0-114">Opis</span><span class="sxs-lookup"><span data-stu-id="a93c0-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="a93c0-115">Środowisko uruchomieniowe języka wspólnego nie oblicza kodów skrótów dla ciągów na podstawie poszczególnych domen aplikacji; pojedynczy algorytm służy do obliczania kodów skrótów ciągów.</span><span class="sxs-lookup"><span data-stu-id="a93c0-115">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="a93c0-116">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="a93c0-116">This is the default.</span></span>|  
|`1`|<span data-ttu-id="a93c0-117">Środowisko uruchomieniowe języka wspólnego oblicza kody skrótów dla ciągów na podstawie poszczególnych domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a93c0-117">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="a93c0-118">Identyczne ciągi w różnych domenach aplikacji i w różnych procesach będą mieć różne kody skrótów.</span><span class="sxs-lookup"><span data-stu-id="a93c0-118">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a93c0-119">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a93c0-119">Child Elements</span></span>  

 <span data-ttu-id="a93c0-120">Brak.</span><span class="sxs-lookup"><span data-stu-id="a93c0-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a93c0-121">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a93c0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a93c0-122">Element</span><span class="sxs-lookup"><span data-stu-id="a93c0-122">Element</span></span>|<span data-ttu-id="a93c0-123">Opis</span><span class="sxs-lookup"><span data-stu-id="a93c0-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a93c0-124">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a93c0-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a93c0-125">Zawiera informacje dotyczące opcji inicjowania środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="a93c0-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a93c0-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a93c0-126">Remarks</span></span>  

 <span data-ttu-id="a93c0-127">Domyślnie <xref:System.StringComparer> Klasa i <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> Metoda używają jednego algorytmu wyznaczania wartości skrótu, który tworzy spójny kod skrótu w różnych domenach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a93c0-127">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="a93c0-128">Jest to równoznaczne z ustawieniem `enabled` atrybutu `<UseRandomizedStringHashAlgorithm>` elementu na `0` .</span><span class="sxs-lookup"><span data-stu-id="a93c0-128">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="a93c0-129">Jest to algorytm wyznaczania wartości skrótu używany w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a93c0-129">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="a93c0-130"><xref:System.StringComparer>Klasa i <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> Metoda mogą również używać innego algorytmu wyznaczania wartości skrótu, który oblicza kody skrótów dla poszczególnych domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a93c0-130">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="a93c0-131">W związku z tym kody skrótów dla równoważnych ciągów różnią się w różnych domenach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a93c0-131">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="a93c0-132">Jest to funkcja opcjonalna. Aby skorzystać z niego, należy ustawić `enabled` atrybut `<UseRandomizedStringHashAlgorithm>` elementu na `1` .</span><span class="sxs-lookup"><span data-stu-id="a93c0-132">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="a93c0-133">Wyszukiwanie ciągu w tabeli skrótów jest zazwyczaj operacją O (1).</span><span class="sxs-lookup"><span data-stu-id="a93c0-133">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="a93c0-134">Jednak w przypadku wystąpienia dużej liczby kolizji wyszukiwanie może być operacją O (n<sup>2</sup>).</span><span class="sxs-lookup"><span data-stu-id="a93c0-134">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="a93c0-135">Można użyć `<UseRandomizedStringHashAlgorithm>` elementu konfiguracji, aby wygenerować losowy algorytm wyznaczania wartości skrótu na domenę aplikacji, co z kolei ogranicza liczbę potencjalnych kolizji, szczególnie gdy klucze, z których są obliczane kody skrótów, są oparte na danych wejściowych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="a93c0-135">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a93c0-136">Przykład</span><span class="sxs-lookup"><span data-stu-id="a93c0-136">Example</span></span>  

 <span data-ttu-id="a93c0-137">W poniższym przykładzie zdefiniowano `DisplayString` klasę, która zawiera znak prywatny w postaci ciągu, `s` którego wartością jest "to jest ciąg".</span><span class="sxs-lookup"><span data-stu-id="a93c0-137">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="a93c0-138">Zawiera również `ShowStringHashCode` metodę, która wyświetla wartość ciągu i jego kod skrótu wraz z nazwą domeny aplikacji, w której jest wykonywana metoda.</span><span class="sxs-lookup"><span data-stu-id="a93c0-138">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="a93c0-139">W przypadku uruchomienia tego przykładu bez podawania pliku konfiguracji wyświetlane są dane wyjściowe podobne do poniższych.</span><span class="sxs-lookup"><span data-stu-id="a93c0-139">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="a93c0-140">Należy zauważyć, że kody skrótów dla ciągu są identyczne w obu domenach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a93c0-140">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="a93c0-141">Jeśli jednak dodasz następujący plik konfiguracji do katalogu przykładu, a następnie uruchomisz przykład, kody skrótów dla tego samego ciągu różnią się w zależności od domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a93c0-141">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="a93c0-142">Gdy plik konfiguracji jest obecny, w przykładzie są wyświetlane następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="a93c0-142">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="a93c0-143">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a93c0-143">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
