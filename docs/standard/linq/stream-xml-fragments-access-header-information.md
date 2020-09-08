---
title: Jak przesyłać fragmenty XML z dostępem do informacji nagłówka — LINQ to XML
description: Dowiedz się, jak zaimplementować i używać niestandardowej metody osi, która strumieniuje fragmenty XML z pliku określonego przez identyfikator URI.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 7f242770-b0c7-418d-894b-643215e1f8aa
ms.openlocfilehash: d50c29feb305341155257cd215e0292350689e7b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553256"
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-linq-to-xml"></a><span data-ttu-id="5658d-103">Jak przesyłać fragmenty XML z dostępem do informacji nagłówka (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="5658d-103">How to stream XML fragments with access to header information (LINQ to XML)</span></span>

<span data-ttu-id="5658d-104">Czasami konieczne jest odczytanie arbitralnie dużych plików XML i zapisanie aplikacji w celu przewidzenia rozmiaru pamięci aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5658d-104">Sometimes you have to read arbitrarily large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="5658d-105">W przypadku próby wypełnienia drzewa XML przy użyciu dużego pliku XML użycie pamięci będzie proporcjonalne do rozmiaru pliku, czyli nadmierne.</span><span class="sxs-lookup"><span data-stu-id="5658d-105">If you attempt to populate an XML tree with a large XML file, your memory usage will be proportional to the size of the file—that is, excessive.</span></span> <span data-ttu-id="5658d-106">W związku z tym należy zamiast tego użyć techniki przesyłania strumieniowego.</span><span class="sxs-lookup"><span data-stu-id="5658d-106">Therefore, you should use a streaming technique instead.</span></span>

<span data-ttu-id="5658d-107">Jedną z opcji jest zapisanie aplikacji przy użyciu programu <xref:System.Xml.XmlReader> .</span><span class="sxs-lookup"><span data-stu-id="5658d-107">One option is to write your application using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="5658d-108">Można jednak użyć LINQ do wykonywania zapytań w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="5658d-108">However, you might want to use LINQ to query the XML tree.</span></span> <span data-ttu-id="5658d-109">W takim przypadku można napisać własną metodę osi niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="5658d-109">If so, you can write your own custom axis method.</span></span> <span data-ttu-id="5658d-110">Aby uzyskać więcej informacji, zobacz [jak napisać metodę osi LINQ to XML](write-linq-xml-axis-method.md).</span><span class="sxs-lookup"><span data-stu-id="5658d-110">For more information, see [How to write a LINQ to XML axis method](write-linq-xml-axis-method.md).</span></span>

<span data-ttu-id="5658d-111">Aby napisać własną metodę osi, napisz małą metodę, która używa <xref:System.Xml.XmlReader> do odczytu węzłów do momentu osiągnięcia jednego z węzłów, w których Cię interesują.</span><span class="sxs-lookup"><span data-stu-id="5658d-111">To write your own axis method, you write a small method that uses the <xref:System.Xml.XmlReader> to read nodes until it reaches one of the nodes in which you're interested.</span></span> <span data-ttu-id="5658d-112">Metoda następnie wywołuje <xref:System.Xml.Linq.XNode.ReadFrom%2A> , który odczytuje z <xref:System.Xml.XmlReader> i tworzy wystąpienie fragmentu XML.</span><span class="sxs-lookup"><span data-stu-id="5658d-112">The method then calls <xref:System.Xml.Linq.XNode.ReadFrom%2A>, which reads from the <xref:System.Xml.XmlReader> and instantiates an XML fragment.</span></span> <span data-ttu-id="5658d-113">Następnie przekazuje każdy fragment `yield return` do metody, która wylicza metodę osi niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="5658d-113">It then yields each fragment through `yield return` to the method that's enumerating your custom axis method.</span></span> <span data-ttu-id="5658d-114">Następnie można napisać zapytania LINQ na niestandardowej metodzie osi.</span><span class="sxs-lookup"><span data-stu-id="5658d-114">You can then write LINQ queries on your custom axis method.</span></span>

<span data-ttu-id="5658d-115">Techniki przesyłania strumieniowego najlepiej zastosować w sytuacjach, gdy trzeba przetwarzać dokument źródłowy tylko raz i można przetwarzać elementy w kolejności dokumentu.</span><span class="sxs-lookup"><span data-stu-id="5658d-115">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="5658d-116">Niektóre standardowe operatory zapytań, takie jak <xref:System.Linq.Enumerable.OrderBy%2A> , iteruje źródło, zbierają wszystkie dane, sortują je, a następnie zwracają pierwszy element w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="5658d-116">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="5658d-117">Jeśli używasz operatora zapytania, który materializuje jego źródło przed uzyskaniem pierwszego elementu, nie będzie zachowana mała ilość pamięci.</span><span class="sxs-lookup"><span data-stu-id="5658d-117">If you use a query operator that materializes its source before yielding the first item, you won't retain a small memory footprint.</span></span>

