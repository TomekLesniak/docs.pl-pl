---
title: LINQ to XML a DOM
description: Istnieją kluczowe różnice między LINQ to XML i DOM. LINQ to XML obsługuje konstrukcję funkcjonalną i literały XML, które lepiej pokazują strukturę drzew XML, które kompilują.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 51c0e3d2-c047-4e6a-a423-d61a882400b7
ms.openlocfilehash: 905fe1b47361e2b96c79bc56cb831b3cb298e4de
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553323"
---
# <a name="linq-to-xml-vs-dom"></a>LINQ to XML a DOM

W tym artykule opisano niektóre kluczowe różnice między LINQ to XML i bieżącym głównym interfejsem API programowania plików XML, W3C Document Object Model (DOM).

## <a name="new-ways-to-construct-xml-trees"></a>Nowe sposoby konstruowania drzew XML

W modelu W3C DOM utworzysz drzewo XML od dołu do góry. oznacza to, że tworzysz dokument, tworzysz elementy, a następnie dodasz elementy do dokumentu.

Na przykład w poniższym przykładzie użyto typowego sposobu tworzenia drzewa XML przy użyciu implementacji modelu DOM firmy Microsoft <xref:System.Xml.XmlDocument> .

```csharp
XmlDocument doc = new XmlDocument();
XmlElement name = doc.CreateElement("Name");
name.InnerText = "Patrick Hines";
XmlElement phone1 = doc.CreateElement("Phone");
phone1.SetAttribute("Type", "Home");
phone1.InnerText = "206-555-0144";
XmlElement phone2 = doc.CreateElement("Phone");
phone2.SetAttribute("Type", "Work");
phone2.InnerText = "425-555-0145";
XmlElement street1 = doc.CreateElement("Street1");
street1.InnerText = "123 Main St";
XmlElement city = doc.CreateElement("City");
city.InnerText = "Mercer Island";
XmlElement state = doc.CreateElement("State");
state.InnerText = "WA";
XmlElement postal = doc.CreateElement("Postal");
postal.InnerText = "68042";
XmlElement address = doc.CreateElement("Address");
address.AppendChild(street1);
address.AppendChild(city);
address.AppendChild(state);
address.AppendChild(postal);
XmlElement contact = doc.CreateElement("Contact");
contact.AppendChild(name);
contact.AppendChild(phone1);
contact.AppendChild(phone2);
contact.AppendChild(address);
XmlElement contacts = doc.CreateElement("Contacts");
contacts.AppendChild(contact);
doc.AppendChild(contacts);
```

```vb
Dim doc As XmlDocument = New XmlDocument()
Dim name As XmlElement = doc.CreateElement("Name")
name.InnerText = "Patrick Hines"
Dim phone1 As XmlElement = doc.CreateElement("Phone")
phone1.SetAttribute("Type", "Home")
phone1.InnerText = "206-555-0144"
Dim phone2 As XmlElement = doc.CreateElement("Phone")
phone2.SetAttribute("Type", "Work")
phone2.InnerText = "425-555-0145"
Dim street1 As XmlElement = doc.CreateElement("Street1")
street1.InnerText = "123 Main St"
Dim city As XmlElement = doc.CreateElement("City")
city.InnerText = "Mercer Island"
Dim state As XmlElement = doc.CreateElement("State")
state.InnerText = "WA"
Dim postal As XmlElement = doc.CreateElement("Postal")
postal.InnerText = "68042"
Dim address As XmlElement = doc.CreateElement("Address")
address.AppendChild(street1)
address.AppendChild(city)
address.AppendChild(state)
address.AppendChild(postal)
Dim contact As XmlElement = doc.CreateElement("Contact")
contact.AppendChild(name)
contact.AppendChild(phone1)
contact.AppendChild(phone2)
contact.AppendChild(address)
Dim contacts As XmlElement = doc.CreateElement("Contacts")
contacts.AppendChild(contact)
doc.AppendChild(contacts)
Console.WriteLine(doc.OuterXml)
```

Ten styl kodowania ukrywa strukturę drzewa XML. LINQ to XML również obsługuje alternatywne podejście, *konstrukcja funkcjonalna*, która lepiej pokazuje strukturę. Takie podejście można wykonać za pomocą <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XAttribute> konstruktorów i. W Visual Basic można również wykonać za pomocą literałów XML. W tym przykładzie przedstawiono konstruowanie tego samego drzewa XML przy użyciu konstrukcji funkcjonalnej:

