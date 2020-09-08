---
title: Jak serializować przy użyciu LINQ to XML DataContractSerializer
description: Dowiedz się, jak serializować i deserializować przy użyciu obiektu DataContractSerializer.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 3320ecbf-cdbe-480e-979c-2c14bbef9988
ms.openlocfilehash: 6fcc8f725855386fe987589fe4dde74b06ed60a6
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553259"
---
# <a name="how-to-serialize-using-datacontractserializer-linq-to-xml"></a>Jak serializować przy użyciu obiektu DataContractSerializer (LINQ to XML)

W tym artykule przedstawiono przykład serializacji i deserializacji przy użyciu <xref:System.Runtime.Serialization.DataContractSerializer> języka C# i Visual Basic.

## <a name="example-create-objects-that-contain-xelement-objects-then-serialize-and-deserialize-them"></a>Przykład: Utwórz obiekty, które zawierają `XElement` obiekty, a następnie serializować i deserializacji

Poniższy przykład tworzy wiele obiektów, które zawierają <xref:System.Xml.Linq.XElement> obiekty. Następnie serializować je do plików tekstowych, a następnie deserializacji ich z plików tekstowych.

```csharp
using System;
using System.Xml;
using System.Xml.Linq;
using System.IO;
using System.Runtime.Serialization;

public class XLinqTest
{
    public static void Main()
    {
        Test<XElement>(CreateXElement());
        Test<XElementContainer>(new XElementContainer());
        Test<XElementNullContainer>(new XElementNullContainer());
    }

    public static void Test<T>(T obj)
    {
        DataContractSerializer s = new DataContractSerializer(typeof(T));
        using (FileStream fs = File.Open("test" + typeof(T).Name + ".xml", FileMode.Create))
        {
            Console.WriteLine("Testing for type: {0}", typeof(T));
            s.WriteObject(fs, obj);
        }
        using (FileStream fs = File.Open("test" + typeof(T).Name + ".xml", FileMode.Open))
        {
            object s2 = s.ReadObject(fs);
            if (s2 == null)
                Console.WriteLine("  Deserialized object is null (Nothing in VB)");
            else
                Console.WriteLine("  Deserialized type: {0}", s2.GetType());
        }
    }

    public static XElement CreateXElement()
    {
        return new XElement(XName.Get("NameInNamespace", "http://www.adventure-works.org"));
    }
}

[DataContract]
public class XElementContainer
{
    [DataMember]
    public XElement member;

    public XElementContainer()
    {
        member = XLinqTest.CreateXElement();
    }
}

[DataContract]
public class XElementNullContainer
{
    [DataMember]
    public XElement member;

    public XElementNullContainer()
    {
        member = null;
    }
}
```

```vb
Imports System
Imports System.Xml
Imports System.Xml.Linq
Imports System.IO
Imports System.Runtime.Serialization

Public Class XLinqTest
    Shared Sub Main()
        Test(Of XElement)(CreateXElement())
        Test(Of XElementContainer)(New XElementContainer())
        Test(Of XElementNullContainer)(New XElementNullContainer())
    End Sub

    Public Shared Sub Test(Of T)(ByRef obj)
        Dim s As DataContractSerializer = New DataContractSerializer(GetType(T))
        Using fs As FileStream = File.Open("test" & GetType(T).Name & ".xml", FileMode.Create)
            Console.WriteLine("Testing for type: {0}", GetType(T))
            s.WriteObject(fs, obj)
        End Using

        Using fs As FileStream = File.Open("test" & GetType(T).Name & ".xml", FileMode.Open)
            Dim s2 As Object = s.ReadObject(fs)
            If s2 Is Nothing Then
                Console.WriteLine("  Deserialized object is null (Nothing in VB)")
            Else
                Console.WriteLine("  Deserialized type: {0}", s2.GetType())
            End If
        End Using
    End Sub

    Public Shared Function CreateXElement() As XElement
        Return New XElement(XName.Get("NameInNamespace", "http://www.adventure-works.org"))
    End Function
End Class

<DataContract()> _
Public Class XElementContainer
    <DataMember()> _
    Public member As XElement

    Public Sub XElementContainer()
        member = XLinqTest.CreateXElement()
    End Sub
End Class

<DataContract()> _
Public Class XElementNullContainer
    <DataMember()> _
    Public member As XElement

    Public Sub XElementNullContainer()
        member = Nothing
    End Sub
End Class
```

 Ten przykład generuje następujące wyniki:

```output
Testing for type: System.Xml.Linq.XElement
  Deserialized type: System.Xml.Linq.XElement
Testing for type: XElementContainer
  Deserialized type: XElementContainer
Testing for type: XElementNullContainer
  Deserialized type: XElementNullContainer
```
