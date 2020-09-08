---
title: Przegląd przestrzeni nazw — LINQ to XML
description: Informacje o nazwach XML, przestrzeniach nazw XML i prefiksach przestrzeni nazw XML oraz o klasach XName i XNamespace.
ms.date: 07/20/2015
ms.assetid: 16283322-8238-4918-ab11-802ac6748eb7
ms.openlocfilehash: 81fe678a8d6be32461c675cc527595033e826165
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553143"
---
# <a name="namespaces-overview-linq-to-xml"></a>Przegląd przestrzeni nazw (LINQ to XML)

W tym artykule wprowadzono *nazwy XML*, *przestrzenie*nazw XML, *prefiksy przestrzeni nazw XML*oraz <xref:System.Xml.Linq.XName> <xref:System.Xml.Linq.XNamespace> klasy i.

Nazwy XML często są źródłem złożoności w programowaniu XML. Nazwa XML składa się z przestrzeni nazw XML (nazywanej również identyfikatorem URI przestrzeni nazw XML) i nazwy lokalnej. Przestrzeń nazw XML jest podobna do przestrzeni nazw w programie .NET. Umożliwia ona unikatową kwalifikowanie nazw elementów i atrybutów w celu uniknięcia konfliktów nazw między różnymi częściami dokumentu XML. Po zadeklarowaniu przestrzeni nazw XML można wybrać lokalną nazwę, która musi być unikatowa w obrębie tej przestrzeni nazw.

Innym aspektem nazw XML są prefiksy przestrzeni nazw XML, które powodują większość złożoności nazw XML. Te prefiksy umożliwiają utworzenie skrótu dla przestrzeni nazw XML, co sprawia, że dokument XML jest bardziej zwięzły i zrozumiały. Jednak znaczenie prefiksu XML zależy od kontekstu, który zwiększa złożoność. Na przykład prefiks XML `aw` może być skojarzony z jedną przestrzenią nazw XML w części drzewa XML i z inną przestrzenią nazw w innej części.

Jedną z zalet korzystania z LINQ to XML w języku C# jest to, że nie trzeba używać prefiksów XML. Gdy LINQ to XML ładuje lub analizuje dokument XML, każdy prefiks XML jest rozpoznawany jako odpowiadający mu obszar nazw XML. Po wykonaniu tej czynności podczas pracy z dokumentem, który używa przestrzeni nazw, prawie zawsze uzyskuje się dostęp do przestrzeni nazw za pomocą identyfikatora URI przestrzeni nazw, a nie za pośrednictwem prefiksu przestrzeni nazw. Gdy deweloperzy pracują z nazwami XML w LINQ to XML zawsze pracują z w pełni kwalifikowaną nazwą XML (czyli przestrzenią nazw XML i nazwą lokalną). Jednak LINQ to XML umożliwia współdziałanie z prefiksami przestrzeni nazw i kontrolowanie ich w razie potrzeby.

W przypadku używania LINQ to XML z literałami Visual Basic i XML należy używać prefiksów przestrzeni nazw podczas pracy z dokumentami w przestrzeni nazw.

W LINQ to XML Klasa, która reprezentuje nazwy XML, to <xref:System.Xml.Linq.XName> . Nazwy XML często pojawiają się w interfejsie API LINQ to XML i wszędzie tam, gdzie jest wymagana nazwa XML, <xref:System.Xml.Linq.XName> parametr zostanie znaleziony. Jednak rzadko pracujemy bezpośrednio z <xref:System.Xml.Linq.XName> . <xref:System.Xml.Linq.XName> zawiera niejawną konwersję z ciągu.

Aby uzyskać więcej informacji, zobacz <xref:System.Xml.Linq.XNamespace> i <xref:System.Xml.Linq.XName>.
