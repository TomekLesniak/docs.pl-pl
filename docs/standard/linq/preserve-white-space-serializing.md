---
title: Zachowaj biały znak podczas serializacji-LINQ to XML
description: W przypadku serializowania drzewa XML można kontrolować biały znak na różne sposoby.
ms.date: 07/20/2015
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
ms.openlocfilehash: 6d907e68a2df3905794b555954330f31b5e75655
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553074"
---
# <a name="preserve-white-space-while-serializing-linq-to-xml"></a>Zachowaj biały znak podczas serializacji (LINQ to XML)

W tym artykule opisano sposób sterowania białym znakiem podczas serializowania drzewa XML.

Typowym scenariuszem jest odczytywanie wciętych plików XML, tworzenie drzewa XML w pamięci bez jakichkolwiek białych węzłów tekstowych (to nie zachowuje białych znaków), wykonywanie niektórych operacji na pliku XML, a następnie zapisywanie kodu XML z wcięciem. Podczas serializacji pliku XML z formatowaniem zachowywana jest tylko znaczący biały znak w drzewie XML. Jest to domyślne zachowanie LINQ to XML.

Inny typowy scenariusz polega na odczytaniu i zmodyfikowaniu kodu XML, który został już celowo wcięty. W żaden sposób nie trzeba zmieniać tego wcięcia. W tym celu w LINQ to XML jest zachowywany biały znak podczas ładowania lub analizowania kodu XML i wyłączania formatowania podczas serializacji XML.

## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Białe zachowanie metod, które serializować drzewa XML

Następujące metody w <xref:System.Xml.Linq.XElement> i <xref:System.Xml.Linq.XDocument> klasy serializacji drzewa XML. Można serializować drzewo XML do pliku, a <xref:System.IO.TextReader> lub <xref:System.Xml.XmlReader> . `ToString`Metoda jest serializowana do ciągu.

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>
- [XElement. ToString ()](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
- [XDocument. ToString ()](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)

Jeśli metoda nie przyjmuje <xref:System.Xml.Linq.SaveOptions> jako argument, metoda będzie formatować (wcięcie) serializacji XML. W takim przypadku wszystkie nieznaczące białe znaki w drzewie XML są odrzucane.

Jeśli metoda przyjmuje <xref:System.Xml.Linq.SaveOptions> jako argument, można określić, że metoda nie formatuje (wcięcie) serializacji XML. W takim przypadku wszystkie odstępy w drzewie XML są zachowywane.
