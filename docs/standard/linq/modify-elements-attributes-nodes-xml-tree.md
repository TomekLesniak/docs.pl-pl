---
title: Modyfikowanie elementów, atrybutów i węzłów w drzewie XML
description: Dowiedz się więcej o metodach i właściwościach, których można użyć do modyfikacji elementu, jego węzłów podrzędnych lub jego atrybutów.
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: 671ba38350e443d95c92a9bd790eac3d2deb5cdd
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553747"
---
# <a name="modify-elements-attributes-and-nodes-in-an-xml-tree-linq-to-xml"></a>Modyfikowanie elementów, atrybutów i węzłów w drzewie XML (LINQ to XML)

Poniższa tabela zawiera podsumowanie metod i właściwości, których można użyć do modyfikacji elementu, jego elementów podrzędnych lub jego atrybutów.

Następujące metody modyfikują <xref:System.Xml.Linq.XElement> :

|Metoda|Opis|
|------------|-----------------|
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|Zastępuje element przeanalizowanym kodem XML.|
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|Usuwa całą zawartość (węzły podrzędne i atrybuty) elementu.|
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Usuwa atrybuty elementu.|
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|Zamienia całą zawartość (węzły podrzędne i atrybuty) elementu.|
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|Zastępuje atrybuty elementu.|
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Ustawia wartość atrybutu. Tworzy atrybut, jeśli nie istnieje. Jeśli wartość jest ustawiona na `null` , program usuwa atrybut.|
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Ustawia wartość elementu podrzędnego. Tworzy element, jeśli nie istnieje. Jeśli wartość jest ustawiona na `null` , powoduje usunięcie elementu.|
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|Zamienia zawartość (węzły podrzędne) elementu na określony tekst.|
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|Ustawia wartość elementu.|

Następujące metody modyfikują <xref:System.Xml.Linq.XAttribute> :

|Metoda|Opis|
|------------|-----------------|
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|Ustawia wartość atrybutu.|
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|Ustawia wartość atrybutu.|

 Następujące metody modyfikują <xref:System.Xml.Linq.XNode> (łącznie z <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XDocument> ):

|Metoda|Opis|
|------------|-----------------|
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|Zamienia węzeł na nową zawartość.|

 Następujące metody modyfikują <xref:System.Xml.Linq.XContainer> ( <xref:System.Xml.Linq.XElement> a lub <xref:System.Xml.Linq.XDocument> ):

|Metoda|Opis|
|------------|-----------------|
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|Zastępuje węzły podrzędne nową zawartością:|
