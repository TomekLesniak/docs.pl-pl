---
title: Zachowywanie białych znaków podczas Serializing3
description: Dowiedz się, jak sterować białym znakiem podczas serializowania drzewa XML przy użyciu metod w klasach XElement i XDocument.
ms.date: 07/20/2015
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
ms.openlocfilehash: 01e68671e2fde1a2b5b1d0bc429841077ba0205f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303416"
---
# <a name="preserving-white-space-while-serializing"></a>Zachowywanie białych znaków podczas serializowania
W tym temacie opisano, jak sterować białym znakiem podczas serializowania drzewa XML.  
  
 Typowym scenariuszem jest odczytywanie wcięć XML, tworzenie drzewa XML w pamięci bez żadnych białych węzłów tekstowych (to nie zachowuje białych znaków), wykonywanie niektórych operacji na pliku XML, a następnie zapisywanie kodu XML z wcięciem. Podczas serializacji pliku XML z formatowaniem zachowywana jest tylko znaczący biały znak w drzewie XML. Jest to zachowanie domyślne dla programu [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .  
  
 Inny typowy scenariusz polega na odczytaniu i zmodyfikowaniu kodu XML, który został już celowo wcięty. W żaden sposób nie trzeba zmieniać tego wcięcia. W tym celu [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] należy zachować biały znak podczas ładowania lub analizowania kodu XML i wyłączyć formatowanie podczas serializacji XML.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Białe zachowanie metod, które serializować drzewa XML  
 Następujące metody w <xref:System.Xml.Linq.XElement> i <xref:System.Xml.Linq.XDocument> klasy serializacji drzewa XML. Można serializować drzewo XML do pliku, a <xref:System.IO.TextReader> lub <xref:System.Xml.XmlReader> . `ToString`Metoda jest serializowana do ciągu.  
  
- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
- [XElement. ToString ()](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
- [XDocument. ToString ()](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
 Jeśli metoda nie przyjmuje <xref:System.Xml.Linq.SaveOptions> argumentu, metoda będzie formatować (wcięcie) serializacji XML. W takim przypadku wszystkie nieznaczące białe znaki w drzewie XML są odrzucane.  
  
 Jeśli metoda przyjmuje <xref:System.Xml.Linq.SaveOptions> jako argument, można określić, że metoda nie formatuje (wcięcie) serializacji XML. W takim przypadku wszystkie odstępy w drzewie XML są zachowywane.  
