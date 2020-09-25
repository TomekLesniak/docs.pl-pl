---
title: <cryptographySettings> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: 3c3513c05485550202f2fc5bcae1faabb0e75d47
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201814"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="3f00d-102">\<cryptographySettings> Element</span><span class="sxs-lookup"><span data-stu-id="3f00d-102">\<cryptographySettings> Element</span></span>

<span data-ttu-id="3f00d-103">Zawiera ustawienia kryptografii.</span><span class="sxs-lookup"><span data-stu-id="3f00d-103">Contains cryptography settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**

## <a name="syntax"></a><span data-ttu-id="3f00d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3f00d-104">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f00d-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="3f00d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3f00d-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="3f00d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f00d-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="3f00d-107">Attributes</span></span>  

 <span data-ttu-id="3f00d-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="3f00d-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3f00d-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="3f00d-109">Child Elements</span></span>  
  
|<span data-ttu-id="3f00d-110">Element</span><span class="sxs-lookup"><span data-stu-id="3f00d-110">Element</span></span>|<span data-ttu-id="3f00d-111">Opis</span><span class="sxs-lookup"><span data-stu-id="3f00d-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoNameMapping>](cryptonamemapping-element.md)|<span data-ttu-id="3f00d-112">Zawiera mapowania klas do przyjaznych nazw.</span><span class="sxs-lookup"><span data-stu-id="3f00d-112">Contains mappings of classes to friendly names.</span></span>|  
|[\<oidMap>](oidmap-element.md)|<span data-ttu-id="3f00d-113">Zawiera mapowania identyfikatorów obiektów ASN. 1 (OID) do klas.</span><span class="sxs-lookup"><span data-stu-id="3f00d-113">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3f00d-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="3f00d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="3f00d-115">Element</span><span class="sxs-lookup"><span data-stu-id="3f00d-115">Element</span></span>|<span data-ttu-id="3f00d-116">Opis</span><span class="sxs-lookup"><span data-stu-id="3f00d-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3f00d-117">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3f00d-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="3f00d-118">Zawiera `cryptographySettings` element.</span><span class="sxs-lookup"><span data-stu-id="3f00d-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3f00d-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="3f00d-119">Example</span></span>  

 <span data-ttu-id="3f00d-120">Poniższy przykład pokazuje, jak używać **\<cryptographySettings>** elementu, aby zawierać mapowania nazw kryptograficznych i mapowania identyfikatorów OID.</span><span class="sxs-lookup"><span data-stu-id="3f00d-120">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="3f00d-121">Ten przykład umożliwia skonfigurowanie środowiska uruchomieniowego w taki sposób, aby <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> zwracało `MyHashClass` obiekt i `MyCryptoClass` klasę do 1.3.36.2.1 identyfikatora obiektu.</span><span class="sxs-lookup"><span data-stu-id="3f00d-121">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f00d-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3f00d-122">See also</span></span>

- [<span data-ttu-id="3f00d-123">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="3f00d-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3f00d-124">Schemat ustawień kryptografii</span><span class="sxs-lookup"><span data-stu-id="3f00d-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3f00d-125">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="3f00d-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
