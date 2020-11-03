---
title: <add>, element dla <schemaImporterExtensions>
description: <add>Element dodaje typy używane przez klasę XmlSchemaImporter do mapowania typów XSD na typy .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 38d8ebd6e973632b23865ad60e007d9aa21e7da6
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282000"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="34368-103">\<add>, element dla \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="34368-103">\<add> Element for \<schemaImporterExtensions></span></span>

<span data-ttu-id="34368-104">Dodaje typy używane przez program <xref:System.Xml.Serialization.XmlSchemaImporter> do mapowania typów XSD na typy .NET.</span><span class="sxs-lookup"><span data-stu-id="34368-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET types.</span></span> <span data-ttu-id="34368-105">Aby uzyskać więcej informacji na temat plików konfiguracji, zobacz [Schemat pliku konfiguracji](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="34368-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
\<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a><span data-ttu-id="34368-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="34368-106">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34368-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="34368-107">Attributes and Elements</span></span>  
 <span data-ttu-id="34368-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="34368-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34368-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="34368-109">Attributes</span></span>  
  
|<span data-ttu-id="34368-110">Atrybut</span><span class="sxs-lookup"><span data-stu-id="34368-110">Attribute</span></span>|<span data-ttu-id="34368-111">Opis</span><span class="sxs-lookup"><span data-stu-id="34368-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34368-112">**Nazwij**</span><span class="sxs-lookup"><span data-stu-id="34368-112">**name**</span></span>|<span data-ttu-id="34368-113">Prosta nazwa używana do znajdowania wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="34368-113">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="34368-114">**Wprowadź**</span><span class="sxs-lookup"><span data-stu-id="34368-114">**type**</span></span>|<span data-ttu-id="34368-115">Wymagane.</span><span class="sxs-lookup"><span data-stu-id="34368-115">Required.</span></span> <span data-ttu-id="34368-116">Określa klasę rozszerzenia schematu do dodania.</span><span class="sxs-lookup"><span data-stu-id="34368-116">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="34368-117">Wartość atrybutu **typu** musi znajdować się w jednym wierszu i zawierać w pełni kwalifikowaną nazwę typu.</span><span class="sxs-lookup"><span data-stu-id="34368-117">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="34368-118">Gdy zestaw znajduje się w globalnej pamięci podręcznej zestawów (GAC), musi również zawierać wersję, kulturę i token klucza publicznego podpisanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="34368-118">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34368-119">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="34368-119">Child Elements</span></span>  
 <span data-ttu-id="34368-120">Brak.</span><span class="sxs-lookup"><span data-stu-id="34368-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34368-121">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="34368-121">Parent Elements</span></span>  
  
|<span data-ttu-id="34368-122">Element</span><span class="sxs-lookup"><span data-stu-id="34368-122">Element</span></span>|<span data-ttu-id="34368-123">Opis</span><span class="sxs-lookup"><span data-stu-id="34368-123">Description</span></span>|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|<span data-ttu-id="34368-124">Zawiera typy, które są używane przez <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="34368-124">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="34368-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="34368-125">Example</span></span>  
 <span data-ttu-id="34368-126">Poniższy przykład kodu dodaje typ rozszerzenia, którego XmlSchemaImporter może używać podczas mapowania typów.</span><span class="sxs-lookup"><span data-stu-id="34368-126">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
       PublicKeyToken=b03f5f7f11d50a3a" />
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34368-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="34368-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="34368-128">\<system.xml.serialization> Postaci</span><span class="sxs-lookup"><span data-stu-id="34368-128">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="34368-129">\<schemaImporterExtensions> Postaci</span><span class="sxs-lookup"><span data-stu-id="34368-129">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
