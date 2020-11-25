---
title: <schemaImporterExtensions> Element
description: <schemaImporterExtensions>Element zawiera typy, które są używane przez XmlSchemaImporter do mapowania typów XSD na typy .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 6b644ed1112b748be4dd301d6fa6f2a6416dc67e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722144"
---
# <a name="schemaimporterextensions-element"></a>\<schemaImporterExtensions>, element

Zawiera typy, które są używane przez program <xref:System.Xml.Serialization.XmlSchemaImporter> do mapowania typów XSD na typy .NET. Aby uzyskać więcej informacji na temat plików konfiguracji, zobacz [Schemat pliku konfiguracji](../../framework/configure-apps/file-schema/index.md).  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<add> Element dla \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)|Dodaje typy, które są używane przez program <xref:System.Xml.Serialization.XmlSchemaImporter> do tworzenia mapowań.|  
  
## <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<system.xml.serialization> Postaci](system-xml-serialization-element.md)|Element najwyższego poziomu do sterowania serializacji XML.|  
  
## <a name="example"></a>Przykład  

 Poniższy przykład kodu ilustruje sposób dodawania typów, które są używane przez <xref:System.Xml.Serialization.XmlSchemaImporter> podczas mapowania typów XSD na typy .NET.  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =
        "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [Schemat pliku konfiguracji](../../framework/configure-apps/file-schema/index.md)
- [\<dateTimeSerialization> Postaci](datetimeserialization-element.md)
- [\<add> Element dla \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)
- [\<system.xml.serialization> Postaci](system-xml-serialization-element.md)
