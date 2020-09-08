---
title: Jak strumieniowo fragmenty XML z elementu XmlReader LINQ to XML
description: Można przesyłać strumieniowo fragmenty XML z elementu XmlReader przy użyciu niestandardowej metody osi w językach C# i Visual Basic. Jest to podejście, które może być przydatne podczas ładowania całego drzewa XML do pamięci, jest niemożliwe.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
ms.openlocfilehash: e3a7a6260c66f0295216552c6aa56f71a8536bdf
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553047"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-linq-to-xml"></a>Jak przesyłać fragmenty XML z elementu XmlReader (LINQ to XML)

W przypadku konieczności przetworzenia dużych plików XML może nie być możliwe załadowanie całego drzewa XML do pamięci. W tym artykule przedstawiono sposób przesyłania fragmentów kodu przy użyciu <xref:System.Xml.XmlReader> języka C# i Visual Basic.

Jednym z najbardziej skutecznych sposobów używania <xref:System.Xml.XmlReader> do odczytu <xref:System.Xml.Linq.XElement> obiektów jest napisanie własnej niestandardowej metody osi. Metoda osi zwykle zwraca kolekcję, taką jak <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> , jak pokazano w przykładzie w tym artykule. W metodzie osi niestandardowej po utworzeniu fragmentu kodu XML przez wywołanie <xref:System.Xml.Linq.XNode.ReadFrom%2A> metody Zwróć kolekcję przy użyciu `yield return` . Zapewnia to odroczoną semantykę wykonania do niestandardowej metody osi.

Podczas tworzenia drzewa XML na podstawie <xref:System.Xml.XmlReader> obiektu, <xref:System.Xml.XmlReader> musi on być umieszczony w elemencie. <xref:System.Xml.Linq.XNode.ReadFrom%2A>Metoda nie zwraca, dopóki nie odczyta tagu zamykającego elementu.

Jeśli chcesz utworzyć drzewo częściowe, można stworzyć wystąpienie obiektu <xref:System.Xml.XmlReader> , umieścić go na węźle, który ma zostać przekonwertowany na <xref:System.Xml.Linq.XElement> drzewo, a następnie utworzyć <xref:System.Xml.Linq.XElement> obiekt.

Artykuł [jak przesyłać fragmenty XML z dostępem do informacji nagłówka](stream-xml-fragments-access-header-information.md) zawiera informacje dotyczące przesyłania strumieniowego bardziej złożonego dokumentu.

Artykuł [Jak przeprowadzić transformację strumieniową dużych dokumentów XML](perform-streaming-transform-large-xml-documents.md) zawiera przykład użycia LINQ to XML do przekształcania bardzo dużych dokumentów XML przy zachowaniu niewielkiej ilości pamięci.

## <a name="example-create-a-custom-axis-method"></a>Przykład: Tworzenie niestandardowej metody osi

W tym przykładzie jest tworzona Metoda osi niestandardowej. Zapytanie można wykonać za pomocą zapytania LINQ. Metoda osi niestandardowej `StreamRootChildDoc` może odczytywać dokument zawierający `Child` element powtarzalny.

```csharp
static IEnumerable<XElement> StreamRootChildDoc(StringReader stringReader)
{
    using (XmlReader reader = XmlReader.Create(stringReader))
    {
        reader.MoveToContent();
        // Parse the file and display each of the nodes.
        while (reader.Read())
        {
            switch (reader.NodeType)
            {
                case XmlNodeType.Element:
                    if (reader.Name == "Child") {
                        XElement el = XElement.ReadFrom(reader) as XElement;
                        if (el != null)
                            yield return el;
                    }
                    break;
            }
        }
    }
}

static void Main(string[] args)
{
    string markup = @"<Root>
      <Child Key=""01"">
        <GrandChild>aaa</GrandChild>
      </Child>
      <Child Key=""02"">
        <GrandChild>bbb</GrandChild>
      </Child>
      <Child Key=""03"">
        <GrandChild>ccc</GrandChild>
      </Child>
    </Root>";

    IEnumerable<string> grandChildData =
        from el in StreamRootChildDoc(new StringReader(markup))
        where (int)el.Attribute("Key") > 1
        select (string)el.Element("GrandChild");

    foreach (string str in grandChildData) {
        Console.WriteLine(str);
    }
}
```

```vb
Module Module1
    Sub Main()
        Dim markup = "<Root>" &
                     "  <Child Key=""01"">" &
                     "    <GrandChild>aaa</GrandChild>" &
                     "  </Child>" &
                     "  <Child Key=""02"">" &
                     "    <GrandChild>bbb</GrandChild>" &
                     "  </Child>" &
                     "  <Child Key=""03"">" &
                     "    <GrandChild>ccc</GrandChild>" &
                     "  </Child>" &
                     "</Root>"

        Dim grandChildData =
             From el In New StreamRootChildDoc(New IO.StringReader(markup))
             Where CInt(el.@Key) > 1
             Select el.<GrandChild>.Value

        For Each s In grandChildData
            Console.WriteLine(s)
        Next
    End Sub
End Module

Public Class StreamRootChildDoc
    Implements IEnumerable(Of XElement)

    Private _stringReader As IO.StringReader

    Public Sub New(ByVal stringReader As IO.StringReader)
        _stringReader = stringReader
    End Sub

    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator
        Return New StreamChildEnumerator(_stringReader)
    End Function

    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator
        Return Me.GetEnumerator()
    End Function
End Class

Public Class StreamChildEnumerator
    Implements IEnumerator(Of XElement)

    Private _current As XElement
    Private _reader As Xml.XmlReader
    Private _stringReader As IO.StringReader

    Public Sub New(ByVal stringReader As IO.StringReader)
        _stringReader = stringReader
        _reader = Xml.XmlReader.Create(_stringReader)
        _reader.MoveToContent()
    End Sub

    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current
        Get
            Return _current
        End Get
    End Property

    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current
        Get
            Return Me.Current
        End Get
    End Property

    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext
        While _reader.Read()
            Select Case _reader.NodeType
                Case Xml.XmlNodeType.Element
                    Dim el = TryCast(XElement.ReadFrom(_reader), XElement)
                    If el IsNot Nothing Then
                        _current = el
                        Return True
                    End If
            End Select
        End While

        Return False
    End Function

    Public Sub Reset() Implements IEnumerator.Reset
        _reader = Xml.XmlReader.Create(_stringReader)
        _reader.MoveToContent()
    End Sub

#Region "IDisposable Support"

    Private disposedValue As Boolean ' To detect redundant calls

    ' IDisposable
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)
        If Not Me.disposedValue Then
            If disposing Then
                _reader.Close()
            End If
        End If
        Me.disposedValue = True
    End Sub

    Public Sub Dispose() Implements IDisposable.Dispose
        Dispose(True)
        GC.SuppressFinalize(Me)
    End Sub
#End Region

End Class
```

Ten przykład generuje następujące wyniki:

```output
bbb
ccc
```

Technika używana w tym przykładzie utrzymuje niewielki rozmiar pamięci, nawet w przypadku milionów `Child` elementów.

## <a name="see-also"></a>Zobacz też

- [Analiza kodu XML](parse-string.md)
