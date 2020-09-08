---
title: Pracuj z globalnymi przestrzeniami nazw w Visual Basic-LINQ to XML
description: Należy zadeklarować przestrzeń nazw w Visual Basic z instrukcją Imports, niezależnie od tego, czy przestrzeń nazw jest domyślną przestrzenią nazw, czy ma prefiks. W tym artykule omówiono instrukcje importu i inne aspekty pracy z przestrzeniami nazw.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
ms.openlocfilehash: f05fcab6788388e36e2b68a2d4f022ea63e74280
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553822"
---
# <a name="work-with-global-namespaces-in-visual-basic-linq-to-xml"></a>Pracuj z globalnymi przestrzeniami nazw w Visual Basic (LINQ to XML)

Jedną z najważniejszych funkcji literałów XML w Visual Basic jest możliwość deklarowania przestrzeni nazw XML przy użyciu `Imports` instrukcji. Korzystając z tej funkcji, można zadeklarować przestrzeń nazw XML, która używa prefiksu lub można zadeklarować domyślną przestrzeń nazw XML.

Ta funkcja jest przydatna w dwóch sytuacjach:

- Przestrzenie nazw zadeklarowane w literałach XML nie są przenoszone do wyrażeń osadzonych. Deklarowanie globalnych przestrzeni nazw zmniejsza ilość pracy wymaganej do korzystania z osadzonych wyrażeń z przestrzeniami nazw.
- Aby używać przestrzeni nazw z właściwościami XML, należy zadeklarować globalne przestrzenie nazw.

Można zadeklarować globalne przestrzenie nazw na poziomie projektu. Można również zadeklarować globalne przestrzenie nazw na poziomie modułu, który zastępuje globalne przestrzenie nazw na poziomie projektu. Na koniec można przesłonić globalne przestrzenie nazw w literale XML.

W przypadku używania literałów XML lub właściwości XML, które znajdują się w globalnie zadeklarowanych przestrzeniach nazw, można zobaczyć rozwinięte nazwy literałów XML lub właściwości przez umieszczenie ich w programie Visual Studio. Rozwinięta nazwa zostanie wyświetlona w etykietce narzędzia.

Można uzyskać <xref:System.Xml.Linq.XNamespace> obiekt, który odnosi się do globalnej przestrzeni nazw za pomocą `GetXmlNamespace` metody.

## <a name="example-use-imports-to-declare-a-global-namespace"></a>Przykład: Użyj `Imports` , aby zadeklarować globalną przestrzeń nazw

Poniższy przykład deklaruje domyślną globalną przestrzeń nazw z `Imports` instrukcją, a następnie inicjuje <xref:System.Xml.Linq.XElement> obiekt w tej przestrzeni nazw za pomocą literału XML:

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = <Root/>
        Console.WriteLine(root)
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```xml
<Root xmlns="http://www.adventure-works.com" />
```

## <a name="example-declare-a-global-namespace-that-has-a-prefix"></a>Przykład: Zadeklaruj globalną przestrzeń nazw, która ma prefiks

Następny przykład deklaruje globalną przestrzeń nazw z prefiksem i inicjuje element z literałem XML:

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = <aw:Root/>
        Console.WriteLine(root)
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com" />
```

## <a name="example-declare-a-default-namespace-and-use-an-embedded-expression-for-the-child-element"></a>Przykład: Zadeklaruj domyślną przestrzeń nazw i użyj wyrażenia osadzonego dla `Child` elementu

Przestrzenie nazw, które są zadeklarowane w literałach XML, nie są przenoszone do wyrażeń osadzonych. Poniższy przykład deklaruje domyślną przestrzeń nazw, a następnie używa osadzonego wyrażenia dla `Child` elementu.

```vb
Dim root As XElement = _
    <Root xmlns="http://www.adventure-works.com">
        <%= <Child/> %>
    </Root>
Console.WriteLine(root)
```

Ten przykład generuje następujące wyniki:

```xml
<Root xmlns="http://www.adventure-works.com">
  <Child xmlns="" />
</Root>
```

Otrzymany kod XML zawiera deklarację domyślnej przestrzeni nazw, dzięki czemu `Child` element nie jest w żadnej przestrzeni nazw.

Można zadeklarować inną przestrzeń nazw w wyrażeniu osadzonym w następujący sposób:

```vb
Dim root As XElement = _
    <Root xmlns="http://www.adventure-works.com">
        <%= <Child xmlns="http://www.adventure-works.com"/> %>
    </Root>
Console.WriteLine(root)
```

Ten przykład generuje następujące wyniki:

```xml
<Root xmlns="http://www.adventure-works.com">
  <Child xmlns="http://www.adventure-works.com" />
</Root>
```

Jednak przy użyciu globalnej domyślnej przestrzeni nazw można używać literałów XML bez deklarowania przestrzeni nazw. Otrzymany kod XML będzie w globalnie zadeklarowanej przestrzeni nazw, jak w poniższym przykładzie:

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = <Root>
                                   <%= <Child/> %>
                               </Root>
        Console.WriteLine(root)
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```xml
<Root xmlns="http://www.adventure-works.com">
  <Child />
</Root>
```

## <a name="example-use-namespaces-with-xml-properties"></a>Przykład: Użyj przestrzeni nazw z właściwościami XML

Jeśli pracujesz z drzewem XML, który znajduje się w przestrzeni nazw, i używasz właściwości XML, należy użyć globalnej przestrzeni nazw, aby właściwości XML również znajdować się w poprawnej przestrzeni nazw. Poniższy przykład deklaruje drzewo XML w przestrzeni nazw, a następnie drukuje liczbę `Child` elementów.

```vb
Dim root As XElement = _
    <Root xmlns="http://www.adventure-works.com">
        <Child>content</Child>
    </Root>
Console.WriteLine(root.<Child>.Count())
```

Ten przykład wskazuje, że nie ma żadnych `Child` elementów. Wytwarza następujące dane wyjściowe:

```output
0
```

Jeśli jednak zostanie zadeklarowana Domyślna globalna przestrzeń nazw, wówczas zarówno literał XML, jak i Właściwość XML znajdują się w domyślnej globalnej przestrzeni nazw:

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root>
                <Child>content</Child>
            </Root>
        Console.WriteLine(root.<Child>.Count())
    End Sub
End Module
```

Ten przykład wskazuje, że istnieje jeden `Child` element. Wytwarza następujące dane wyjściowe:

```output
1
```

Jeśli zadeklarujesz globalną przestrzeń nazw, która ma prefiks, można użyć prefiksu dla obu literałów XML i właściwości XML:

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <aw:Root>
                <aw:Child>content</aw:Child>
            </aw:Root>
        Console.WriteLine(root.<aw:Child>.Count())
    End Sub
End Module
```

## <a name="example-use-getxmlnamespace-to-get-an-xnamespace"></a>Przykład: Użyj `GetXmlNamespace` , aby uzyskać `XNamespace`

Można uzyskać <xref:System.Xml.Linq.XNamespace> obiekt za pomocą `GetXmlNamespace` metody:

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = <aw:Root/>
        Dim xn As XNamespace = GetXmlNamespace(aw)
        Console.WriteLine(xn)
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
http://www.adventure-works.com
```

## <a name="see-also"></a>Zobacz też

- [Przegląd przestrzeni nazw](namespaces-overview.md)
