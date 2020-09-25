---
title: <mscorlib>, element ustawień kryptografii
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: 1788205997d0dc49df172c9dfe48faceb8fc3290
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201788"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="4d6c4-102">\<mscorlib>, element ustawień kryptografii</span><span class="sxs-lookup"><span data-stu-id="4d6c4-102">\<mscorlib> Element for Cryptography Settings</span></span>

<span data-ttu-id="4d6c4-103">Zawiera [ \<cryptographySettings> element](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="4d6c4-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<mscorlib>**  
  
## <a name="syntax"></a><span data-ttu-id="4d6c4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4d6c4-104">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d6c4-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="4d6c4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4d6c4-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="4d6c4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d6c4-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="4d6c4-107">Attributes</span></span>  

 <span data-ttu-id="4d6c4-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="4d6c4-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4d6c4-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="4d6c4-109">Child Elements</span></span>  
  
|<span data-ttu-id="4d6c4-110">Element</span><span class="sxs-lookup"><span data-stu-id="4d6c4-110">Element</span></span>|<span data-ttu-id="4d6c4-111">Opis</span><span class="sxs-lookup"><span data-stu-id="4d6c4-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="4d6c4-112">Zawiera ustawienia kryptografii.</span><span class="sxs-lookup"><span data-stu-id="4d6c4-112">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4d6c4-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="4d6c4-113">Parent Elements</span></span>  
  
|<span data-ttu-id="4d6c4-114">Element</span><span class="sxs-lookup"><span data-stu-id="4d6c4-114">Element</span></span>|<span data-ttu-id="4d6c4-115">Opis</span><span class="sxs-lookup"><span data-stu-id="4d6c4-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4d6c4-116">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d6c4-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4d6c4-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="4d6c4-117">Example</span></span>  

 <span data-ttu-id="4d6c4-118">Poniższy przykład pokazuje, jak użyć elementu, **\<mscorlib>** Aby odwoływać się do klasy kryptografii i skonfigurować środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="4d6c4-118">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="4d6c4-119">Następnie można przekazać ciąg "RSA" do <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metody i użyć <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metody do zwrócenia `MyCryptoRSAClass` obiektu.</span><span class="sxs-lookup"><span data-stu-id="4d6c4-119">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d6c4-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4d6c4-120">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="4d6c4-121">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="4d6c4-121">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4d6c4-122">Schemat ustawień kryptografii</span><span class="sxs-lookup"><span data-stu-id="4d6c4-122">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4d6c4-123">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="4d6c4-123">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="4d6c4-124">Konfigurowanie klasy kryptografii</span><span class="sxs-lookup"><span data-stu-id="4d6c4-124">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
