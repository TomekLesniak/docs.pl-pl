---
title: Weryfikacja XDR przy użyciu klasy XmlSchemaCollection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 00833027-1428-4586-83c1-42f5de3323d1
ms.openlocfilehash: 9edde2fc0da97b570162775a33c95d472cda974b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819282"
---
# <a name="xdr-validation-with-xmlschemacollection"></a>Weryfikacja XDR przy użyciu klasy XmlSchemaCollection

W przypadku, gdy sprawdzany jest XML-Data schemat z ograniczeniami (XDR) jest przechowywany w elemencie **XmlSchemaCollection**, jest on SKOJARZONY z identyfikatorem URI przestrzeni nazw określonym podczas dodawania schematu do kolekcji. **XmlValidatingReader** MAPUJE identyfikator URI przestrzeni nazw w dokumencie XML do schematu, który odnosi się do tego identyfikatora URI w kolekcji.

> [!IMPORTANT]
> <xref:System.Xml.Schema.XmlSchemaCollection>Klasa jest obecnie przestarzała i została zastąpiona <xref:System.Xml.Schema.XmlSchemaSet> klasą. Aby uzyskać więcej informacji na temat <xref:System.Xml.Schema.XmlSchemaSet> klasy, zobacz zestaw [XmlSchemaSet dla kompilacji schematu](xmlschemaset-for-schema-compilation.md).

Na przykład, jeśli element główny dokumentu XML to `<bookstore xmlns="urn:newbooks-schema">` , gdy schemat zostanie dodany do obiektu **XmlSchemaCollection** , odwołuje się do tej samej przestrzeni nazw, co następuje:

```vb
xsc.Add("urn:newbooks-schema", "newbooks.xdr")
```

```csharp
xsc.Add("urn:newbooks-schema", "newbooks.xdr");
```

Poniższy przykład kodu tworzy element **XmlValidatingReader** , który pobiera **XmlTextReader** i dodaje schemat XDR, wartość osobowy. XDR do obiektu **XmlSchemaCollection**:

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.Schema

Namespace ValidationSample

    Class Sample

        Public Shared Sub Main()
            Dim tr As New XmlTextReader("HeadCount.xml")
            Dim vr As New XmlValidatingReader(tr)

            vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr")
            vr.ValidationType = ValidationType.XDR
            AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler

            While vr.Read()
                PrintTypeInfo(vr)
                If vr.NodeType = XmlNodeType.Element Then
                    While vr.MoveToNextAttribute()
                        PrintTypeInfo(vr)
                    End While
                End If
            End While
            Console.WriteLine("Validation finished")
        End Sub

        Public Shared Sub PrintTypeInfo(vr As XmlValidatingReader)
            If vr.SchemaType IsNot Nothing Then
                If TypeOf vr.SchemaType Is XmlSchemaDatatype Or TypeOf vr.SchemaType Is XmlSchemaSimpleType Then
                    Dim value As Object = vr.ReadTypedValue()
                    Console.WriteLine($"{vr.NodeType}({vr.Name},{value.GetType().Name}):{value}")
                End If
            End If
        End Sub

        Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)
            Console.WriteLine("**_Validation error")
            Console.WriteLine($"Severity:{args.Severity}")
            Console.WriteLine($"Message:{args.Message}")
        End Sub
    End Class
End Namespace
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Schema;

namespace ValidationSample
{
    class Sample
    {
        public static void Main()
        {
            var tr = new XmlTextReader("HeadCount.xml");
            var vr = new XmlValidatingReader(tr);

            vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr");
            vr.ValidationType = ValidationType.XDR;
            vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);

            while(vr.Read())
            {
                PrintTypeInfo(vr);
                if (vr.NodeType == XmlNodeType.Element)
                {
                   while(vr.MoveToNextAttribute())
                       PrintTypeInfo(vr);
                }
            }
            Console.WriteLine("Validation finished");
        }

        public static void PrintTypeInfo(XmlValidatingReader vr)
        {
            if (vr.SchemaType != null)
            {
                if(vr.SchemaType is XmlSchemaDatatype || vr.SchemaType is XmlSchemaSimpleType)
                {
                    object value = vr.ReadTypedValue();
                    Console.WriteLine($"{vr.NodeType}({vr.Name},{value.GetType().Name}):{value}");
                }
            }
        }

        public static void ValidationHandler(object sender, ValidationEventArgs args)
        {
            Console.WriteLine("_*_Validation error");
            Console.WriteLine($"\tSeverity:{args.Severity}");
            Console.WriteLine($"\tMessage:{args.Message}");
        }
    }
}
```

Poniżej przedstawiono zawartość pliku wejściowego, _HeadCount.xml *, aby sprawdzić poprawność:

```xml
<!--Load HeadCount.xdr in SchemaCollection for Validation-->
<HeadCount xmlns='xdrHeadCount'>
   <Name>Waldo Pepper</Name>
   <Name>Red Pepper</Name>
</HeadCount>
```

Poniżej przedstawiono zawartość pliku schematu XDR, np *. XDR*, do zweryfikowania:

```xml
<Schema xmlns="urn:schemas-microsoft-com:xml-data" xmlns:dt="urn:schemas-microsoft-com:datatypes">
   <ElementType name="Name" content="textOnly"/>
   <AttributeType name="Bldg" default="2"/>
   <ElementType name="HeadCount" content="eltOnly">
      <element type="Name"/>
      <attribute type="Bldg"/>
   </ElementType>
</Schema>
```

## <a name="see-also"></a>Zobacz także

- <xref:System.Xml.XmlValidatingReader.ValidationType%2A>
- [Kompilacja schematu a klasa XmlSchemaCollection](xmlschemacollection-schema-compilation.md)
