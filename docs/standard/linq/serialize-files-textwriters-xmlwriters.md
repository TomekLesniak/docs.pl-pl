---
title: Serializacja do plików, textwrites i xmlwrites-LINQ to XML
description: Można serializować drzewa XML do pliku, TextWriter lub XmlWriter i można serializować dowolny składnik XML, w tym XDocument i XElement, do ciągu przy użyciu metody ToString.
ms.date: 07/20/2015
ms.assetid: bd3ea6f7-895b-4ff4-a625-fe2bb55b1886
ms.openlocfilehash: 20651c06a759d83934c4b035a42eac7c2700eb9f
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553813"
---
# <a name="serialize-to-files-textwriters-and-xmlwriters-linq-to-xml"></a>Serializacja do plików, textwrites i xmlwrites (LINQ to XML)

Można serializować drzewa XML do <xref:System.IO.File> , a <xref:System.IO.TextWriter> lub <xref:System.Xml.XmlWriter> .

Można serializować dowolny składnik XML, w tym <xref:System.Xml.Linq.XDocument> i <xref:System.Xml.Linq.XElement> , do ciągu przy użyciu `ToString` metody.

Jeśli chcesz pominąć formatowanie podczas serializacji do ciągu, możesz użyć <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> metody.

Zachowanie domyślne podczas serializowania do pliku ma format (wcięcie) otrzymany dokument XML. Po zwiększeniu wcięcia nieznaczący biały znak w drzewie XML nie jest zachowywany. Aby serializować z formatowaniem, użyj jednego z przeciążeń następujących metod, które nie przyjmują <xref:System.Xml.Linq.SaveOptions> argumentu:

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

Jeśli chcesz, aby opcja nie była wcięty i aby zachować nieznaczący biały znak w drzewie XML, użyj jednego z przeciążeń następujących metod, które przyjmuje <xref:System.Xml.Linq.SaveOptions> jako argument:

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

Przykłady można znaleźć w odpowiednim artykule referencyjnym.
