---
title: Zarządzanie przestrzeniami nazw w dokumencie XML
description: Dowiedz się, jak zarządzać przestrzeniami nazw w dokumencie XML. Przestrzenie nazw XML kojarzą nazwy elementów i atrybutów w dokumencie XML z niestandardowymi i wstępnie zdefiniowanymi identyfikatorami URI.
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 682643fc-b848-4e42-8c0d-50deeaeb5f2a
ms.openlocfilehash: 500c477eaa98b2858573e1012c62db4bc6c68137
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548094"
---
# <a name="managing-namespaces-in-an-xml-document"></a>Zarządzanie przestrzeniami nazw w dokumencie XML
Przestrzenie nazw XML kojarzą nazwy elementów i atrybutów w dokumencie XML z niestandardowymi i wstępnie zdefiniowanymi identyfikatorami URI. Aby utworzyć te skojarzenia, należy zdefiniować prefiksy dla identyfikatorów URI przestrzeni nazw, a następnie użyć tych prefiksów do kwalifikowania nazw elementów i atrybutów w danych XML. Przestrzenie nazw uniemożliwiają kolizje nazw elementów i atrybutów, a elementy i atrybuty o tej samej nazwie mogą być obsługiwane i sprawdzane inaczej.  
  
<a name="declare"></a>
## <a name="declaring-namespaces"></a>Deklarowanie przestrzeni nazw  
 Aby zadeklarować przestrzeń nazw dla elementu, należy użyć `xmlns:` atrybutu:  
  
 `xmlns:<name>=<"uri">`  
  
 gdzie `<name>` jest prefiks przestrzeni nazw i `<"uri">` jest identyfikatorem URI, który identyfikuje przestrzeń nazw. Po zadeklarowaniu prefiksu można go użyć do kwalifikowania elementów i atrybutów w dokumencie XML i kojarzenia ich z identyfikatorem URI przestrzeni nazw. Ponieważ prefiks przestrzeni nazw jest używany w całym dokumencie, powinien mieć krótki czas.  
  
 Ten przykład definiuje dwa `BOOK` elementy. Pierwszy element jest kwalifikowana przez prefiks, `mybook` , a drugi element jest kwalifikowana przez prefiks, `bb` . Każdy prefiks jest skojarzony z innym identyfikatorem URI przestrzeni nazw:  
  
```xml  
<mybook:BOOK xmlns:mybook="http://www.contoso.com/books.dtd">  
<bb:BOOK xmlns:bb="urn:blueyonderairlines" />
</mybook>
```  
  
 Aby wyrównać, że element jest częścią określonego obszaru nazw, Dodaj do niego prefiks przestrzeni nazw. Na przykład jeśli `Author` element należy do `mybook` przestrzeni nazw, zostanie zadeklarowany jako `<mybook:Author>` .  
  
<a name="scope"></a>
## <a name="declaration-scope"></a>Zakres deklaracji  
 Przestrzeń nazw zaczyna się od jej punktu deklaracji do końca elementu, w którym został zadeklarowany. W tym przykładzie przestrzeń nazw zdefiniowana w `BOOK` elemencie nie ma zastosowania do elementów poza `BOOK` elementem, takich jak `Publisher` element:  
  
```xml  
<Author>Joe Smith</Author>  
<BOOK xmlns:book="http://www.contoso.com">  
    <title>My Wonderful Day</title>  
      <price>$3.95</price>  
</BOOK>  
<Publisher>  
    <Name>MSPress</Name>  
</Publisher>  
```  
  
 Przestrzeń nazw musi być zadeklarowana, zanim będzie można jej użyć, ale nie musi być wyświetlana u góry dokumentu XML.  
  
 W przypadku używania wielu przestrzeni nazw w dokumencie XML, można zdefiniować jeden obszar nazw jako domyślną przestrzeń nazw, aby utworzyć przejrzysty dokument szukania. Domyślna przestrzeń nazw jest zadeklarowana w elemencie głównym i ma zastosowanie do wszystkich niekwalifikowanych elementów w dokumencie. Domyślne przestrzenie nazw mają zastosowanie tylko do elementów, a nie do atrybutów.  
  
 Aby użyć domyślnej przestrzeni nazw, Pomiń prefiks i dwukropek z deklaracji w elemencie:  
  
```xml  
<BOOK xmlns="http://www.contoso.com/books.dtd">  
...
</BOOK>
```  
  
## <a name="managing-namespaces"></a>Zarządzanie przestrzeniami nazw  
 <xref:System.Xml.XmlNamespaceManager>Klasa przechowuje kolekcję identyfikatorów URI przestrzeni nazw i ich prefiksów, a następnie umożliwia wyszukiwanie, Dodawanie i usuwanie przestrzeni nazw z tej kolekcji. W niektórych kontekstach Ta klasa jest wymagana w celu uzyskania lepszej wydajności przetwarzania kodu XML. Na przykład <xref:System.Xml.Xsl.XsltContext> Klasa używa <xref:System.Xml.XmlNamespaceManager> dla obsługi XPath.  
  
 Menedżer przestrzeni nazw nie wykonuje żadnych walidacji w przestrzeniach nazw, ale zakłada, że prefiksy i przestrzenie nazw zostały już zweryfikowane i są zgodne ze specyfikacją [przestrzeni nazw W3C](https://www.w3.org/TR/REC-xml-names/) .  
  
> [!NOTE]
> LINQ TO XML w [C#](../../linq/linq-xml-overview.md) i [Visual Basic](../../linq/linq-xml-overview.md) nie używać <xref:System.Xml.XmlNamespaceManager> do zarządzania przestrzeniami nazw. Zobacz [Praca z przestrzeniami nazw XML (C#)](../../linq/namespaces-overview.md) i [Praca z przestrzeniami nazw XML (Visual Basic)](../../linq/namespaces-overview.md) w dokumentacji LINQ, aby uzyskać informacje na temat zarządzania przestrzeniami nazw przy użyciu LINQ to XML.  
  
 Poniżej przedstawiono niektóre zadania zarządzania i wyszukiwania, które można wykonać za pomocą <xref:System.Xml.XmlNamespaceManager> klasy. Aby uzyskać więcej informacji i przykładów, postępuj zgodnie z linkami do strony odniesienia dla każdej metody lub właściwości.  
  
|Działanie|Zastosowanie|  
|--------|---------|  
|Dodawanie przestrzeni nazw|Metoda <xref:System.Xml.XmlNamespaceManager.AddNamespace%2A>|  
|Usuwanie przestrzeni nazw|Metoda <xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A>|  
|Znajdź identyfikator URI dla domyślnej przestrzeni nazw|<xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A> wartość|  
|Znajdź identyfikator URI dla prefiksu przestrzeni nazw|Metoda <xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A>|  
|Znajdź prefiks dla identyfikatora URI przestrzeni nazw|Metoda <xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A>|  
|Pobierz listę przestrzeni nazw w bieżącym węźle|Metoda <xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A>|  
|Określanie zakresu przestrzeni nazw|<xref:System.Xml.XmlNamespaceManager.PushScope%2A> i <xref:System.Xml.XmlNamespaceManager.PopScope%2A> metody|  
|Sprawdź, czy prefiks jest zdefiniowany w bieżącym zakresie|Metoda <xref:System.Xml.XmlNamespaceManager.HasNamespace%2A>|  
|Pobierz tabelę nazw służącą do wyszukiwania prefiksów i identyfikatorów URI|<xref:System.Xml.XmlNamespaceManager.NameTable%2A> wartość|  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Xml.XmlNamespaceManager>
- [Dokumenty i dane XML](index.md)
