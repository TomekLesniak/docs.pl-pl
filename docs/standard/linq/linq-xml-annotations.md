---
title: Adnotacje — LINQ to XML
description: Dowiedz się, jak używać adnotacji w LINQ to XML do kojarzenia dowolnego dowolnego dowolnego obiektu dowolnego dowolnego typu z dowolnym składnikiem XML w drzewie XML.
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: 80710b3596fc37ed76f23e31d1d781c64d0bc909
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553368"
---
# <a name="linq-to-xml-annotations-linq-to-xml"></a>LINQ to XML adnotacje (LINQ to XML)

Adnotacje w LINQ to XML umożliwiają kojarzenie dowolnego dowolnego dowolnego obiektu dowolnego dowolnego typu z dowolnym składnikiem XML w drzewie XML.

Aby dodać adnotację do składnika XML, takiego jak <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute> , należy wywołać <xref:System.Xml.Linq.XObject.AddAnnotation%2A> metodę. Pobierasz adnotacje według typu.

Zwróć uwagę, że adnotacje nie są częścią sprawdzonych XML; nie są one serializowane ani deserializowane.

## <a name="methods"></a>Metody

Podczas pracy z adnotacjami można użyć następujących metod:

|Metoda|Opis|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|Dodaje obiekt do listy adnotacji elementu <xref:System.Xml.Linq.XObject> .|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|Pobiera pierwszy obiekt adnotacji określonego typu z <xref:System.Xml.Linq.XObject> .|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|Pobiera kolekcję adnotacji określonego typu dla <xref:System.Xml.Linq.XObject> .|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|Usuwa adnotacje określonego typu z <xref:System.Xml.Linq.XObject> .|
