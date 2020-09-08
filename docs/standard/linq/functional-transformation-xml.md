---
title: Przekształcenie funkcjonalne LINQ to XML XML
description: Dowiedz się więcej na temat podejścia do przekształcania funkcjonalnego, aby modyfikować dokumenty XML i jak różni się od podejścia proceduralnego.
ms.date: 07/20/2015
ms.assetid: 0ccb9251-38d7-44e3-9b84-1b5fe25e4b59
ms.openlocfilehash: b23288e013a4104b21523e17e1f266a9f712c451
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553017"
---
# <a name="functional-transformation-of-xml-linq-to-xml"></a>Przekształcanie funkcjonalne kodu XML (LINQ to XML)

W tym artykule omówiono ścisłe podejście do transformacji funkcjonalnej w celu modyfikowania dokumentów XML i kontrastu z podejściem proceduralnym.

## <a name="modifying-an-xml-document"></a>Modyfikowanie dokumentu XML

Jednym z najbardziej typowych zadań dla programisty XML jest przekształcanie XML z jednego kształtu do drugiego. Kształt dokumentu XML jest strukturą dokumentu, która obejmuje następujące elementy:

- Hierarchia wyrażona w dokumencie.
- Nazwy elementów i atrybutów.
- Typy danych elementów i atrybutów.

Ogólnie rzecz biorąc, najbardziej efektywne podejście do przekształcania kodu XML z jednego kształtu na drugi to czysty przekształcenie funkcjonalne. W ramach tego podejścia podstawowe zadanie programisty polega na utworzeniu transformacji, która jest stosowana do całego dokumentu XML (lub do jednego lub większej liczby ściśle zdefiniowanych węzłów). Przekształcanie funkcjonalne jest raczej najłatwiejszym w kodzie (po zapoznaniu się z podejściem programisty), zapewnia najbardziej łatwość obsługi kod i jest często bardziej zwarty niż alternatywne podejścia.

### <a name="xml-functional-transformational-technologies"></a>Technologie transformacji funkcjonalnej XML

Firma Microsoft oferuje dwie funkcjonalne technologie przekształcania do użycia w dokumentach XML: XSLT i LINQ to XML. Język XSLT jest obsługiwany w <xref:System.Xml.Xsl> zarządzanej przestrzeni nazw i natywnej implementacji COM programu MSXML. Chociaż XSLT jest niezawodną technologią do manipulowania dokumentami XML, wymaga znajomości specjalistycznej domeny, a mianowicie języka XSLT i obsługujących je interfejsów API.

LINQ to XML udostępnia narzędzia niezbędne do kodu przekształceń czystych funkcjonalnie w sposób wyraźny i zaawansowany w kodzie C# lub Visual Basic. Przykładowo wiele przykładów w dokumentacji LINQ to XML używa czystego podejścia funkcjonalnego. Ponadto w [samouczku: manipulowanie zawartością w](xml-shape-wordprocessingml-documents.md) samouczku dotyczącego dokumentu WordprocessingML używamy LINQ to XML w funkcjonalne podejścia do manipulowania informacjami w dokumencie programu Microsoft Word.

Aby zapoznać się z bardziej szczegółowym porównaniem LINQ to XML z innymi technologiami Microsoft XML, zobacz [LINQ to XML a inne technologie XML](linq-xml-vs-xml-technologies.md).

Język XSLT jest zalecanym narzędziem dla transformacji skoncentrowanych na dokumentach, gdy dokument źródłowy ma nieregularną strukturę. Jednak LINQ to XML mogą również wykonywać transformacje skoncentrowane na dokumentach. Aby uzyskać więcej informacji, zobacz [jak używać adnotacji do przekształcania drzew LINQ to XML w stylu XSLT](use-annotations-transform-linq-xml-trees-xslt-style.md).

## <a name="see-also"></a>Zobacz też

- [Wprowadzenie do czystych transformacji funkcjonalnych](introduction-pure-functional-transformations.md)
- [Samouczek: manipulowanie zawartością w dokumencie WordprocessingML](xml-shape-wordprocessingml-documents.md)
- [LINQ to XML a inne technologie XML](linq-xml-vs-xml-technologies.md)
