---
title: Jak zaprojektować typ anonimowy LINQ to XML
description: Można projektować do typu anonimowego, zamiast tworzyć typ wyłącznie do użycia w projekcji. W tym artykule przedstawiono przykład dla języków C# i Visual Basic.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 5cb9be13-5ac4-4373-a034-b3520a5b2dec
ms.openlocfilehash: ef0b1c642db055c8c5d4f2275b02119d8ebee8f0
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982419"
---
# <a name="how-to-project-an-anonymous-type-linq-to-xml"></a>Tworzenie projektu typu anonimowego (LINQ to XML)

W niektórych przypadkach można zaprojektować zapytanie do nowego typu, ale zapytanie byłoby używane tylko dla nowego typu. Zamiast tworzyć typ, można projektować do typu anonimowego. Typy anonimowe zapewniają wygodny sposób hermetyzowania zestawu właściwości tylko do odczytu w obiekcie bez konieczności jawnego definiowania typu. Jeśli napiszesz zapytanie, które tworzy obiekt typu anonimowego w `select` klauzuli, zapytanie zwraca <xref:System.Collections.IEnumerable> Typ.

W poniższym przykładzie pokazano Tworzenie obiektu typu anonimowego, który został zainicjowany z dwiema właściwościami `Amount` i `Message` .

```csharp
var v = new { Amount = 108, Message = "Hello" };
```

```vb
Dim v = New With { .Amount = 108, .Message = "Hello" };
```

Typ każdej właściwości jest wnioskowany przez kompilator. Nazwa typu jest generowana przez kompilator i nie jest dostępna na poziomie kodu źródłowego.

Aby uzyskać więcej informacji na temat typów anonimowych, zobacz:

- [Typy anonimowe (Przewodnik programowania w języku C#)](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [Typy anonimowe (Visual Basic)](../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)

## <a name="example-project-an-anonymous-type-by-creating-objects-in-the-select-clause"></a>Przykład: projekt typu anonimowego przez utworzenie obiektów w `select` klauzuli

W tym przykładzie `select` klauzula projektuje typ anonimowy. Przykład używa `var` do tworzenia `IEnumerable` obiektu. W `foreach` pętli Zmienna iteracji zostaje wystąpieniem typu anonimowego utworzonego w wyrażeniu zapytania.

Ten przykład używa [przykładowego pliku XML dokumentu XML: klienci i zamówienia](sample-xml-file-customers-orders.md).

```csharp
XElement custOrd = XElement.Load("CustomersOrders.xml");
var custList =
    from el in custOrd.Element("Customers").Elements("Customer")
    select new {
        CustomerID = (string)el.Attribute("CustomerID"),
        CompanyName = (string)el.Element("CompanyName"),
        ContactName = (string)el.Element("ContactName")
    };
foreach (var cust in custList)
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName);
```

```vb
Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")
Dim custList = _
    From el In custOrd.<Customers>.<Customer> _
    Select New With { _
        .CustomerID = el.@<CustomerID>, _
        .CompanyName = el.<CompanyName>.Value, _
        .ContactName = el.<ContactName>.Value _
    }
For Each cust In custList
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName)
Next
```

Ten przykład generuje następujące wyniki:

```output
GREAL:Great Lakes Food Market:Howard Snyder
HUNGC:Hungry Coyote Import Store:Yoshi Latimer
LAZYK:Lazy K Kountry Store:John Steel
LETSS:Let's Stop N Shop:Jaime Yorres
```

## <a name="see-also"></a>Zobacz także

- [Typy anonimowe (Przewodnik programowania w języku C#)](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [Typy anonimowe (Visual Basic)](../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
