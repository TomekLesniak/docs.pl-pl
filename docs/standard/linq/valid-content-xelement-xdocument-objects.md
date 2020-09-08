---
title: Prawidłowa zawartość obiektów XElement i XDocument-LINQ to XML
description: Konstruktory XElement i XDocumenty akceptują wiele typów argumentów, w tym kolekcje zwracane z zapytań. Istnieją inne konstruktory i funkcje umożliwiające dodawanie zawartości XML.
ms.date: 07/20/2015
ms.assetid: 0d253586-2b97-459f-b1a7-f30f38f3ed9f
ms.openlocfilehash: e0288dce06f8040385c9b9a30335fd039d3c45bd
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553765"
---
# <a name="valid-content-of-xelement-and-xdocument-objects-linq-to-xml"></a>Prawidłowa zawartość obiektów XElement i XDocument (LINQ to XML)

W tym artykule opisano prawidłowe argumenty, które mogą być przekazane do konstruktorów, oraz metody, które służą do dodawania zawartości do elementów i dokumentów.

## <a name="valid-types-for-the-xelement-constructor"></a>Prawidłowe typy dla konstruktora XElement

Zapytania często są oceniane <xref:System.Collections.Generic.IEnumerable%601> do <xref:System.Xml.Linq.XElement> lub <xref:System.Collections.Generic.IEnumerable%601> z <xref:System.Xml.Linq.XAttribute> . Można przekazać kolekcje <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute> obiekty do <xref:System.Xml.Linq.XElement> konstruktora. Dlatego warto przekazać wyniki zapytania jako zawartość do metod i konstruktorów używanych do wypełniania drzew XML.

Podczas dodawania prostej zawartości można przekazywać różne typy do tej metody, w tym:

- <xref:System.String>
- <xref:System.Double>
- <xref:System.Single>
- <xref:System.Decimal>
- <xref:System.Boolean>
- <xref:System.DateTime>
- <xref:System.TimeSpan>
- <xref:System.DateTimeOffset>
- Dowolny typ, który implementuje `Object.ToString` .
- Dowolny typ, który implementuje <xref:System.Collections.Generic.IEnumerable%601> .

Podczas dodawania zawartości złożonej różne typy mogą być przesyłane do tej metody, w tym:

- <xref:System.Xml.Linq.XObject>
- <xref:System.Xml.Linq.XNode>
- <xref:System.Xml.Linq.XAttribute>
- Dowolny typ, który implementuje <xref:System.Collections.Generic.IEnumerable%601>

Jeśli obiekt implementuje <xref:System.Collections.Generic.IEnumerable%601> , kolekcja w obiekcie jest wyliczana i dodawane są wszystkie elementy w kolekcji. Jeśli kolekcja zawiera <xref:System.Xml.Linq.XNode> obiekty lub <xref:System.Xml.Linq.XAttribute> , każdy element w kolekcji zostanie dodany osobno. Jeśli kolekcja zawiera tekst (lub obiekty, które są konwertowane na tekst), tekst w kolekcji zostanie połączony i dodany jako pojedynczy węzeł tekstowy.

Jeśli zawartość jest `null` , nic nie jest dodawane. Podczas przekazywania kolekcji elementy w kolekcji mogą być `null` . `null`Element w kolekcji nie ma wpływu na drzewo.

Dodany atrybut musi mieć unikatową nazwę w obrębie zawartego elementu.

W przypadku dodawania <xref:System.Xml.Linq.XNode> lub <xref:System.Xml.Linq.XAttribute> obiektów, jeśli nowa zawartość nie ma elementu nadrzędnego, obiekty są po prostu dołączone do drzewa XML. Jeśli nowa zawartość jest już nadrzędna i jest częścią innego drzewa XML, Nowa zawartość jest klonowana, a nowo sklonowana zawartość jest dołączona do drzewa XML.

## <a name="valid-types-for-the-xdocument-constructor"></a>Prawidłowe typy dla konstruktora XDocument

Atrybuty i zawartość prosta nie mogą zostać dodane do dokumentu.

Nie ma wielu scenariuszy, które wymagają utworzenia <xref:System.Xml.Linq.XDocument> . Zamiast tego można zazwyczaj utworzyć drzewa XML z <xref:System.Xml.Linq.XElement> węzłem głównym. Jeśli użytkownik nie ma konkretnego wymagania dotyczącego tworzenia dokumentu (na przykład dlatego, że konieczne jest utworzenie instrukcji przetwarzania i komentarzy na najwyższym poziomie lub konieczność obsługi typów dokumentów), często jest wygodniejszy do użycia <xref:System.Xml.Linq.XElement> jako węzeł główny.

Prawidłowe typy dla <xref:System.Xml.Linq.XDocument.%23ctor%2A> konstruktora obejmują następujące elementy:

- Zero lub jeden <xref:System.Xml.Linq.XDocumentType> obiekt. Typy dokumentów muszą występować przed elementem.
- Zero lub jeden element.
- Zero lub więcej komentarzy.
- Zero lub więcej instrukcji przetwarzania.
- Zero lub więcej węzłów tekstowych, które zawierają tylko biały znak.

## <a name="constructors-and-functions-for-adding-content"></a>Konstruktory i funkcje umożliwiające dodawanie zawartości

Poniższe metody pozwalają dodać zawartość podrzędną do elementu <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XDocument> :

|Metoda|Opis|
|------------|-----------------|
|<xref:System.Xml.Linq.XElement.%23ctor%2A>|Konstruuje <xref:System.Xml.Linq.XElement> .|
|<xref:System.Xml.Linq.XDocument.%23ctor%2A>|Konstruuje a <xref:System.Xml.Linq.XDocument> .|
|<xref:System.Xml.Linq.XContainer.Add%2A>|Dodaje do końca zawartości podrzędnej <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XDocument> .|
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Dodaje zawartość po <xref:System.Xml.Linq.XNode> .|
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Dodaje zawartość przed <xref:System.Xml.Linq.XNode> .|
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Dodaje zawartość na początku zawartości podrzędnej <xref:System.Xml.Linq.XContainer> .|
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A>|Zamienia całą zawartość (węzły podrzędne i atrybuty) obiektu <xref:System.Xml.Linq.XElement> .|
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|Zastępuje atrybuty <xref:System.Xml.Linq.XElement> .|
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|Zamienia węzły podrzędne na nową zawartość.|
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A>|Zamienia węzeł na nową zawartość.|

## <a name="see-also"></a>Zobacz też

- [Drzewa XML](functional-construction.md)