## <a name="example-implement-and-use-a-custom-axis-method-that-streams-xml-fragments-from-the-file-specified-by-a-uri"></a><span data-ttu-id="5658d-118">Przykład: implementacja i użycie niestandardowej metody osi, która strumieniuje fragmenty XML z pliku określonego przez identyfikator URI</span><span class="sxs-lookup"><span data-stu-id="5658d-118">Example: Implement and use a custom axis method that streams XML fragments from the file specified by a URI</span></span>

<span data-ttu-id="5658d-119">Czasami problem jest znacznie bardziej interesujący.</span><span class="sxs-lookup"><span data-stu-id="5658d-119">Sometimes the problem gets just a little more interesting.</span></span> <span data-ttu-id="5658d-120">W poniższym dokumencie XML konsument niestandardowej metody osi musi znać nazwę klienta, do którego należy każdy element.</span><span class="sxs-lookup"><span data-stu-id="5658d-120">In the following XML document, the consumer of your custom axis method also has to know the name of the customer that each item belongs to.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Root>
  <Customer>
    <Name>A. Datum Corporation</Name>
    <Item>
      <Key>0001</Key>
    </Item>
    <Item>
      <Key>0002</Key>
    </Item>
    <Item>
      <Key>0003</Key>
    </Item>
    <Item>
      <Key>0004</Key>
    </Item>
  </Customer>
  <Customer>
    <Name>Fabrikam, Inc.</Name>
    <Item>
      <Key>0005</Key>
    </Item>
    <Item>
      <Key>0006</Key>
    </Item>
    <Item>
      <Key>0007</Key>
    </Item>
    <Item>
      <Key>0008</Key>
    </Item>
  </Customer>
  <Customer>
    <Name>Southridge Video</Name>
    <Item>
      <Key>0009</Key>
    </Item>
    <Item>
      <Key>0010</Key>
    </Item>
  </Customer>
</Root>
```

<span data-ttu-id="5658d-121">Podejście, które ten przykład przyjmuje, ma również na celu śledzenie informacji o tym nagłówku, zapisanie informacji nagłówka, a następnie utworzenie małego drzewa XML zawierającego zarówno informacje nagłówka, jak i szczegółowe dane, które są wyliczane.</span><span class="sxs-lookup"><span data-stu-id="5658d-121">The approach that this example takes is to also watch for this header information, save the header information, and then build a small XML tree that contains both the header information and the detail that you're enumerating.</span></span> <span data-ttu-id="5658d-122">Następnie metoda osi daje nowe, małe drzewo XML.</span><span class="sxs-lookup"><span data-stu-id="5658d-122">The axis method then yields this new, small XML tree.</span></span> <span data-ttu-id="5658d-123">Następnie zapytanie ma dostęp do informacji nagłówka oraz informacji szczegółowych.</span><span class="sxs-lookup"><span data-stu-id="5658d-123">The query then has access to the header information as well as the detail information.</span></span>

<span data-ttu-id="5658d-124">Takie podejście ma niewielkie rozmiary pamięci.</span><span class="sxs-lookup"><span data-stu-id="5658d-124">This approach has a small memory footprint.</span></span> <span data-ttu-id="5658d-125">Ze względu na to, że każdy szczegółowy fragment kodu XML jest przewidziany, żadne odwołania nie są przechowywane w poprzednim fragmencie i dostępne do wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="5658d-125">As each detail XML fragment is yielded, no references are kept to the previous fragment, and it's available for garbage collection.</span></span> <span data-ttu-id="5658d-126">Ta technika tworzy wiele krótkoterminowych obiektów na stercie.</span><span class="sxs-lookup"><span data-stu-id="5658d-126">This technique creates many short lived objects on the heap.</span></span>

<span data-ttu-id="5658d-127">Poniższy przykład przedstawia sposób implementacji i używania niestandardowej metody osi, która strumieniuje fragmenty XML z pliku określonego przez identyfikator URI.</span><span class="sxs-lookup"><span data-stu-id="5658d-127">The following example shows how to implement and use a custom axis method that streams XML fragments from the file specified by the URI.</span></span> <span data-ttu-id="5658d-128">Ta niestandardowa oś jest zapisywana w taki sposób, że oczekuje dokumentu, `Customer` `Name` , i `Item` elementy, i że te elementy będą ułożone jak w powyższym `Source.xml` dokumencie.</span><span class="sxs-lookup"><span data-stu-id="5658d-128">This custom axis is written such that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the above `Source.xml` document.</span></span> <span data-ttu-id="5658d-129">Jest to implementacja uproszczony.</span><span class="sxs-lookup"><span data-stu-id="5658d-129">It's a simplistic implementation.</span></span> <span data-ttu-id="5658d-130">Bardziej niezawodna implementacja zostanie przygotowana do analizy nieprawidłowego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="5658d-130">A more robust implementation would be prepared to parse an invalid document.</span></span>

```csharp
static IEnumerable<XElement> StreamCustomerItem(string uri)
{
    using (XmlReader reader = XmlReader.Create(uri))
    {
        XElement name = null;
        XElement item = null;

        reader.MoveToContent();

        // Parse the file, save header information when encountered, and yield the
        // Item XElement objects as they're created.

        // loop through Customer elements
        while (reader.Read())
        {
            if (reader.NodeType == XmlNodeType.Element
                && reader.Name == "Customer")
            {
                // move to Name element
                while (reader.Read())
                {
                    if (reader.NodeType == XmlNodeType.Element &&
                        reader.Name == "Name")
                    {
                        name = XElement.ReadFrom(reader) as XElement;
                        break;
                    }
                }

                // Loop through Item elements
                while (reader.Read())
                {
                    if (reader.NodeType == XmlNodeType.EndElement)
                        break;
                    if (reader.NodeType == XmlNodeType.Element
                        && reader.Name == "Item")
                    {
                        item = XElement.ReadFrom(reader) as XElement;
                        if (item != null) {
                            XElement tempRoot = new XElement("Root",
                                new XElement(name)
                            );
                            tempRoot.Add(item);
                            yield return item;
                        }
                    }
                }
            }
        }
    }
}

