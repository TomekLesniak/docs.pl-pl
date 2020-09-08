---
title: Literały XML w Visual Basic-LINQ to XML
description: Drzewo XML można utworzyć w Visual Basic przy użyciu literałów XML i osadzonych wyrażeń. Wyrażenia osadzone umożliwiają ocenę wyrażenia i wstawianie wyników wyrażenia do drzewa XML.
ms.date: 07/20/2015
ms.assetid: 94fc0e03-978e-4c08-ab6c-0dc3c1e64f10
ms.openlocfilehash: e3b1213672a6a7ddd71fcc38b4502108a6f49881
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553208"
---
# <a name="xml-literals-in-visual-basic-linq-to-xml"></a>Literały XML w Visual Basic (LINQ to XML)

Ten artykuł zawiera informacje dotyczące tworzenia drzew XML w Visual Basic przy użyciu literałów XML i osadzonych wyrażeń.

## <a name="example-use-xml-literals-to-create-an-xml-tree"></a>Przykład: Użyj literałów XML do utworzenia drzewa XML

Poniższy przykład pokazuje, jak utworzyć <xref:System.Xml.Linq.XElement> , w tym przypadku `contacts` , za pomocą literałów XML:

```vb
Dim contacts As XElement = _
    <Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone>206-555-0144</Phone>
            <Address>
                <Street1>123 Main St</Street1>
                <City>Mercer Island</City>
                <State>WA</State>
                <Postal>68042</Postal>
            </Address>
        </Contact>
    </Contacts>
```

## <a name="example-use-xml-literals-to-create-an-xelement-with-simple-content"></a>Przykład: Użyj literałów XML, aby utworzyć XElement z prostą zawartością

Można utworzyć obiekt zawierający <xref:System.Xml.Linq.XElement> prostą zawartość w następujący sposób:

```vb
Dim n as XElement = <Customer>Adventure Works</Customer>
Console.WriteLine(n)
```

Ten przykład generuje następujące wyniki:

```xml
<Customer>Adventure Works</Customer>
```

## <a name="example-use-an-xml-literal-to-create-an-empty-element"></a>Przykład: Użyj literału XML do utworzenia pustego elementu

Można utworzyć pustą <xref:System.Xml.Linq.XElement> w następujący sposób:

```vb
Dim n As XElement = <Customer/>
Console.WriteLine(n)
```

Ten przykład generuje następujące wyniki:

```xml
<Customer />
```

## <a name="use-embedded-expressions-to-create-content"></a>Tworzenie zawartości za pomocą osadzonych wyrażeń

Ważną funkcją literałów XML jest to, że dopuszczają one osadzone wyrażenia. Wyrażenia osadzone umożliwiają ocenę wyrażenia i wstawianie wyników wyrażenia do drzewa XML. Jeśli wyrażenie szacuje typ <xref:System.Xml.Linq.XElement> , element zostanie wstawiony do drzewa. Jeśli wyrażenie szacuje typ <xref:System.Xml.Linq.XAttribute> , atrybut zostanie wstawiony do drzewa. Elementy i atrybuty można wstawiać do drzewa tylko wtedy, gdy są prawidłowe.

należy pamiętać, że tylko pojedyncze wyrażenie może przejść do wyrażenia osadzonego. Nie można osadzić wielu instrukcji. Jeśli wyrażenie wykracza poza pojedynczy wiersz, należy użyć znaku kontynuacji wiersza.

Jeśli używasz wyrażenia osadzonego do dodawania istniejących węzłów (w tym elementów) i atrybutów do nowego drzewa XML i jeśli istniejące węzły są już nadrzędne, węzły są klonowane. Nowo sklonowane węzły są dołączone do nowego drzewa XML. Jeśli istniejące węzły nie są nadrzędne, węzły są po prostu dołączone do nowego drzewa XML. W ostatnim przykładzie w tym artykule pokazano, jak to zrobić.

