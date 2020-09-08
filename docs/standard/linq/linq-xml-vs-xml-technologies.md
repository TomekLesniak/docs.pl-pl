---
title: LINQ to XML a inne technologie XML
description: Dowiedz się, w jaki sposób LINQ to XML porównuje z wartościami XSLT, MSXML i XmlLite, aby lepiej wybierać technologie.
ms.date: 07/20/2015
ms.assetid: 01b8e746-12d3-471d-b811-7539e4547784
ms.openlocfilehash: ac118543bd1101e50edfcf99a609a715b885bfbd
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553480"
---
# <a name="linq-to-xml-vs-other-xml-technologies"></a>LINQ to XML a inne technologie XML

W tym artykule porównano LINQ to XML z następującymi technologiami XML: <xref:System.Xml.XmlReader> , XSLT, MSXML i XmlLite. Te informacje mogą pomóc zdecydować, które technologie mają być używane.

Aby zapoznać się z porównaniem LINQ to XML z Document Object Model (DOM), zobacz [LINQ to XML vs. dom](linq-xml-vs-dom.md).

## <a name="linq-to-xml-vs-xmlreader"></a>LINQ to XML a XmlReader

<xref:System.Xml.XmlReader> jest to szybki, progresywny parser, bez buforowania.

LINQ to XML jest zaimplementowana w systemie <xref:System.Xml.XmlReader> i są ściśle zintegrowane. Można jednak również używać <xref:System.Xml.XmlReader> bezpośrednio.

Załóżmy na przykład, że tworzysz usługę sieci Web, która będzie analizować setki dokumentów XML na sekundę, a dokumenty mają tę samą strukturę, co oznacza, że wystarczy napisać tylko jedną implementację kodu w celu przeanalizowania kodu XML. W takim przypadku prawdopodobnie chcesz używać <xref:System.Xml.XmlReader> bezpośrednio.

Natomiast w przypadku kompilowania systemu, który analizuje wiele mniejszych dokumentów XML, a każdy z nich jest inny, warto skorzystać z ulepszeń wydajności oferowanych przez LINQ to XML.

## <a name="linq-to-xml-vs-xslt"></a>LINQ to XML a XSLT

Zarówno LINQ to XML, jak i XSLT zapewniają szerokie możliwości transformacji dokumentu XML. XSLT jest podejściem deklaratywnym opartym na regułach. Zaawansowane programiści XSLT zapisują kod XSLT w stylu programowania funkcjonalnego, który podkreśla podejście bezstanowe. Przekształcenia można napisać przy użyciu czystych funkcji, które są implementowane bez efektów ubocznych. Takie podejście oparte na regułach lub funkcjonalnej jest nieznane dla wielu deweloperów i może być trudne i czasochłonne.

Język XSLT może być wydajnym systemem, który daje aplikacje o wysokiej wydajności. Na przykład niektóre duże firmy sieci Web używają XSLT jako sposobu generowania kodu HTML z pliku XML, który został pobrany z różnych rodzajów magazynów danych. Zarządzany aparat XSLT kompiluje kod XSLT do kodu środowiska uruchomieniowego języka wspólnego (CLR) i wykonuje jeszcze lepsze scenariusze niż w przypadku natywnego aparatu XSLT.

Jednak język XSLT nie korzysta z języka C# i Visual Basic znajomości wielu deweloperów. Wymagają od deweloperów pisania kodu w innym i złożonym języku programowania. Korzystanie z dwóch niezintegrowanych systemów programistycznych, takich jak C# (lub Visual Basic) i wyników XSLT w systemach oprogramowania, które są trudniejsze do opracowania i utrzymania.

Po utworzeniu wzorców LINQ to XML wyrażeń zapytania LINQ to XML przekształcenia są zaawansowaną technologią łatwą do użycia. Zasadniczo należy utworzyć dokument XML przy użyciu konstruowania funkcjonalnego, ściągania danych z różnych źródeł, konstruowania <xref:System.Xml.Linq.XElement> obiektów dynamicznie i asemblera całości w nowym drzewie XML. Transformacja może generować zupełnie nowy dokument. Konstruowanie transformacji w LINQ to XML jest stosunkowo łatwe i intuicyjne oraz możliwy do odczytania kod. Zmniejsza to koszty związane z programowaniem i konserwacją.

LINQ to XML nie ma zamiaru zastępować języka XSLT. Język XSLT jest nadal narzędziem wybranym dla skomplikowanych i skoncentrowanych na dokumentach przekształceń XML, zwłaszcza jeśli struktura dokumentu nie jest dobrze zdefiniowana.

Język XSLT ma zalety organizacja World Wide Web Consortium (W3C). Jeśli jest wymagane użycie tylko technologii, które są standardami, XSLT może być bardziej odpowiednie.

XSLT jest XML i dlatego można programistycznie manipulować.

## <a name="linq-to-xml-vs-msxml"></a>LINQ to XML a MSXML

MSXML jest technologią opartą na modelu COM do przetwarzania kodu XML, który jest dołączony do systemu Microsoft Windows. Program MSXML oferuje natywną implementację modelu DOM z obsługą języka XPath i XSLT. Zawiera również SAX2, które nie są buforowaniem, oparte na zdarzeniach.

Program MSXML działa prawidłowo, jest domyślnie bezpieczny w większości scenariuszy i można do niego uzyskać dostęp w programie Internet Explorer w celu przetwarzania kodu XML po stronie klienta w aplikacjach w stylu AJAX. Program MSXML może być używany z dowolnego języka programowania, który obsługuje COM, w tym C++, JavaScript i Visual Basic 6,0.

Program MSXML nie jest zalecany do użycia w kodzie zarządzanym opartym na środowisku CLR.

## <a name="linq-to-xml-vs-xmllite"></a>LINQ to XML a XmlLite

XmlLite to nie tylko buforowanie, analizator składni ściągania. Deweloperzy wykorzystują głównie XmlLite z C++. Nie zaleca się, aby deweloperzy używali XmlLite z kodem zarządzanym.

Główną zaletą XmlLite jest to lekki, szybki parser XML, który jest bezpieczny w większości scenariuszy. Powierzchnia obszaru zagrożenia jest mała. Jeśli konieczne jest przeanalizowanie dokumentów niezaufanych i chcesz chronić przed atakami, takimi jak odmowa usługi lub narażeniem na dane, może być dobrym rozwiązaniem.

XmlLite nie jest zintegrowany z zapytaniem Integrated Language (LINQ). Nie zapewnia to ulepszeń zwiększających produktywność, które są podstawą dla LINQ.

## <a name="see-also"></a>Zobacz też

- [Przegląd LINQ to XML](linq-xml-overview.md)