```csharp
XElement contacts =
    new XElement("Contacts",
        new XElement("Contact",
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144",
                new XAttribute("Type", "Home")),
            new XElement("phone", "425-555-0145",
                new XAttribute("Type", "Work")),
            new XElement("Address",
                new XElement("Street1", "123 Main St"),
                new XElement("City", "Mercer Island"),
                new XElement("State", "WA"),
                new XElement("Postal", "68042")
            )
        )
    );
```

```vb
Dim contacts = _
    <Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type="Home">206-555-0144</Phone>
            <Phone Type="Work">425-555-0145</Phone>
            <Address>
                <Street1>123 Main St</Street1>
                <City>Mercer Island</City>
                <State>WA</State>
                <Postal>68042</Postal>
            </Address>
        </Contact>
    </Contacts>
```

Zwróć uwagę, że Wcięcie kodu w celu skonstruowania drzewa XML pokazuje strukturę bazowego kodu XML. Wersja Visual Basic używa literałów XML.

Aby uzyskać więcej informacji, zobacz [drzewa XML](functional-construction.md).

## <a name="work-directly-with-xml-elements"></a>Pracuj bezpośrednio z elementami XML

Gdy program jest używany w języku XML, główny fokus jest zazwyczaj na elementach XML i prawdopodobnie na atrybutach. W LINQ to XML można bezpośrednio korzystać z elementów i atrybutów XML. Można na przykład wykonać następujące czynności:

- Utwórz elementy XML bez używania obiektu dokumentu. Upraszcza to programowanie, gdy trzeba będzie korzystać z fragmentów drzew XML.
- Załaduj `T:System.Xml.Linq.XElement` obiekty bezpośrednio z pliku XML.
- Serializacja `T:System.Xml.Linq.XElement` obiektów do pliku lub strumienia.

Porównaj ten element z W3C DOM, w którym dokument XML jest używany jako kontener logiczny dla drzewa XML. W modelu DOM, węzły XML, w tym elementy i atrybuty, muszą zostać utworzone w kontekście dokumentu XML. Oto fragment kodu do utworzenia elementu Name w modelu DOM:

```csharp
XmlDocument doc = new XmlDocument();
XmlElement name = doc.CreateElement("Name");
name.InnerText = "Patrick Hines";
doc.AppendChild(name);
```

```vb
Dim doc As XmlDocument = New XmlDocument()
Dim name As XmlElement = doc.CreateElement("Name")
name.InnerText = "Patrick Hines"
doc.AppendChild(name)
```

Jeśli chcesz użyć elementu w wielu dokumentach, należy zaimportować węzły między dokumentami. LINQ to XML pozwala uniknąć tej warstwy złożoności.

W przypadku używania LINQ to XML Klasa jest używana <xref:System.Xml.Linq.XDocument> tylko wtedy, gdy chcesz dodać komentarz lub instrukcję przetwarzania na poziomie głównym dokumentu.

## <a name="simplified-handling-of-names-and-namespaces"></a>Uproszczona obsługa nazw i przestrzeni nazw

Obsługa nazw, przestrzeni nazw i prefiksów przestrzeni nazw jest ogólnie złożonym elementem programowania XML. LINQ to XML upraszcza nazwy i przestrzenie nazw, eliminując wymóg postępowania z prefiksami przestrzeni nazw. Jeśli chcesz kontrolować prefiksy przestrzeni nazw, możesz. Ale jeśli zdecydujesz się nie jawnie kontrolować prefiksów przestrzeni nazw, LINQ to XML przypisze prefiksy przestrzeni nazw podczas serializacji, jeśli są wymagane lub będą serializować przy użyciu domyślnych przestrzeni nazw, jeśli nie są. Jeśli są używane domyślne przestrzenie nazw, nie będzie żadnych prefiksów przestrzeni nazw w dokumencie będącym wynikiem. Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

Innym problemem z modelem DOM jest to, że nie pozwala na zmianę nazwy węzła. Zamiast tego należy utworzyć nowy węzeł i skopiować do niego wszystkie węzły podrzędne, tracąc oryginalną tożsamość węzła. LINQ to XML uniknąć tego problemu, umożliwiając ustawienie <xref:System.Xml.Linq.XName> właściwości w węźle.

