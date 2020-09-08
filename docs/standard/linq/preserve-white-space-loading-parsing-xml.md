---
title: Zachowywanie białych znaków podczas ładowania lub analizowania LINQ to XML XML
description: Można kontrolować zachowanie białych znaków LINQ to XML metod, które wypełniają drzewa XML. Na przykład można usunąć wcięcia dla przetwarzania w pamięci lub pozostawić je w stanie takim, w jakim jest.
ms.date: 07/20/2015
ms.assetid: f3ff58c4-55aa-4fcd-b933-e3a2ee6e706c
ms.openlocfilehash: 783a1198f0b1754c690f04159860056a0fbadeb4
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553095"
---
# <a name="preserve-white-space-while-loading-or-parsing-xml-linq-to-xml"></a>Zachowaj biały znak podczas ładowania lub analizowania kodu XML (LINQ to XML)

W tym artykule opisano sposób sterowania zachowaniem odstępu LINQ to XML.

Typowym scenariuszem jest odczytywanie wciętych plików XML, tworzenie drzewa XML w pamięci bez jakichkolwiek białych węzłów tekstowych (to nie zachowuje białych znaków), wykonywanie niektórych operacji na pliku XML, a następnie zapisywanie kodu XML z wcięciem. Podczas serializacji pliku XML z formatowaniem zachowywana jest tylko znaczący biały znak w drzewie XML. Jest to domyślne zachowanie LINQ to XML.

Inny typowy scenariusz polega na odczytaniu i zmodyfikowaniu kodu XML, który został już celowo wcięty. W żaden sposób nie trzeba zmieniać tego wcięcia. W tym celu w LINQ to XML jest zachowywany biały znak podczas ładowania lub analizowania kodu XML i wyłączania formatowania podczas serializacji XML.

W tym artykule opisano zachowanie białych znaków metod, które wypełniają drzewa XML. Aby uzyskać informacje o kontrolowaniu białego miejsca podczas serializacji drzew XML, zobacz [Zachowaj biały znak podczas serializacji](preserve-white-space-serializing.md).

## <a name="behavior-of-methods-that-populate-xml-trees"></a>Zachowanie metod, które wypełniają drzewa XML

Poniższe metody w <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> klasach i wypełniają drzewo XML. Można wypełnić drzewo XML z pliku, a <xref:System.IO.TextReader> , a <xref:System.Xml.XmlReader> lub ciągu:

- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>

Jeśli metoda nie przyjmuje <xref:System.Xml.Linq.LoadOptions> jako argument, metoda nie zachowuje nieznaczącego odstępu.

W większości przypadków, jeśli metoda przyjmuje <xref:System.Xml.Linq.LoadOptions> jako argument, można opcjonalnie zachować nieznaczące odstępy jako węzły tekstowe w drzewie XML. Jeśli jednak metoda ładuje plik XML z elementu <xref:System.Xml.XmlReader> , <xref:System.Xml.XmlReader> określa, czy biały znak zostanie zachowany, czy nie. Ustawienie <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> nie będzie miało żadnego efektu.

Przy użyciu tych metod, jeśli biały znak jest zachowywany, w drzewie XML jako węzły zostanie wstawiony nieznaczący biały znak <xref:System.Xml.Linq.XText> . Jeśli odstęp nie jest zachowywany, węzły tekstu nie są wstawiane.

Drzewo XML można utworzyć przy użyciu <xref:System.Xml.XmlWriter> . Węzły, które są zapisywane <xref:System.Xml.XmlWriter> w, są wypełniane w drzewie. Jednak podczas tworzenia drzewa XML przy użyciu tej metody wszystkie węzły są zachowywane niezależnie od tego, czy jest to biały znak, czy nie, czy biały znak jest znaczący.