static void Main(string[] args)
{
    XElement xmlTree = new XElement("Root",
        from el in StreamCustomerItem("Source.xml")
        where (int)el.Element("Key") >= 3 && (int)el.Element("Key") <= 7
        select new XElement("Item",
            new XElement("Customer", (string)el.Parent.Element("Name")),
            new XElement(el.Element("Key"))
        )
    );
    Console.WriteLine(xmlTree);
}
```

```vb
Module Module1

    Sub Main()
        Dim xmlTree = <Root>
                          <%=
                              From el In New StreamCustomerItem("Source.xml")
                              Let itemKey = CInt(el.<Key>.Value)
                              Where itemKey >= 3 AndAlso itemKey <= 7
                              Select <Item>
                                         <Customer><%= el.Parent.<Name>.Value %></Customer>
                                         <%= el.<Key> %>
                                     </Item>
                          %>
                      </Root>

        Console.WriteLine(xmlTree)
    End Sub

End Module

Public Class StreamCustomerItem
    Implements IEnumerable(Of XElement)

    Private _uri As String

    Public Sub New(ByVal uri As String)
        _uri = uri
    End Sub

    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator
        Return New StreamCustomerItemEnumerator(_uri)
    End Function

    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator
        Return Me.GetEnumerator()
    End Function
End Class

Public Class StreamCustomerItemEnumerator
    Implements IEnumerator(Of XElement)

    Private _current As XElement
    Private _customerName As String
    Private _reader As Xml.XmlReader
    Private _uri As String

    Public Sub New(ByVal uri As String)
        _uri = uri
        _reader = Xml.XmlReader.Create(_uri)
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
        Dim item As XElement
        Dim name As XElement

        ' Parse the file, save header information when encountered, and return the
        ' current Item XElement.

        ' loop through Customer elements
        While _reader.Read()
            If _reader.NodeType = Xml.XmlNodeType.Element Then
                Select Case _reader.Name
                    Case "Customer"
                        ' move to Name element
                        While _reader.Read()

                            If _reader.NodeType = Xml.XmlNodeType.Element AndAlso
                                _reader.Name = "Name" Then

                                name = TryCast(XElement.ReadFrom(_reader), XElement)
                                _customerName = If(name IsNot Nothing, name.Value, "")
                                Exit While
                            End If

                        End While
                    Case "Item"
                        item = TryCast(XElement.ReadFrom(_reader), XElement)
                        Dim tempRoot = <Root>
                                           <Name><%= _customerName %></Name>
                                           <%= item %>
                                       </Root>
                        _current = item
                        Return True
                End Select
            End If
        End While

        Return False
    End Function

    Public Sub Reset() Implements IEnumerator.Reset
        _reader = Xml.XmlReader.Create(_uri)
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

 <span data-ttu-id="5658d-131">Ten kod spowoduje wygenerowanie następujących danych wyjściowych:</span><span class="sxs-lookup"><span data-stu-id="5658d-131">This code produces the following output:</span></span>

```xml
<Root>
  <Item>
    <Customer>A. Datum Corporation</Customer>
    <Key>0003</Key>
  </Item>
  <Item>
    <Customer>A. Datum Corporation</Customer>
    <Key>0004</Key>
  </Item>
  <Item>
    <Customer>Fabrikam, Inc.</Customer>
    <Key>0005</Key>
  </Item>
  <Item>
    <Customer>Fabrikam, Inc.</Customer>
    <Key>0006</Key>
  </Item>
  <Item>
    <Customer>Fabrikam, Inc.</Customer>
    <Key>0007</Key>
  </Item>
</Root>
```
