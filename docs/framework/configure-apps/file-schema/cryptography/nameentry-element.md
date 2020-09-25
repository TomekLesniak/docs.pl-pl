---
title: <nameEntry> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: 4341b1fcd3762e5aa55f0ba988f7f49d4b5cacd6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201775"
---
# <a name="nameentry-element"></a><span data-ttu-id="4229a-102">\<nameEntry> Element</span><span class="sxs-lookup"><span data-stu-id="4229a-102">\<nameEntry> Element</span></span>

<span data-ttu-id="4229a-103">Mapuje nazwę klasy na przyjazną nazwę algorytmu, która pozwala jednej klasie mieć wiele przyjaznych nazw.</span><span class="sxs-lookup"><span data-stu-id="4229a-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameEntry>**  
  
## <a name="syntax"></a><span data-ttu-id="4229a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4229a-104">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4229a-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="4229a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4229a-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="4229a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4229a-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="4229a-107">Attributes</span></span>  
  
|<span data-ttu-id="4229a-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="4229a-108">Attribute</span></span>|<span data-ttu-id="4229a-109">Opis</span><span class="sxs-lookup"><span data-stu-id="4229a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4229a-110">**Nazwij**</span><span class="sxs-lookup"><span data-stu-id="4229a-110">**name**</span></span>|<span data-ttu-id="4229a-111">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="4229a-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="4229a-112">Określa przyjazną nazwę algorytmu, który implementuje Klasa kryptografii.</span><span class="sxs-lookup"><span data-stu-id="4229a-112">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="4229a-113">**określonej**</span><span class="sxs-lookup"><span data-stu-id="4229a-113">**class**</span></span>|<span data-ttu-id="4229a-114">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="4229a-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="4229a-115">Określa wartość atrybutu **name** w [\<cryptoClass>](cryptoclass-element.md) elemencie.</span><span class="sxs-lookup"><span data-stu-id="4229a-115">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4229a-116">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="4229a-116">Child Elements</span></span>  

 <span data-ttu-id="4229a-117">Brak.</span><span class="sxs-lookup"><span data-stu-id="4229a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4229a-118">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="4229a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4229a-119">Element</span><span class="sxs-lookup"><span data-stu-id="4229a-119">Element</span></span>|<span data-ttu-id="4229a-120">Opis</span><span class="sxs-lookup"><span data-stu-id="4229a-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4229a-121">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4229a-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="4229a-122">Określa element główny dla sekcji konfiguracji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4229a-122">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4229a-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4229a-123">Remarks</span></span>  

 <span data-ttu-id="4229a-124">Atrybut **name** może być nazwą jednej z klas abstrakcyjnych znalezionych w <xref:System.Security.Cryptography> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4229a-124">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="4229a-125">Po wywołaniu metody **Create** dla abstrakcyjnej klasy kryptograficznej, nazwa klasy abstrakcyjnej jest przenoszona do <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="4229a-125">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="4229a-126">Funkcja " **Nofrom** " zwraca wystąpienie typu wskazane przez atrybut **Class** .</span><span class="sxs-lookup"><span data-stu-id="4229a-126">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="4229a-127">Jeśli atrybut **name** jest krótką nazwą, taką jak RSA, można **użyć tej nazwy podczas wywoływania metody.**</span><span class="sxs-lookup"><span data-stu-id="4229a-127">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4229a-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="4229a-128">Example</span></span>  

 <span data-ttu-id="4229a-129">Poniższy przykład pokazuje, jak użyć elementu, **\<nameEntry>** Aby odwoływać się do klasy kryptografii i skonfigurować środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="4229a-129">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="4229a-130">Następnie można przekazać ciąg "RSA" do <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metody i użyć <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metody do zwrócenia `MyCryptoRSAClass` obiektu.</span><span class="sxs-lookup"><span data-stu-id="4229a-130">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4229a-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4229a-131">See also</span></span>

- [<span data-ttu-id="4229a-132">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="4229a-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4229a-133">Schemat ustawień kryptografii</span><span class="sxs-lookup"><span data-stu-id="4229a-133">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4229a-134">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="4229a-134">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="4229a-135">Konfigurowanie klasy kryptografii</span><span class="sxs-lookup"><span data-stu-id="4229a-135">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