## <a name="example-use-an-embedded-expression-to-insert-an-element"></a>Przykład: Użyj wyrażenia osadzonego do wstawienia elementu

W poniższym przykładzie do wstawienia elementu do drzewa jest stosowane wyrażenie osadzone:

```vb
xmlTree1 As XElement = _
    <Root>
        <Child>Contents</Child>
    </Root>
Dim xmlTree2 As XElement = _
    <Root>
        <%= xmlTree1.<Child> %>
    </Root>
Console.WriteLine(xmlTree2)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <Child>Contents</Child>
</Root>
```

## <a name="example-use-an-embedded-expression-for-content"></a>Przykład: Użyj wyrażenia osadzonego dla zawartości

Możesz użyć wyrażenia osadzonego, aby dostarczyć zawartość elementu:

```vb
Dim str As String
str = "Some content"
Dim root As XElement = <Root><%= str %></Root>
Console.WriteLine(root)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>Some content</Root>
```

## <a name="example-use-a-linq-query-in-an-embedded-expression"></a>Przykład: użycie zapytania LINQ w wyrażeniu osadzonym

Wyniki zapytania LINQ można użyć do udostępnienia zawartości elementu:

```vb
Dim arr As Integer() = {1, 2, 3}

Dim n As XElement = _
    <Root>
        <%= From i In arr Select <Child><%= i %></Child> %>
    </Root>

Console.WriteLine(n)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <Child>1</Child>
  <Child>2</Child>
  <Child>3</Child>
</Root>
```

## <a name="example-use-an-embedded-expression-to-provide-node-names"></a>Przykład: Użyj wyrażenia osadzonego, aby podać nazwy węzłów

Można również użyć wyrażenia osadzonego do obliczania nazw atrybutów, wartości atrybutów, nazw elementów i wartości elementów:

```vb
Dim eleName As String = "ele"
Dim attName As String = "att"
Dim attValue As String = "aValue"
Dim eleValue As String = "eValue"
Dim n As XElement = _
    <Root <%= attName %>=<%= attValue %>>
        <<%= eleName %>>
            <%= eleValue %>
        </>
    </Root>
Console.WriteLine(n)
```

Ten przykład generuje następujące wyniki:

```xml
<Root att="aValue">
  <ele>eValue</ele>
</Root>
```

## <a name="example-use-an-embedded-expression-to-clone-and-attach-nodes"></a>Przykład: Użyj wyrażenia osadzonego do klonowania i dołączania węzłów

Jak wspomniano wcześniej, jeśli używasz wyrażenia osadzonego do dodawania istniejących węzłów (w tym elementów) i atrybutów do nowego drzewa XML, a węzły dodawane do węzłów są już nadrzędne, węzły są klonowane i klony są dołączone do nowego drzewa XML. Jeśli istniejące węzły nie są nadrzędne, są po prostu dołączone do nowego drzewa XML.

Poniższy kod ilustruje zachowanie po dodaniu elementu nadrzędnego do drzewa i po dodaniu elementu z elementem nadrzędnym do drzewa.

```vb
' Create a tree with a child element.
Dim xmlTree1 As XElement = _
    <Root>
        <Child1>1</Child1>
    </Root>

' Create an element that's not parented.
Dim child2 As XElement = <Child2>2</Child2>

' Create a tree and add Child1 and Child2 to it.
Dim xmlTree2 As XElement = _
    <Root>
        <%= xmlTree1.<Child1>(0) %>
        <%= child2 %>
    </Root>

' Compare Child1 identity.
Console.WriteLine("Child1 was {0}", _
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _
    "attached", "cloned"))

' Compare Child2 identity.
Console.WriteLine("Child2 was {0}", _
    IIf(child2 Is xmlTree2.Element("Child2"), _
    "attached", "cloned"))
```

Ten przykład generuje następujące wyniki:

```output
Child1 was cloned
Child2 was attached
```

## <a name="see-also"></a>Zobacz też

- [Konstrukcja funkcjonalna](functional-construction.md)
