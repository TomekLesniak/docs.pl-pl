---
title: <dateTimeSerialization> Element
description: W tym artykule opisano <dateTimeSerialization> element, który określa tryb serializacji obiektów DateTime.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 1623517e66955c14b7e738c860ec16086fe30429
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678977"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="c3704-103">\<dateTimeSerialization> Element</span><span class="sxs-lookup"><span data-stu-id="c3704-103">\<dateTimeSerialization> Element</span></span>

<span data-ttu-id="c3704-104">Określa tryb serializacji <xref:System.DateTime> obiektów.</span><span class="sxs-lookup"><span data-stu-id="c3704-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a><span data-ttu-id="c3704-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c3704-105">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3704-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c3704-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c3704-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c3704-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3704-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c3704-108">Attributes</span></span>  
  
|<span data-ttu-id="c3704-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c3704-109">Attributes</span></span>|<span data-ttu-id="c3704-110">Opis</span><span class="sxs-lookup"><span data-stu-id="c3704-110">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="c3704-111">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="c3704-111">Optional.</span></span> <span data-ttu-id="c3704-112">Określa tryb serializacji.</span><span class="sxs-lookup"><span data-stu-id="c3704-112">Specifies the serialization mode.</span></span> <span data-ttu-id="c3704-113">Jedną z <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> wartości.</span><span class="sxs-lookup"><span data-stu-id="c3704-113">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="c3704-114">Wartość domyślna to **roundtrip**.</span><span class="sxs-lookup"><span data-stu-id="c3704-114">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3704-115">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c3704-115">Child Elements</span></span>  

 <span data-ttu-id="c3704-116">Brak.</span><span class="sxs-lookup"><span data-stu-id="c3704-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3704-117">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c3704-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c3704-118">Element</span><span class="sxs-lookup"><span data-stu-id="c3704-118">Element</span></span>|<span data-ttu-id="c3704-119">Opis</span><span class="sxs-lookup"><span data-stu-id="c3704-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3704-120">System.XML.serialization</span><span class="sxs-lookup"><span data-stu-id="c3704-120">system.xml.serialization</span></span>|<span data-ttu-id="c3704-121">Element najwyższego poziomu do sterowania serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="c3704-121">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3704-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c3704-122">Remarks</span></span>  

<span data-ttu-id="c3704-123">Gdy ta właściwość jest ustawiona na wartość **Local**, <xref:System.DateTime> obiekty są zawsze sformatowane jako czas lokalny.</span><span class="sxs-lookup"><span data-stu-id="c3704-123">When this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="c3704-124">Oznacza to, że informacje o strefie czas lokalny zawsze jest zawarte w danych serializacji.</span><span class="sxs-lookup"><span data-stu-id="c3704-124">That is, local time zone information is always included with the serialized data.</span></span>
  
<span data-ttu-id="c3704-125">Gdy ta właściwość ma wartość **roundtrip**, <xref:System.DateTime> obiekty są sprawdzane w celu określenia, czy znajdują się one w lokalnej, UTC lub nieokreślonej strefie czasowej.</span><span class="sxs-lookup"><span data-stu-id="c3704-125">When this property is set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="c3704-126"><xref:System.DateTime> Obiekty są następnie serializowany w taki sposób, że jest zachowywany tych informacji.</span><span class="sxs-lookup"><span data-stu-id="c3704-126">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="c3704-127">Jest to zachowanie domyślne i jest to zalecane zachowanie dla wszystkich nowych aplikacji, które nie komunikują się ze starszymi wersjami platformy.</span><span class="sxs-lookup"><span data-stu-id="c3704-127">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3704-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c3704-128">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="c3704-129">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="c3704-129">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="c3704-130">\<schemaImporterExtensions> Postaci</span><span class="sxs-lookup"><span data-stu-id="c3704-130">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="c3704-131">\<add> Element dla \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="c3704-131">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="c3704-132">\<system.xml.serialization> Postaci</span><span class="sxs-lookup"><span data-stu-id="c3704-132">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
