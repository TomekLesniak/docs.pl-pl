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
# <a name="serialize-to-files-textwriters-and-xmlwriters-linq-to-xml"></a><span data-ttu-id="d68b5-103">Serializacja do plików, textwrites i xmlwrites (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="d68b5-103">Serialize to files, TextWriters, and XmlWriters (LINQ to XML)</span></span>

<span data-ttu-id="d68b5-104">Można serializować drzewa XML do <xref:System.IO.File> , a <xref:System.IO.TextWriter> lub <xref:System.Xml.XmlWriter> .</span><span class="sxs-lookup"><span data-stu-id="d68b5-104">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>

<span data-ttu-id="d68b5-105">Można serializować dowolny składnik XML, w tym <xref:System.Xml.Linq.XDocument> i <xref:System.Xml.Linq.XElement> , do ciągu przy użyciu `ToString` metody.</span><span class="sxs-lookup"><span data-stu-id="d68b5-105">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>

<span data-ttu-id="d68b5-106">Jeśli chcesz pominąć formatowanie podczas serializacji do ciągu, możesz użyć <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="d68b5-106">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="d68b5-107">Zachowanie domyślne podczas serializowania do pliku ma format (wcięcie) otrzymany dokument XML.</span><span class="sxs-lookup"><span data-stu-id="d68b5-107">The default behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="d68b5-108">Po zwiększeniu wcięcia nieznaczący biały znak w drzewie XML nie jest zachowywany.</span><span class="sxs-lookup"><span data-stu-id="d68b5-108">When you indent, the insignificant white space in the XML tree isn't preserved.</span></span> <span data-ttu-id="d68b5-109">Aby serializować z formatowaniem, użyj jednego z przeciążeń następujących metod, które nie przyjmują <xref:System.Xml.Linq.SaveOptions> argumentu:</span><span class="sxs-lookup"><span data-stu-id="d68b5-109">To serialize with formatting, use one of the overloads of the following methods that don't take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

<span data-ttu-id="d68b5-110">Jeśli chcesz, aby opcja nie była wcięty i aby zachować nieznaczący biały znak w drzewie XML, użyj jednego z przeciążeń następujących metod, które przyjmuje <xref:System.Xml.Linq.SaveOptions> jako argument:</span><span class="sxs-lookup"><span data-stu-id="d68b5-110">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

<span data-ttu-id="d68b5-111">Przykłady można znaleźć w odpowiednim artykule referencyjnym.</span><span class="sxs-lookup"><span data-stu-id="d68b5-111">For examples, see the appropriate reference article.</span></span>
