---
title: Jak pobrać wartość elementu (LINQ to XML) (C#)
description: Dowiedz się, jak uzyskać wartość elementów. Zobacz przykłady użycia rzutowania ciągów, rzutowania liczb całkowitych i właściwości Value.
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: eb750927d74c3068d7ab06caba9835110bd77a09
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301544"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a>Jak pobrać wartość elementu (LINQ to XML) (C#)

W tym artykule pokazano, jak uzyskać wartość elementów. Istnieją dwa podstawowe sposoby uzyskiwania wartości:

- Rzutowanie elementu <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute> na żądany typ. Operator jawnej konwersji konwertuje zawartość elementu lub atrybutu do określonego typu i przypisuje go do zmiennej.

- Użyj <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości lub <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> . Możesz również ustawić wartość przy użyciu tych właściwości.

W języku C# Rzutowanie jest ogólnie lepszym rozwiązaniem. Jeśli przerzutuje element lub atrybut do typu wartości null, kod jest łatwiejszy do zapisu podczas pobierania wartości elementu (lub atrybutu), który może lub nie istnieje. [Ostatni przykład](#element-might-not-exist-example) w tym artykule pokazuje, że Rzutowanie jest prostsze w przypadku, gdy element może nie istnieć. Nie można jednak ustawić zawartości elementu przez rzutowanie, jak można za pomocą <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości.  
  
## <a name="string-cast-example"></a>Przykład rzutowania ciągu  
 Aby pobrać wartość elementu, należy rzutować <xref:System.Xml.Linq.XElement> obiekt na żądany typ. Można rzutować element na ciąg w następujący sposób:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="integer-cast-example"></a>Przykład rzutowania liczby całkowitej  
 Można również rzutować elementy do typów innych niż ciąg. Na przykład jeśli masz element zawierający liczbę całkowitą, możesz go rzutować na `int` , jak pokazano w poniższym kodzie:  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]zapewnia jawne Operatory rzutowania dla następujących typów danych:,,,,,,,,,, `string` `bool` `bool?` `int` `int?` `uint` `uint?` `long` `long?` `ulong` `ulong?` , `float` , `float?` , `double` ,,,,,, `double?` `decimal` `decimal?` `DateTime` `DateTime?` `TimeSpan` , `TimeSpan?` ,, `GUID` i `GUID?` .  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]zapewnia te same Operatory rzutowania dla <xref:System.Xml.Linq.XAttribute> obiektów.  
  
## <a name="value-property-example"></a>Przykład właściwości wartości  
 Możesz użyć właściwości, <xref:System.Xml.Linq.XElement.Value%2A> Aby pobrać zawartość elementu:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="element-might-not-exist-example"></a>Element może nie istnieć przykład
 Czasami próbujesz pobrać wartość elementu, mimo że nie masz pewności, czy istnieje. W tym przypadku, gdy przypiszesz element rzutowany do typu referencyjnego nullable lub typu wartości null, jeśli element nie istnieje, przypisana zmienna jest ustawiona na `null` . Poniższy kod pokazuje, że gdy element może lub nie istnieje, łatwiej jest użyć rzutowania niż w celu użycia <xref:System.Xml.Linq.XElement.Value%2A> właściwości.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 Ten kod spowoduje wygenerowanie następujących danych wyjściowych:  
  
```output  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 Ogólnie rzecz biorąc, można napisać łatwiejszy kod podczas używania rzutowania do pobrania zawartości elementów i atrybutów.  
  
## <a name="see-also"></a>Zobacz też

- [Osie LINQ to XML (C#)](./linq-to-xml-axes-overview.md)
