---
title: Jak korzystać ze słowników przy użyciu LINQ to XML (C#)
description: Dowiedz się, jak używać słowników przy użyciu LINQ to XML. Zobacz przykłady konwertowania słowników do formatu XML i XML z powrotem do innych struktur danych.
ms.date: 07/20/2015
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: bdba7a2b3dfc16fab1e239ac804c317dfefb7d9e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302623"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a>Jak korzystać ze słowników przy użyciu LINQ to XML (C#)
Często wygodnie jest przekonwertować różne struktury danych na XML, a następnie XML z powrotem do innych struktur danych. W tym temacie przedstawiono określoną implementację ogólnego podejścia poprzez konwersję <xref:System.Collections.Generic.Dictionary%602> do formatu XML i z powrotem.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie stosowana jest forma konstrukcji funkcjonalnej, w której zapytania projektują nowe <xref:System.Xml.Linq.XElement> obiekty, a wynikowa kolekcja jest przenoszona jako argument do konstruktora obiektu głównego <xref:System.Xml.Linq.XElement> .  
  
```csharp  
Dictionary<string, string> dict = new Dictionary<string, string>();  
dict.Add("Child1", "Value1");  
dict.Add("Child2", "Value2");  
dict.Add("Child3", "Value3");  
dict.Add("Child4", "Value4");  
XElement root = new XElement("Root",  
    from keyValue in dict  
    select new XElement(keyValue.Key, keyValue.Value)  
);  
Console.WriteLine(root);  
```  
  
 Ten kod spowoduje wygenerowanie następujących danych wyjściowych:  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a>Przykład  
 Poniższy kod tworzy słownik z pliku XML.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "Value1"),  
    new XElement("Child2", "Value2"),  
    new XElement("Child3", "Value3"),  
    new XElement("Child4", "Value4")  
);  
  
Dictionary<string, string> dict = new Dictionary<string, string>();  
foreach (XElement el in root.Elements())  
    dict.Add(el.Name.LocalName, el.Value);  
foreach (string str in dict.Keys)  
    Console.WriteLine("{0}:{1}", str, dict[str]);  
```  
  
 Ten kod spowoduje wygenerowanie następujących danych wyjściowych:  
  
```output  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
