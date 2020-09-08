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
# <a name="linq-to-xml-annotations-linq-to-xml"></a><span data-ttu-id="7d535-103">LINQ to XML adnotacje (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="7d535-103">LINQ to XML annotations (LINQ to XML)</span></span>

<span data-ttu-id="7d535-104">Adnotacje w LINQ to XML umożliwiają kojarzenie dowolnego dowolnego dowolnego obiektu dowolnego dowolnego typu z dowolnym składnikiem XML w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="7d535-104">Annotations in LINQ to XML enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>

<span data-ttu-id="7d535-105">Aby dodać adnotację do składnika XML, takiego jak <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute> , należy wywołać <xref:System.Xml.Linq.XObject.AddAnnotation%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="7d535-105">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="7d535-106">Pobierasz adnotacje według typu.</span><span class="sxs-lookup"><span data-stu-id="7d535-106">You retrieve annotations by type.</span></span>

<span data-ttu-id="7d535-107">Zwróć uwagę, że adnotacje nie są częścią sprawdzonych XML; nie są one serializowane ani deserializowane.</span><span class="sxs-lookup"><span data-stu-id="7d535-107">Note that annotations aren't part of the XML infoset; they're not serialized or deserialized.</span></span>

## <a name="methods"></a><span data-ttu-id="7d535-108">Metody</span><span class="sxs-lookup"><span data-stu-id="7d535-108">Methods</span></span>

<span data-ttu-id="7d535-109">Podczas pracy z adnotacjami można użyć następujących metod:</span><span class="sxs-lookup"><span data-stu-id="7d535-109">You can use the following methods when working with annotations:</span></span>

|<span data-ttu-id="7d535-110">Metoda</span><span class="sxs-lookup"><span data-stu-id="7d535-110">Method</span></span>|<span data-ttu-id="7d535-111">Opis</span><span class="sxs-lookup"><span data-stu-id="7d535-111">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="7d535-112">Dodaje obiekt do listy adnotacji elementu <xref:System.Xml.Linq.XObject> .</span><span class="sxs-lookup"><span data-stu-id="7d535-112">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="7d535-113">Pobiera pierwszy obiekt adnotacji określonego typu z <xref:System.Xml.Linq.XObject> .</span><span class="sxs-lookup"><span data-stu-id="7d535-113">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="7d535-114">Pobiera kolekcję adnotacji określonego typu dla <xref:System.Xml.Linq.XObject> .</span><span class="sxs-lookup"><span data-stu-id="7d535-114">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="7d535-115">Usuwa adnotacje określonego typu z <xref:System.Xml.Linq.XObject> .</span><span class="sxs-lookup"><span data-stu-id="7d535-115">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