## <a name="static-method-support-for-loading-xml"></a>Obsługa metody statycznej do ładowania pliku XML

LINQ to XML umożliwia ładowanie XML przy użyciu metod statycznych zamiast metod instancji. Upraszcza to ładowanie i analizowanie. Aby uzyskać więcej informacji, zobacz [jak załadować XML z pliku](load-xml-file.md).

## <a name="removal-of-support-for-dtd-constructs"></a>Usuwanie obsługi dla konstrukcji DTD

LINQ to XML bardziej upraszcza programowanie XML przez usunięcie obsługi jednostek i odwołań do jednostek. Zarządzanie jednostkami jest skomplikowane i rzadko jest używane. Usunięcie ich obsługi zwiększa wydajność i upraszcza interfejs programowania. Gdy zostanie wypełnione drzewo LINQ to XML, wszystkie jednostki DTD są rozwinięte.

## <a name="support-for-fragments"></a>Obsługa fragmentów

LINQ to XML nie zapewnia równoważnej `XmlDocumentFragment` klasy. W wielu przypadkach `XmlDocumentFragment` koncepcje mogą być obsługiwane przez wynik zapytania, które zostało wpisane w <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XNode> lub <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> .

## <a name="support-for-xpathnavigator"></a>Obsługa elementu XPathNavigator

LINQ to XML zapewnia obsługę <xref:System.Xml.XPath.XPathNavigator> za pomocą metod rozszerzających w <xref:System.Xml.XPath?displayProperty=nameWithType> przestrzeni nazw. Aby uzyskać więcej informacji, zobacz <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.

## <a name="support-for-white-space-and-indentation"></a>Obsługa białych znaków i wcięć

LINQ to XML obsługuje biały znak więcej niż w modelu DOM.

Typowym scenariuszem jest odczytywanie wciętych plików XML, tworzenie drzewa XML w pamięci bez jakichkolwiek białych węzłów tekstowych (to nie zachowuje białych znaków), wykonywanie niektórych operacji na pliku XML, a następnie zapisywanie kodu XML z wcięciem. Podczas serializacji pliku XML z formatowaniem zachowywana jest tylko znaczący biały znak w drzewie XML. Jest to domyślne zachowanie LINQ to XML.

Inny typowy scenariusz polega na odczytaniu i zmodyfikowaniu kodu XML, który został już celowo wcięty. W żaden sposób nie trzeba zmieniać tego wcięcia. W LINQ to XML można to zrobić, wykonując następujące czynności:

- Zachowywanie białych znaków podczas ładowania lub analizowania kodu XML.
- Wyłączanie formatowania podczas serializacji kodu XML.

LINQ to XML przechowuje biały znak jako <xref:System.Xml.Linq.XText> węzeł, zamiast mieć wyspecjalizowany <xref:System.Xml.XmlNodeType.Whitespace> Typ węzła, jak dom.

## <a name="support-for-annotations"></a>Obsługa adnotacji

Elementy LINQ to XML obsługują rozszerzalny zestaw adnotacji. Jest to przydatne do śledzenia różnych informacji o elemencie, takich jak informacje o schemacie, informacje o tym, czy element jest powiązany z interfejsem użytkownika, czy też innym rodzajem informacji specyficznych dla aplikacji. Aby uzyskać więcej informacji, zobacz [LINQ to XML adnotacje](linq-xml-annotations.md).

## <a name="support-for-schema-information"></a>Obsługa informacji o schemacie

LINQ to XML zapewnia obsługę walidacji XSD za pomocą metod rozszerzających w <xref:System.Xml.Schema?displayProperty=nameWithType> przestrzeni nazw. Można sprawdzić, czy drzewo XML jest zgodne z XSD. Drzewo XML można wypełnić za pomocą sprawdzonych po walidacji schematu (PSVI). Aby uzyskać więcej informacji, zobacz [Jak sprawdzić przy użyciu XSD](validate-xsd.md) i <xref:System.Xml.Schema.Extensions> .

## <a name="see-also"></a>Zobacz też

- [Przegląd LINQ to XML](linq-xml-overview.md)
