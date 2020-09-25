---
title: <cryptoNameMapping> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: 9ffae33a3c8a06d6cfcabf5a58b7d72baeda79c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201801"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="06104-102">\<cryptoNameMapping> Element</span><span class="sxs-lookup"><span data-stu-id="06104-102">\<cryptoNameMapping> Element</span></span>

<span data-ttu-id="06104-103">Zawiera mapowania klas do przyjaznych nazw.</span><span class="sxs-lookup"><span data-stu-id="06104-103">Contains mappings of classes to friendly names.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**

## <a name="syntax"></a><span data-ttu-id="06104-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="06104-104">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06104-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="06104-105">Attributes and Elements</span></span>  

 <span data-ttu-id="06104-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="06104-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06104-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="06104-107">Attributes</span></span>  

 <span data-ttu-id="06104-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="06104-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="06104-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="06104-109">Child Elements</span></span>  
  
|<span data-ttu-id="06104-110">Element</span><span class="sxs-lookup"><span data-stu-id="06104-110">Element</span></span>|<span data-ttu-id="06104-111">Opis</span><span class="sxs-lookup"><span data-stu-id="06104-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="06104-112">Zawiera listę klas kryptograficznych, które mają mapowanie do przyjaznej nazwy w **\<nameEntry>** elemencie.</span><span class="sxs-lookup"><span data-stu-id="06104-112">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="06104-113">Mapuje nazwę klasy na przyjazną nazwę algorytmu, która pozwala jednej klasie mieć wiele przyjaznych nazw.</span><span class="sxs-lookup"><span data-stu-id="06104-113">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06104-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="06104-114">Parent Elements</span></span>  
  
|<span data-ttu-id="06104-115">Element</span><span class="sxs-lookup"><span data-stu-id="06104-115">Element</span></span>|<span data-ttu-id="06104-116">Opis</span><span class="sxs-lookup"><span data-stu-id="06104-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="06104-117">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="06104-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="06104-118">Zawiera ustawienia kryptografii.</span><span class="sxs-lookup"><span data-stu-id="06104-118">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="06104-119">Zawiera mapowania klas do przyjaznych nazw.</span><span class="sxs-lookup"><span data-stu-id="06104-119">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="06104-120">Zawiera \<cryptographySettings> element.</span><span class="sxs-lookup"><span data-stu-id="06104-120">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="06104-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="06104-121">Example</span></span>  

 <span data-ttu-id="06104-122">Poniższy przykład pokazuje, jak użyć elementu, **\<cryptoNameMapping>** Aby odwoływać się do klasy kryptografii i skonfigurować środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="06104-122">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="06104-123">Następnie można przekazać ciąg "RSA" do <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metody i użyć <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metody do zwrócenia `MyCryptoRSAClass` obiektu.</span><span class="sxs-lookup"><span data-stu-id="06104-123">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06104-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="06104-124">See also</span></span>

- [<span data-ttu-id="06104-125">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="06104-125">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="06104-126">Schemat ustawień kryptografii</span><span class="sxs-lookup"><span data-stu-id="06104-126">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="06104-127">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="06104-127">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="06104-128">Konfigurowanie klasy kryptografii</span><span class="sxs-lookup"><span data-stu-id="06104-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
