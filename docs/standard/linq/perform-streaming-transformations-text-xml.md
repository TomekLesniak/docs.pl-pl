---
title: Jak wykonać przekształcenia strumieniowe tekstu do formatu XML w języku C# — LINQ to XML
description: Można użyć metody rozszerzenia, która zwalnia wiersz w czasie, aby przesłać strumieniowo plik tekstowy do przetworzenia. Ta technika ogranicza wymagania dotyczące pamięci w porównaniu do metod, które ładują cały plik, a następnie przetwarzają je.
ms.date: 07/20/2015
dev_langs:
- csharp
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
ms.openlocfilehash: 8e0d710d7cbc6de8cc60721c211376a82b6c29fc
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553783"
---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-in-c-linq-to-xml"></a>Jak wykonać przekształcenia strumieniowe tekstu do formatu XML w języku C# (LINQ to XML)

Można użyć metody rozszerzenia, która zwalnia wiersz w czasie, aby przesłać strumieniowo plik tekstowy do przetworzenia. Ta technika ogranicza wymagania dotyczące pamięci w porównaniu do metod, które ładują cały plik, a następnie przetwarzają je.

Metoda rozszerzająca może dostarczyć linię przy użyciu `yield return` konstrukcji. Zapytanie LINQ może przetworzyć strumień w opóźniony sposób. Jeśli używasz <xref:System.Xml.Linq.XStreamingElement> do przesyłania strumieniowego danych wyjściowych, możesz utworzyć transformację z pliku tekstowego w formacie XML, który używa minimalnej ilości pamięci, niezależnie od rozmiaru źródłowego pliku tekstowego.

> [!NOTE]
> Technika jest najlepiej stosowana w sytuacjach, w których można przetwarzać cały plik raz, pobierając wiersze z dokumentu źródłowego. Przetwarzanie pliku więcej niż raz, lub sortowanie przed przetwarzaniem, zmniejsza korzyści wynikające z wydajności techniki przesyłania strumieniowego.

## <a name="example-use-an-extension-method-to-stream-text"></a>Przykładowo Użyj metody rozszerzenia do przesyłania strumieniowego tekstu

W przykładzie zastosowano następujący plik tekstowy, People.txt jako Źródło:

```text
#This is a comment
1,Tai,Yee,Writer
2,Nikolay,Grachev,Programmer
3,David,Wright,Inventor
```

W kodzie dla przykładu Metoda rozszerzająca `Lines` udostępnia tekst wiersz w czasie:

```csharp
public static class StreamReaderSequence
{
    public static IEnumerable<string> Lines(this StreamReader source)
    {
        if (source == null)
            throw new ArgumentNullException(nameof(source));

        string line;
        while ((line = source.ReadLine()) != null)
        {
            yield return line;
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        var sr = new StreamReader("People.txt");
        var xmlTree = new XStreamingElement("Root",
            from line in sr.Lines()
            let items = line.Split(',')
            where !line.StartsWith("#")
            select new XElement("Person",
                       new XAttribute("ID", items[0]),
                       new XElement("First", items[1]),
                       new XElement("Last", items[2]),
                       new XElement("Occupation", items[3])
                   )
        );
        Console.WriteLine(xmlTree);
        sr.Close();
    }
}
```

Przykład generuje następujące dane wyjściowe:

```xml
<Root>
  <Person ID="1">
    <First>Tai</First>
    <Last>Yee</Last>
    <Occupation>Writer</Occupation>
  </Person>
  <Person ID="2">
    <First>Nikolay</First>
    <Last>Grachev</Last>
    <Occupation>Programmer</Occupation>
  </Person>
  <Person ID="3">
    <First>David</First>
    <Last>Wright</Last>
    <Occupation>Inventor</Occupation>
  </Person>
</Root>
```

## <a name="see-also"></a>Zobacz też

- <xref:System.Xml.Linq.XStreamingElement>
