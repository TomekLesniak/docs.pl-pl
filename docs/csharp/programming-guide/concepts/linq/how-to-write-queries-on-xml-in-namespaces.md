---
title: Jak pisać zapytania dotyczące kodu XML w przestrzeniach nazw (C#)
description: Dowiedz się, jak pisać zapytania dotyczące kodu XML w przestrzeniach nazw. Dla tych zapytań należy użyć obiektów XName, które mają prawidłową przestrzeń nazw.
ms.date: 07/20/2015
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: 64eb9df1cde3b434a11e2e5410aab96993dc0fa1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303182"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a>Jak pisać zapytania dotyczące kodu XML w przestrzeniach nazw (C#)
Aby napisać zapytanie dotyczące kodu XML, który znajduje się w przestrzeni nazw, należy użyć <xref:System.Xml.Linq.XName> obiektów, które mają prawidłową przestrzeń nazw.  
  
 W przypadku języka C# najbardziej typowym podejściem jest zainicjowanie <xref:System.Xml.Linq.XNamespace> przy użyciu ciągu, który zawiera identyfikator URI, a następnie użycie przeciążenia operatora dodawania, aby połączyć przestrzeń nazw z nazwą lokalną.  
  
 Pierwszy zestaw przykładów w tym temacie przedstawia sposób tworzenia drzewa XML w domyślnej przestrzeni nazw. Drugi zestaw pokazuje, jak utworzyć drzewo XML w przestrzeni nazw z prefiksem.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład tworzy drzewo XML, który znajduje się w domyślnym obszarze nazw. Następnie pobiera kolekcję elementów.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```output  
1  
2  
3  
```  
  
## <a name="example"></a>Przykład  
 W języku C# zapytania są pisane w taki sam sposób, niezależnie od tego, czy piszesz zapytania w drzewie XML, który używa przestrzeni nazw z prefiksem lub w drzewie XML z domyślną przestrzenią nazw.  
  
 Poniższy przykład tworzy drzewo XML, który znajduje się w przestrzeni nazw z prefiksem. Następnie pobiera kolekcję elementów.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```output  
1  
2  
3  
```  
  
## <a name="see-also"></a>Zobacz także

- [Przegląd przestrzeni nazw (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)
