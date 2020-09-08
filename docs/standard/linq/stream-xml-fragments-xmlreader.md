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
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-linq-to-xml"></a><span data-ttu-id="2867d-104">Jak przesyłać fragmenty XML z elementu XmlReader (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="2867d-104">How to stream XML fragments from an XmlReader (LINQ to XML)</span></span>

<span data-ttu-id="2867d-105">W przypadku konieczności przetworzenia dużych plików XML może nie być możliwe załadowanie całego drzewa XML do pamięci.</span><span class="sxs-lookup"><span data-stu-id="2867d-105">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="2867d-106">W tym artykule przedstawiono sposób przesyłania fragmentów kodu przy użyciu <xref:System.Xml.XmlReader> języka C# i Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2867d-106">This article shows how to stream fragments using an <xref:System.Xml.XmlReader> in C# and Visual Basic.</span></span>

<span data-ttu-id="2867d-107">Jednym z najbardziej skutecznych sposobów używania <xref:System.Xml.XmlReader> do odczytu <xref:System.Xml.Linq.XElement> obiektów jest napisanie własnej niestandardowej metody osi.</span><span class="sxs-lookup"><span data-stu-id="2867d-107">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="2867d-108">Metoda osi zwykle zwraca kolekcję, taką jak <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> , jak pokazano w przykładzie w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="2867d-108">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this article.</span></span> <span data-ttu-id="2867d-109">W metodzie osi niestandardowej po utworzeniu fragmentu kodu XML przez wywołanie <xref:System.Xml.Linq.XNode.ReadFrom%2A> metody Zwróć kolekcję przy użyciu `yield return` .</span><span class="sxs-lookup"><span data-stu-id="2867d-109">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="2867d-110">Zapewnia to odroczoną semantykę wykonania do niestandardowej metody osi.</span><span class="sxs-lookup"><span data-stu-id="2867d-110">This provides deferred execution semantics to your custom axis method.</span></span>

<span data-ttu-id="2867d-111">Podczas tworzenia drzewa XML na podstawie <xref:System.Xml.XmlReader> obiektu, <xref:System.Xml.XmlReader> musi on być umieszczony w elemencie.</span><span class="sxs-lookup"><span data-stu-id="2867d-111">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="2867d-112"><xref:System.Xml.Linq.XNode.ReadFrom%2A>Metoda nie zwraca, dopóki nie odczyta tagu zamykającego elementu.</span><span class="sxs-lookup"><span data-stu-id="2867d-112">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method doesn't return until it has read the close tag of the element.</span></span>

<span data-ttu-id="2867d-113">Jeśli chcesz utworzyć drzewo częściowe, można stworzyć wystąpienie obiektu <xref:System.Xml.XmlReader> , umieścić go na węźle, który ma zostać przekonwertowany na <xref:System.Xml.Linq.XElement> drzewo, a następnie utworzyć <xref:System.Xml.Linq.XElement> obiekt.</span><span class="sxs-lookup"><span data-stu-id="2867d-113">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>

<span data-ttu-id="2867d-114">Artykuł [jak przesyłać fragmenty XML z dostępem do informacji nagłówka](stream-xml-fragments-access-header-information.md) zawiera informacje dotyczące przesyłania strumieniowego bardziej złożonego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="2867d-114">The article [How to stream XML fragments with access to header information](stream-xml-fragments-access-header-information.md) contains information on streaming a more complex document.</span></span>

<span data-ttu-id="2867d-115">Artykuł [Jak przeprowadzić transformację strumieniową dużych dokumentów XML](perform-streaming-transform-large-xml-documents.md) zawiera przykład użycia LINQ to XML do przekształcania bardzo dużych dokumentów XML przy zachowaniu niewielkiej ilości pamięci.</span><span class="sxs-lookup"><span data-stu-id="2867d-115">The article [How to perform streaming transform of large XML documents](perform-streaming-transform-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>

## <a name="example-create-a-custom-axis-method"></a><span data-ttu-id="2867d-116">Przykład: Tworzenie niestandardowej metody osi</span><span class="sxs-lookup"><span data-stu-id="2867d-116">Example: Create a custom axis method</span></span>

<span data-ttu-id="2867d-117">W tym przykładzie jest tworzona Metoda osi niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="2867d-117">This example creates a custom axis method.</span></span> <span data-ttu-id="2867d-118">Zapytanie można wykonać za pomocą zapytania LINQ.</span><span class="sxs-lookup"><span data-stu-id="2867d-118">You can query it by using a LINQ query.</span></span> <span data-ttu-id="2867d-119">Metoda osi niestandardowej `StreamRootChildDoc` może odczytywać dokument zawierający `Child` element powtarzalny.</span><span class="sxs-lookup"><span data-stu-id="2867d-119">The custom axis method `StreamRootChildDoc` can read a document that has a repeating `Child` element.</span></span>

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

<span data-ttu-id="2867d-120">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="2867d-120">This example produces the following output:</span></span>

```output
bbb
ccc
```

<span data-ttu-id="2867d-121">Technika używana w tym przykładzie utrzymuje niewielki rozmiar pamięci, nawet w przypadku milionów `Child` elementów.</span><span class="sxs-lookup"><span data-stu-id="2867d-121">The technique used in this example maintains a small memory footprint even for millions of `Child` elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="2867d-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2867d-122">See also</span></span>

- [<span data-ttu-id="2867d-123">Analiza kodu XML</span><span class="sxs-lookup"><span data-stu-id="2867d-123">Parse XML</span></span>](parse-string.md)
