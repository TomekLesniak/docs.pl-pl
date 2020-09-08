---
title: Zdarzenia LINQ to XML — LINQ to XML
description: Dowiedz się, jak używać zdarzeń XML do monitorowania zmian w drzewie XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 755aa1a449e873a2c4f5b17d4df3eee7ecfa9969
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553339"
---
# <a name="linq-to-xml-events-linq-to-xml"></a>Zdarzenia LINQ to XML (LINQ to XML)

Zdarzenia LINQ to XML umożliwiają otrzymywanie powiadomień, gdy drzewo XML zostanie zmienione.

Zdarzenia można dodawać do dowolnego wystąpienia dowolnego <xref:System.Xml.Linq.XObject> . Procedura obsługi zdarzeń będzie następnie otrzymywać zdarzenia dotyczące modyfikacji tego <xref:System.Xml.Linq.XObject> elementu i jego elementów podrzędnych. Na przykład można dodać program obsługi zdarzeń do elementu głównego drzewa i obsłużyć wszystkie modyfikacje drzewa z tego programu obsługi zdarzeń.

Przykłady zdarzeń LINQ to XML można znaleźć w tematach <xref:System.Xml.Linq.XObject.Changing> i <xref:System.Xml.Linq.XObject.Changed> .

## <a name="types-and-events"></a>Typy i zdarzenia

Następujące typy są używane podczas pracy ze zdarzeniami:

|Typ|Opis|
|----------|-----------------|
|<xref:System.Xml.Linq.XObjectChange>|Określa typ zdarzenia, gdy zdarzenie jest zgłaszane dla elementu <xref:System.Xml.Linq.XObject> .|
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|Dostarcza dane dla <xref:System.Xml.Linq.XObject.Changing> zdarzeń i <xref:System.Xml.Linq.XObject.Changed> .|

Podczas modyfikowania drzewa XML są zgłaszane następujące zdarzenia:

|Zdarzenie|Opis|
|-----------|-----------------|
|<xref:System.Xml.Linq.XObject.Changing>|Występuje tuż przed tym <xref:System.Xml.Linq.XObject> lub dowolnym z jego obiektów podrzędnych zostanie zmieniony.|
|<xref:System.Xml.Linq.XObject.Changed>|Występuje po <xref:System.Xml.Linq.XObject> zmianie lub dowolnych jego elementów podrzędnych.|

## <a name="example-use-events-to-maintain-a-proper-total-when-items-are-changed"></a>Przykład: Użyj zdarzeń, aby zachować prawidłową sumę w przypadku zmiany elementów

Zdarzenia są przydatne, gdy chcesz zachować pewne zagregowane informacje w drzewie XML. Na przykład możesz chcieć zachować sumę faktury, która jest sumą elementów wiersza faktury. Ten przykład używa zdarzeń, aby zachować sumę wszystkich elementów podrzędnych w ramach elementu złożonego `Items` .

```csharp
XElement root = new XElement("Root",
    new XElement("Total", "0"),
    new XElement("Items")
);
XElement total = root.Element("Total");
XElement items = root.Element("Items");
items.Changed += (object sender, XObjectChangeEventArgs cea) =>
{
    switch (cea.ObjectChange)
    {
        case XObjectChange.Add:
            if (sender is XElement)
                total.Value = ((int)total + (int)(XElement)sender).ToString();
            if (sender is XText)
                total.Value = ((int)total + (int)((XText)sender).Parent).ToString();
            break;
        case XObjectChange.Remove:
            if (sender is XElement)
                total.Value = ((int)total - (int)(XElement)sender).ToString();
            if (sender is XText)
                total.Value = ((int)total - Int32.Parse(((XText)sender).Value)).ToString();
            break;
    }
    Console.WriteLine("Changed {0} {1}",
      sender.GetType().ToString(), cea.ObjectChange.ToString());
};
items.SetElementValue("Item1", 25);
items.SetElementValue("Item2", 50);
items.SetElementValue("Item2", 75);
items.SetElementValue("Item3", 133);
items.SetElementValue("Item1", null);
items.SetElementValue("Item4", 100);
Console.WriteLine("Total:{0}", (int)total);
Console.WriteLine(root);
```

```vb
Module Module1
    Dim WithEvents items As XElement = Nothing
    Dim total As XElement = Nothing
    Dim root As XElement = _
            <Root>
                <Total>0</Total>
                <Items></Items>
            </Root>

    Private Sub XObjectChanged( _
            ByVal sender As Object, _
            ByVal cea As XObjectChangeEventArgs) _
            Handles items.Changed
        Select Case cea.ObjectChange
            Case XObjectChange.Add
                If sender.GetType() Is GetType(XElement) Then
                    total.Value = CStr(CInt(total.Value) + _
                            CInt((DirectCast(sender, XElement)).Value))
                End If
                If sender.GetType() Is GetType(XText) Then
                    total.Value = CStr(CInt(total.Value) + _
                            CInt((DirectCast(sender, XText)).Value))
                End If
            Case XObjectChange.Remove
                If sender.GetType() Is GetType(XElement) Then
                    total.Value = CStr(CInt(total.Value) - _
                            CInt((DirectCast(sender, XElement)).Value))
                End If
                If sender.GetType() Is GetType(XText) Then
                    total.Value = CStr(CInt(total.Value) - _
                            CInt((DirectCast(sender, XText)).Value))
                End If
        End Select
        Console.WriteLine("Changed {0} {1}", _
                            sender.GetType().ToString(), _
                            cea.ObjectChange.ToString())
    End Sub

    Sub Main()
        total = root.<Total>(0)
        items = root.<Items>(0)
        items.SetElementValue("Item1", 25)
        items.SetElementValue("Item2", 50)
        items.SetElementValue("Item2", 75)
        items.SetElementValue("Item3", 133)
        items.SetElementValue("Item1", Nothing)
        items.SetElementValue("Item4", 100)
        Console.WriteLine("Total:{0}", CInt(total))
        Console.WriteLine(root)
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
Changed System.Xml.Linq.XElement Add
Changed System.Xml.Linq.XElement Add
Changed System.Xml.Linq.XText Remove
Changed System.Xml.Linq.XText Add
Changed System.Xml.Linq.XElement Add
Changed System.Xml.Linq.XElement Remove
Changed System.Xml.Linq.XElement Add
Total:308
<Root>
  <Total>308</Total>
  <Items>
    <Item2>75</Item2>
    <Item3>133</Item3>
    <Item4>100</Item4>
  </Items>
</Root>
```
